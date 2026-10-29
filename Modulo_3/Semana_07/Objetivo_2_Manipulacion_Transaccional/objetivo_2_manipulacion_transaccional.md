# Descripción del escenario

Un e-commerce permite agregar productos a un carrito mediante una petición al servidor que incluye, entre otros datos, el identificador del producto y la cantidad solicitada.
Por ejemplo, el cliente podría enviar una petición con una cantidad de `1`. Si un usuario modifica ese parámetro a `-5` y el servidor acepta el valor sin validarlo, la aplicación podría calcular un subtotal negativo.
La vulnerabilidad aparece cuando el backend confía en un dato controlado por el cliente y no comprueba que cumpla las reglas del negocio.
Es importante aclarar que un subtotal negativo no acredita dinero automáticamente. Para que se produzca una ganancia indebida, también tendría que existir una falla en la lógica que procesa los importes, pagos o saldos.

## ¿Porque ocurre esta falla?

Esta falla ocurre porque el backend no realiza una validación adecuada de los datos de entrada.
Si no realiza esta validación ocurre lo planteado en el escenario, es decir el servidor al confiar en el valor recibido sin verificar que es valido, un usuario puede modificar los parámetros. El origen principal de la vulnerabilidad es la ausencia de controles de validación en el servidor y la falta de restricciones que garanticen el cumplimiento de las reglas de negocio. Donde la validación exclusiva del frontend no es suficiente, ya que se pueden modificar antes de llegar al backend

## ¿Como mitigar esta falla?

Hay varias formas de poder mitigarla primero debería validarse el contenido en el backend, teniendo los campos con un valor esperado, mayor a cero, ademas que el numero respete las reglas de negocio (si es entero que solamente se utilicen enteros y no permitan el uso de un numero con coma), tampoco deberían superar el máximo permitido, entonces si se modifica algo el servidor debe rechazar la petición y no modificar el carrito.
Calcular los importes en el servidor y no confiar en el frontend.
Proteger las operaciones económicas, que las devoluciones y reembolsos tengan sus operaciones especificas con sus validaciones y controles propios.
Por ultimo utilizar controles consistentes reglas aplicadas en todos los puntos relevantes del backend, no solo en la pantalla o endpoints. Las operaciones que modifican deben mantener la consistencia de los datos.

