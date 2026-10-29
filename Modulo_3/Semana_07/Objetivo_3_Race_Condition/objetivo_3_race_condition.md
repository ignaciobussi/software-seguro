# ¿Cómo puede un atacante utilizar la herramienta Turbo Intruder de Burp Suite?

Un atacante podría utilizar **Turbo Intruder**, una herramienta de **Burp Suite**, para enviar 50 peticiones HTTP concurrentes al endpoint encargado de canjear un código de descuento de un solo uso.

La técnica **Last-Byte Synchronization** busca sincronizar las solicitudes concurrentes para que lleguen al servidor con una diferencia temporal mínima. Para ello, Turbo Intruder prepara las peticiones y coordina el envío de sus últimos bytes, de modo que las solicitudes puedan llegar al servidor en un intervalo muy reducido. Esto disminuye el efecto de las diferencias de latencia y aumenta las posibilidades de que varias peticiones coincidan dentro de la misma ventana de carrera.

Si el servidor comprueba que el cupón está disponible, pero demora en registrar su utilización en la base de datos, varias solicitudes podrían superar esa comprobación antes de que se actualice el estado del cupón. Como consecuencia, el sistema podría aplicar el descuento varias veces, aunque el código solo permita un canje.

Pero, enviar 50 peticiones simultáneas no garantiza que el ataque tenga éxito. El resultado depende de cómo el servidor procese las solicitudes y gestione las operaciones sobre la base de datos.
