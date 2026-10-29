# El punto ciego de los escáneres automatizados

Las herramientas automatizadas de análisis de seguridad, como **Nessus, Acunetix y el escáner activo de Burp Suite**, son útiles para detectar **vulnerabilidades técnicas**, como **XSS** o configuraciones inseguras. Sin embargo, presentan limitaciones para identificar **fallas en la lógica de negocio**.

Esto se debe a que las vulnerabilidades de lógica de negocio dependen de las **reglas específicas** y del **funcionamiento esperado** de cada aplicación. Por ejemplo, una tienda podría ofrecer un descuento exclusivo para nuevos usuarios, pero permitir que una misma persona cree varias cuentas para obtener el beneficio repetidamente. Aunque las operaciones se ejecuten técnicamente sin errores, el sistema no estaría respetando la **regla comercial establecida**.

Los escáneres automatizados pueden tener dificultades para detectar estos casos porque no siempre conocen las **reglas del negocio** ni pueden deducir todas las **secuencias de acciones** que un usuario podría realizar para aprovecharlas.

Por este motivo, la **auditoría manual** es indispensable: permite comprender el funcionamiento de la aplicación, analizar sus reglas y probar diferentes flujos de ejecución para identificar comportamientos que, aunque sean técnicamente válidos, **no deberían estar permitidos**.

En conclusión, las herramientas automatizadas y la auditoría manual son **complementarias**. Los escáneres permiten detectar numerosos problemas técnicos de forma eficiente, mientras que el **análisis manual** ayuda a descubrir fallas que requieren comprender el contexto y las reglas particulares del negocio.
