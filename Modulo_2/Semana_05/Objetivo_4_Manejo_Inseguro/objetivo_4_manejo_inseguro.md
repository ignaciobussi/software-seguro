# Manejo de Errores (Stack Trace)

Hay una gran diferencia entre un mensaje de error genérico y un Stack Trace, podemos verlo principalmente en que respuesta nos dan al momento de que ocurrió un error.

Por ejemplo un mensaje de error genérico seria lo siguiente:
Se produjo un error al procesar la solicitud.
Por favor, intente nuevamente más tarde.

En cambio un mensaje de Stack Trace seria de este modo:
Traceback (most recent call last):
  File "/var/www/app/routes/login.py", line 42, in login
    user = database.get_user(username)
  File "/var/www/app/database.py", line 18, in get_user
    return connection.execute(query)
DatabaseError: no such table: users

Podemos diferenciar que en el segundo ejemplo se revelan mas detalles de la implementación interna de la aplicación que un usuario común no necesita conocer. Entonces al estar en un entorno de producción, la aplicación está disponible para usuarios reales y, potencialmente, para atacantes externos. La exposición de un Stack Trace detallado facilita la explotación porque proporciona información sobre el funcionamiento interno de la aplicación, lo que permite identificar posibles vulnerabilidades y preparar ataques más específicos.
Si estos pueden provocar errores y observar las trazas completas, podrían utilizar la información para:
1. Identificar las tecnologías y los componentes utilizados.
2. Descubrir posibles vulnerabilidades en las bibliotecas o funcionalidades involucradas.
3. Comprender mejor cómo funciona internamente la aplicación.
4. Preparar ataques más específicos aprovechando la información obtenida.
Es importante destacar que la exposición de un Stack Trace no garantiza que exista una vulnerabilidad explotable, pero puede facilitar considerablemente su identificación.
