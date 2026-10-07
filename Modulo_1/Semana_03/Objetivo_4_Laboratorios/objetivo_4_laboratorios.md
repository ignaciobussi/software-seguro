# Informe de Laboratorios

# 1. Apagar la IA

## Procedimiento

1. Veo que al ingresar el laboratorio se pueden ver que los valores que nos da pistas que contienen expresiones regulares buscamos un rango
2. Genere un codigo con IA el cual me genera un rango de hashes del 9000 al 13000
3. Luego pedi que me genere otro script para poder buscar la expresion regular de 16 digitos
4. En el momento que lo encuentra al valor 5524663362514956 lo genero en un numero de MD5 consiguiendo el codigo para finalizar el laboratorio

# 2. El Mejor Secreto

## Procedimiento 

1. Al ver el video de la pista puedo identificar por el sonido que confirma que es una secuencia de 12 digitos, siendo 6a-2-6b-6b-9-6a-9-9-9-9-5-6b calificamos cada valor como distintos digitos osea A-B-C-C-D-A-D-D-D-D-E-C son 5 variables distintas entre si entonces calculo la cantidad de contraseñas que debo generar siendo 10x9x8x7x6 = 30240
2. Le pido a la IA que me genere un codigo que cree esa cantidad de contraseñas para tener un archivo con todas las posibilidades
3. Luego genero otro script en el cual le digo que al archivo que me creo anteriormente con las contraseñas lo utilice para hacer un ataque de fuerza bruta en el archivo zip automatizandolo. 
4. Encuentra la contaseña que es 547795999937 el cual me permite ingresar al archvio brindando el codigo que nos permite finalizar el laboratorio

# 3. Votacion

## Procedimiento

1. Al hacer una votacion nos fijamos que tipo de peticion se genera 
2. En la peticion aparece un set-cookie, lo que no deberia aparecer y nos agrega una cookie para negarnos la repeticion de voto
3. Al comprar la con la primera votacion que se realizo, se ve que en esa no hay una cookie 
4. al reenviar esa peticion en el repetear se suma un voto mas
5. La envio al intruder cambiando un parametro que no afecte para poder pasar en votos a harvard
6. Al superar la en votos nos dan el codigo, dando por finalizado el laboratorio

# 4. Votacion Nueva

## Procedimiento

1. Al hacer la votacion se genera una peticion
2. En la peticon al querer votar de nuevo nos dice que no podemos votar de nuevo por el uso de la misma IP
3. Utilizo un header X-Forwarded-For: 199.123.122.<1> como ip marcando el 1 como parametro number en el intruder
4. Genero las peticiones necesarias para poder seobrepasar a harvard 
5. Superando los votos nos dan el codigo dandolo por finalizado
