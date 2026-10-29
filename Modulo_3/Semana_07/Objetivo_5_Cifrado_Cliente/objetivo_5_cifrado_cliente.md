# Descripción del escenario

Una aplicación financiera cifra los datos de las peticiones mediante **JavaScript** antes de enviarlos al servidor. El equipo de desarrollo considera que esto impide que un usuario pueda leer o modificar los datos utilizando herramientas como **Burp Suite**.

Sin embargo, un usuario que controla su propio navegador puede modificar los datos **antes de que JavaScript los cifre**. Por ejemplo, podría cambiar el monto de una transferencia y dejar que la aplicación cifre el valor modificado antes de enviarlo al servidor.

La vulnerabilidad aparece cuando el **backend confía en los datos recibidos** y no verifica que la operación cumpla las reglas de negocio. El cifrado no garantiza que los valores enviados sean legítimos ni que el usuario esté autorizado a realizar la operación.

# ¿Por qué esta afirmación genera una falsa sensación de seguridad?

Esta afirmación genera una falsa sensación de seguridad porque se considera que cifrar los datos en el frontend impide que el usuario pueda modificarlos. Sin embargo, como JavaScript se ejecuta en el navegador del usuario, este puede cambiar los valores **antes de que sean cifrados**.

Por ejemplo, podría modificar el monto de una transferencia y dejar que la aplicación cifre el nuevo valor. Así, no necesitaría **romper el cifrado** para intentar manipular la petición.

El problema principal aparece cuando el backend confía en los datos recibidos sin validar que cumplan las reglas de negocio. Por eso, el servidor debe comprobar que la operación esté **autorizada** y que respete los **límites establecidos**, independientemente de que los datos estén cifrados.

# ¿Dónde reside el fallo fundamental de diseño y cómo podría un atacante evadir esta protección?

El fallo fundamental consiste en **confiar en el frontend como mecanismo de seguridad**, cuando el usuario puede controlar y modificar lo que ocurre en su propio navegador.

Un atacante podría realizar los siguientes pasos:

1. **Interceptar una petición** con Burp Suite para observar los datos enviados al servidor.
2. **Analizar el JavaScript** para identificar cómo se procesan y cifran los datos.
3. **Modificar los valores antes del cifrado**, evitando tener que romper el algoritmo criptográfico.
4. **Enviar la petición modificada** y comprobar si el backend acepta los valores sin validar las reglas de negocio.

Para leer los datos, también podría inspeccionar el código y observar los **valores originales antes de que sean cifrados**. Esto demuestra que el cifrado en el frontend no impide que el usuario manipule los datos de su propio navegador.
