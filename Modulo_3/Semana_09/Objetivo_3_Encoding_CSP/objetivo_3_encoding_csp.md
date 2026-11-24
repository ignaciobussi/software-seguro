# Defensa en Profundidad (Encoding y CSP)

Un arquitecto de seguridad puede reducir considerablemente el riesgo de ataques XSS mediante la implementación de dos capas de defensa complementarias.

## 1. Output Encoding (Codificación de Salida)

Consiste en transformar los caracteres especiales de los datos ingresados por el usuario en representaciones seguras según el contexto donde serán utilizados.

Por ejemplo, en un contexto HTML, los caracteres `<` y `>` se convierten en las entidades HTML `&lt;` y `&gt;`, respectivamente. Esto permite que el navegador interprete el contenido como texto simple y no como código ejecutable.

Esta defensa se implementa a nivel de código y busca prevenir la vulnerabilidad desde su origen.

## 2. Content Security Policy (CSP)

Es una política de seguridad implementada mediante cabeceras HTTP que permite establecer restricciones sobre los recursos que el navegador puede cargar y ejecutar.

Por ejemplo:

```http
Content-Security-Policy: default-src 'self'; script-src 'self';
```

Esta política restringe la carga de scripts al mismo origen de la aplicación y bloquea la ejecución de JavaScript inline.

De esta manera, si un atacante logra inyectar código malicioso debido a un error en la codificación de salida, el navegador puede impedir su ejecución.

Sin embargo, una CSP mal configurada o demasiado permisiva podría ser evadida. Por eso, debe utilizarse como una segunda capa de seguridad que complemente al Output Encoding y no como un reemplazo de este.
