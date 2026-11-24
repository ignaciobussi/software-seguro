# Comparación técnica entre XSS y CSRF

La diferencia fundamental entre ambos ataques es que **XSS explota la confianza que tiene el navegador en una aplicación web, mientras que CSRF explota la confianza que tiene una aplicación web en las peticiones realizadas por el navegador.**

En un ataque XSS, el atacante consigue ejecutar código JavaScript malicioso dentro del contexto de la aplicación legítima, permitiéndole acceder a información sensible, modificar el contenido de la página o realizar acciones en nombre de la víctima. En cambio, en un ataque CSRF, el atacante no necesita inyectar código dentro de la aplicación, sino que busca provocar el envío de peticiones no autorizadas aprovechando que el navegador adjunta automáticamente las cookies de sesión de la víctima.

Desde el punto de vista técnico, mientras que XSS se origina por el tratamiento inseguro de datos no confiables que terminan siendo interpretados como código ejecutable, CSRF se produce porque el servidor valida la autenticación del usuario, pero no verifica adecuadamente la legitimidad de la petición recibida.