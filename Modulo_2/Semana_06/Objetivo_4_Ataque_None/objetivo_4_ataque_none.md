# Análisis del Ataque de Algoritmo "None"

El algoritmo `none` representa un JWT **sin firma criptográfica**. Esta vulnerabilidad aparece cuando el **backend acepta este tipo de token en un contexto en el que debería exigir una firma válida**.

La firma permite comprobar la **integridad y autenticidad del JWT**. Si un atacante modifica el Payload de un token firmado, la firma original deja de ser válida para ese contenido modificado, por lo que un servidor correctamente implementado debería rechazarlo.

En el caso de que el backend acepte tokens con `alg: none` sin verificar una firma válida, un atacante podría **modificar el Payload**, por ejemplo, un campo relacionado con el rol. Si la aplicación confía en esos datos para identificar al usuario o determinar sus permisos, podría aceptar una **identidad falsificada**.

En este escenario, el atacante no necesita conocer la clave secreta del servidor, porque **no necesita generar una firma válida**: aprovecha la ausencia de una verificación criptográfica obligatoria. El problema no consiste en descubrir la clave, sino en que el backend **confía en información cuya autenticidad no comprobó**.

El impacto depende de la implementación de la aplicación. Para prevenir esta vulnerabilidad, el servidor debe:

- **Definir explícitamente los algoritmos permitidos.**
- **Rechazar tokens sin firma** cuando se requiera una firma válida.
- **Verificar la autenticidad del JWT** antes de confiar en sus datos.