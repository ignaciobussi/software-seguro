# Informe de Laboratorios

# 1. Turnero

1. Empezamos accediendo al laboratorio Turnero
2. Analizamos las peticiones que se generan al comenzar **(XHR)**
3. Podemos identificar una url que tiene **api/user_id/appointments**
4. Verificamos que al cambiar el numero de nuestro usuario a otro numero random nos muestra otros datos por lo que damos por sentado que nos permite entrar a otros usuarios al cambiar ese numero
5. Utilizamos Burp para editar esa URL y que envia constantes peticiones hasta conseguir el usuario "xdalvik"
6. Una vez que lo encontramos utilizamos el metodo DELETE /api/appointments/id el cual tambien te permite borrar cosas de otros usuarios ya que no tiene necesidad de ninguna verficacion previa
7. Colocamos los ids de los turnos de xdalvik, borrando uno por uno
8. Recargamos la pagina, y conseguimos el codigo para finalizar el laboratorio

# 2. Ventas 

# 4. Gran Rifa 2019

# Procedimiento

1. Accedi al laboratorio Gran Rifa 2019
2. Abri la herramienta de desarrollo
3. Descubri que la pagina me **permitia editar el nombre** de la persona
4. Ingresamos a la seccion de **Red** en la herramienta de desarrollo y podemos ver las peticiones que se realizaron.
5. Corroboramos en la peticion GET del archivo /api/numeros la parte de Respuesta para poder conocer el JSON y el nombre de cada variable y su valor
6. Al editar el nombre puede verse que se genera una **peticion POST relacionada a John Backus**.
7. A esa peticion **elegi editar y volver a enviar**
8. Generamos una **nueva peticion POST** donde en el cuerpo escribiremos **{"esta_pago": true}**. 
9. envie la peticion y verifique que la respuesta del servidor indica que el **estado "OK"**.
9. Finalmente recargue la pagina, consiguiendo el codigo para dar por finalizado el laboratorio.
