# Diferencia entre Ataque de fuerza Bruta y Ataque de Diccionario

Ambos ataques son métodos automatizados para poder adivinar las credenciales de un formulario de autenticación (login), pero se diferencian en la **estrategia de generación de combinaciones** y en la **eficiencia**

En el ataque de **Fuerza bruta** es un método es muy ineficiente, ya que este se basa en **todas las combinaciones posibles** de caracteres (letras, números, símbolos). Empezando a probar con 'a', 'b', 'c', 'ab', y así sucesivamente siendo muy tedioso y crece de manera exponencial conforme aumenta la longitud.
En cambio con el **Ataque de Diccionario** se le brinda una **lista predefinida de palabras**, pudiendo ser claves comunes o variaciones conocidas. Este diccionarios pueden tener contraseñas como '123456', 'password'. 'admin', 'qwerty', etc. Es **rápido y eficiente**. Depende del tamaño del diccionario, reduciendo en gran cantidad el numero de intentos.

# Mecanismos de defensa
Para evitar o mitigar los ataque de automatización, se pueden implementar las siguientes medidas.

## A. Bloque IP + CUENTA 
* **Descripción:** Limite la cantidad de peticiones permitidas desde una misma dirección de IP hacia un usuario especifico.
* **Impacto:** Bloquea la combinacion de la IP + CUENTA permitiendo acceder desde otra IP a esa cuenta (en caso de que si hubiera un intento de acceder de manera maliciosa) y también permitir a esa IP acceder a otras cuentas (en caso de que sea un empresa y así no bloquear el acceso a todos),

## B. Desafió CAPTCHA
* **Descripción:** Introduce una prueba de interacción humana al querer acceder a una cuenta.
* **Impacto:** Bloquea las herramientas automatizadas (como el intruder en Burp) al no poder resolver el reto.
