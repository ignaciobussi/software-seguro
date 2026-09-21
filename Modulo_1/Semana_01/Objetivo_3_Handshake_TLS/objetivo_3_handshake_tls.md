##HandShake TLS

El **Handshake TLS** es el proceso donde el navegador y el servidor se ponen de acuerdo para poder establecer una conexión segura de manera cifrada antes de comenzar a intercambiar datos de la aplicación.

## 1. ¿Como funciona el proceso?

Durante ese proceso el cliente envía un mensaje **ClientHello**, esto incluye una lista de los algoritmos criptográficos que soporta. El servidor recibe el **ClientHello** y responde con **ServerHello** seleccionando la combinación compatible para utilizar durante la conexión. 
Luego el servidor envía su **certificado digital** al navegador. Este certificado permite al navegador verificar la identidad del servidor, comprobando que sea valido y corresponda al sitio que queremos acceder. 
Después, ambos establecen un secreto compartido para no enviar directamente texto por internet, donde realizan operaciones criptográficas manteniendo el secreto.
El TLS combina ambos tipos de cifrado, ya que utiliza las propiedades de la **criptografía asimétrica** para la autenticación y el establecimiento de la conexión, y luego utiliza **cifrado simétrico** para proteger los datos de la aplicación de manera eficiente.
Una vez que ambos tienen las claves necesarias para proteger la comunicación comienza el intercambio de los datos de la aplicación.

