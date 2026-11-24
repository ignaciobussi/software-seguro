# Anatomía de un Ataque CSRF (Cross-Site Request Forgery)

CSRF es una vulnerabilidad que permite a un atacante realizar acciones en nombre de una víctima que se encuentra autenticada en una aplicación web, sin necesidad de conocer sus credenciales ni robar sus cookies de sesión.

## Flujo de un ataque CSRF

1. La víctima inicia sesión en una aplicación web y el navegador almacena su cookie de sesión.
2. El atacante prepara una página maliciosa que provoca el envío de una petición hacia la aplicación vulnerable.
3. La víctima accede a la página maliciosa mientras mantiene su sesión activa.
4. El navegador envía la petición hacia la aplicación y, si las políticas de cookies lo permiten, adjunta automáticamente la cookie de sesión de la víctima.
5. El servidor valida la cookie y ejecuta la acción solicitada sin comprobar si fue realizada voluntariamente por el usuario.

## ¿Por qué ocurre este fallo de seguridad?

Esta vulnerabilidad ocurre debido al comportamiento automático de los navegadores, que adjuntan las cookies correspondientes al sitio de destino cuando las políticas de seguridad lo permiten.

El servidor utiliza estas cookies para identificar al usuario, pero no verifica adecuadamente la legitimidad de la petición.

Incluso si la cookie posee el atributo `HttpOnly`, el ataque puede realizarse, ya que este atributo impide que JavaScript acceda a la cookie, pero no evita que el navegador la envíe automáticamente.

## Mitigación mediante el atributo SameSite

El atributo `SameSite` permite controlar el envío de cookies en peticiones originadas desde otros sitios web.

### SameSite=Strict

```http
Set-Cookie: session=abc123; SameSite=Strict
```

Es la configuración más restrictiva, ya que impide el envío de cookies en peticiones provenientes de otros sitios, incluso cuando el usuario accede mediante un enlace externo.

### SameSite=Lax

```http
Set-Cookie: session=abc123; SameSite=Lax
```

Permite el envío de cookies en determinadas navegaciones externas, como aquellas realizadas mediante enlaces GET, pero restringe su envío en peticiones POST y cargas de recursos provenientes de otros sitios.

Sin embargo, si una aplicación permite modificar información mediante peticiones GET, podría continuar siendo vulnerable a CSRF.

Por este motivo, se recomienda complementar el atributo `SameSite` con mecanismos adicionales, como tokens anti-CSRF y la validación de la cabecera `Origin`.