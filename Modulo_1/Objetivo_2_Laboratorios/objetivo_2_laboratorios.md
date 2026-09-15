# Informe de Laboratorios

# 1. Turnero

## Procedimiento

1. Empezamos accediendo al laboratorio Turnero
2. Analizamos las peticiones que se generan al comenzar **(XHR)**
3. Podemos identificar una URL que tiene **api/user_id/appointments**
4. Verificamos que al cambiar el numero de nuestro usuario a otro numero random nos muestra otros datos por lo que damos por sentado que nos permite entrar a otros usuarios al cambiar ese numero
5. Utilizamos Burp para editar esa URL y que envia constantes peticiones hasta conseguir el usuario "xdalvik"
6. Una vez que lo encontramos utilizamos el método DELETE /api/appointments/id el cual también te permite borrar cosas de otros usuarios ya que no tiene necesidad de ninguna verificación previa
7. Colocamos los ids de los turnos de xdalvik, borrando uno por uno
8. Recargamos la pagina, y conseguimos el código para finalizar el laboratorio

# 2. Ventas 

## Procedimiento 

1. Empezamos accediendo al laboratorio Ventas
2. En el enunciado nos dice que se encuentra en la ruta /ventas entonces en la URL agregamos ese endpoint
3. Agregamos un parámetro /?id=1 donde se recarga sola la pagina mostrando un texto forbidden
4. Podemos deducir por el estado 403 que eso significa que es en realidad una venta que se realizo pero no tenemos los permisos para poder verla
5. Utilizamos un script que nos permite poder hacer constantes peticiones cambiando de ?id=1 a 2, 3, 4, ... y que haga conteo de los estados 403
6. Al finalizar nos muestra el numero de 1641 ventas por el estado 403 a ese valor lo enviamos en MD5 generando el código 10c272d06794d3e5785d5e7c5356e9ff
7. Damos por finalizado el laboratorio

# 3. Presupuesto

## Procedimiento

1. Accedí al laboratorio de Presupuesto
2. Hice un calculo auxiliar para poder sacar los valores que se requieren para poder completar el laboratorio
3. Descubrí que al apretar el botón de **Revisar** la petición que envía es **/api/gastos/(id)/editar**, entonces significa que podemos realizar cambios
4. Busco el **JSON /api/gastos** para conocer el nombre de la variable del monto
5. A la petición del paso 3 la **edito y vuelvo a enviar** como una petición **POST** donde en el body pongo el monto que debería poner para que den los resultados
6. Los valores que disminuí fue Flete de 6000 a 500, Agua de 1000 a 500 y Seguros de 5000 a 1500 (9500 en total) y aumente Luz de 2000 a 5000 y Reuniones de 2000 a 4000 (5000 en total)
7. Al tener todo revisado y que den bien los promedios nos dan el código
8. Damos por finalizado el laboratorio

# 4. Gran Rifa 2019

## Procedimiento

1. Accedí al laboratorio Gran Rifa 2019
2. Abrí la herramienta de desarrollo
3. Descubrí que la pagina me **permitía editar el nombre** de la persona
4. Ingresamos a la sección de **Red** en la herramienta de desarrollo y podemos ver las peticiones que se realizaron.
5. Corroboramos en la petición GET del archivo /api/números la parte de Respuesta para poder conocer el JSON y el nombre de cada variable y su valor
6. Al editar el nombre puede verse que se genera una **petición POST relacionada a John Backus**.
7. A esa petición **elegí editar y volver a enviar**
8. Generamos una **nueva petición POST** donde en el cuerpo escribiremos **{"esta_pago": true}**. 
9. Envié la petición y verifique que la respuesta del servidor indica que el **estado "OK"**.
9. Finalmente recargue la pagina, consiguiendo el código para dar por finalizado el laboratorio.
