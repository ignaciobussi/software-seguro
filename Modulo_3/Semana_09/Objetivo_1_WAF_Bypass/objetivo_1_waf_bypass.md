# ¿Por qué es inútil eliminar únicamente las etiquetas <script>?

La defensa que se propone es insuficiente porque intenta evitar el XSS mediante una **lista negra de cadenas**, es decir elimina las etiquetas script y /script. El problema de hacer esto es que Javascript puede ejecutarse en el navegador de otras formas, sin necesidad de utilizar esas etiquetas.
En HTML hay mas atributos que ejecutan codigo cuando ocurre un evento. Por ejemplo **onerror** y **onload**. Por eso, aunque el filtro elimine las etiquetas script, un atacante puede introducir elementos HTML con manejadores de eventos que ejecuten el JavaScript.

# PayLoad que ejecutan sin utilizar <script>

## Payload 1: atributo onerror en una imagen

img src=x onerror="alert('XSS')"

Lo que ocurre con esto es que el navegador intenta cargar la imagen indicada por src=x. Como el recurso no existe o no puede cargarse, se dispara el evento error y se ejecuta el código JavaScript contenido en onerror.

## Payload 2: atributo onclick

a href="#" onclick="alert('XSS')"

Se crea un enlace HTML mediante la etiqueta a y se utiliza el atributo onclick para ejecutar código JavaScript cuando el **usuario hace clic sobre él**. En este caso, se ejecuta alert('XSS'), mostrando una ventana emergente con el mensaje XSS.

