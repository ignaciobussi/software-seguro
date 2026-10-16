# Auditoria de Cookies y Banderas de Seguridad

## Sitios web de uso publico

### Mercado Libre

| Cookie | HttpOnly | Secure | SameSite | Evaluación |
|---|---|---|---|---|
| `_csrf` | true | true | None | La cookie tiene activadas las banderas HttpOnly y Secure, lo que restringe su acceso directo desde JavaScript y evita su envío mediante conexiones HTTP sin cifrar. Sin embargo, SameSite=None permite su envío en contextos entre sitios. |

### Wikipedia

| Cookie | HttpOnly | Secure | SameSite | Evaluación |
|---|---|---|---|---|
| `eswikimwuser-sessionId` | false | false | Vacío | La cookie no tiene activadas las banderas HttpOnly ni Secure. Si efectivamente contiene un identificador de sesión autenticada, JavaScript podría acceder a ella mediante document.cookie y, si se envía por una conexión HTTP sin cifrar, podría quedar expuesta a la interceptación. La ausencia de SameSite tambien es visible en la herramienta. |

### GitHub

| Cookie | HttpOnly | Secure | SameSite | Evaluación |
|---|---|---|---|---|
| `_gh_sess` | true | true | Lax | La cookie tiene activadas las banderas HttpOnly y Secure, lo que restringe su acceso directo desde JavaScript y evita su envío mediante conexiones HTTP sin cifrar. Además, SameSite=Lax limita su envío en determinados contextos entre sitios. |

## Bandera HTTPOnly 

Esta bandera controla si JavaScript puede acceder directamente a una cookie mediante mecanismos como document.cookie. Puede tener los siguientes valores:

- **true:** JavaScript no puede leer la cookie mediante document.cookie.

- **false:** JavaScript puede leerla mediante ese mecanismo, siempre que esté disponible para el contexto correspondiente.

Para las cookies que contienen una sesión autenticada, se recomienda configurar HttpOnly=true, ya que ayuda a reducir el riesgo de robo de la sesión mediante ataques de Cross-Site Scripting (XSS). Sin embargo, esta bandera no evita por sí sola los ataques XSS ni impide que un script malicioso realice otras acciones en nombre del usuario.

## Bandera Secure

Esta bandera indica que el navegador solo debe enviar la cookie mediante conexiones HTTPS, protegiendola frente al envio a traves de conexiones HTTP sin cifrar

- **true:** el navegador solo envía la cookie mediante HTTPS.

- **false:** la cookie podría enviarse mediante una conexión HTTP sin cifrar, si la solicitud coincide con su dominio y ruta y se cumplen las demás condiciones.

Si una cookie de sesión no tiene activada la bandera Secure, un atacante que pueda interceptar una comunicación HTTP podría obtener el identificador de sesión y utilizarlo para suplantar al usuario, siempre que consiga capturarlo y la sesión siga siendo válida. Esto se conoce como secuestro de sesión (Session Hijacking).
