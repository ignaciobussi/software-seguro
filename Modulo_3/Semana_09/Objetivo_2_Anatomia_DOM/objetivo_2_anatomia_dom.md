El DOM-Based XSS puede pasar inadvertido para muchos sistemas de prevención de intrusos (IPS) y firewalls de aplicaciones web (WAF) porque la vulnerabilidad se produce directamente en el navegador, sin necesidad de que el contenido malicioso llegue al servidor.

Esto ocurre debido a que los navegadores no envían al servidor el fragmento de una URL que aparece después del carácter #. Sin embargo, JavaScript puede acceder a esa información mediante location.hash.

Por ejemplo, si una aplicación utiliza el siguiente código:

document.getElementById('saludo').innerHTML = location.hash.substring(1)

Está obteniendo el contenido del fragmento de la URL y colocándolo dentro del HTML mediante innerHTML. El problema es que este método interpreta el contenido como HTML, por lo que una entrada maliciosa podría provocar la ejecución de código JavaScript en el navegador de la víctima.

De esta manera, aunque el servidor nunca reciba el contenido malicioso, el navegador sí lo procesa mediante el código JavaScript de la aplicación.

Por este motivo, los WAF e IPS pueden no detectar el ataque: inspeccionan las solicitudes HTTP, pero no necesariamente pueden analizar lo que sucede posteriormente dentro del navegador. Esto representa una limitación de los mecanismos de protección tradicionales frente a vulnerabilidades que se producen del lado del cliente.
