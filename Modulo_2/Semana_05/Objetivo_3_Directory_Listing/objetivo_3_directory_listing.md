# Directory Listing

Es una falla de seguridad en la cual, al estar activa si un atacante accede a un directorio que no contiene un archivo indice el servidor web genera automáticamente una pagina en donde se muestra el **listado de contenidos de directorios y subdirectorios**. 

## Que ocurre cuando el atacante puede navegar por los directorios y que tipos de archivos sensibles se exponen?

El peligro que puede generar es la visibilidad de archivos sensibles como copias de seguridad (.bak, .zip o .tar.gz), bases de datos (.sql), archivos de configuración (.env) o registros (.log). También la descarga de información confidencial que seria obtener datos personales, credenciales o códigos fuentes si los archivos están accesibles (.php o .js). Por ultimo es posibles que puedan preparar ataques utilizando la información encontrada para identificar vulnerabilidades o buscar formas de acceder al sistema.

## Como mitigarlo?

Para poder mitigar esta falla de seguridad hay varias opciones
1. **Deshabilitar el Directory Listing**, es decir configurar el servidor para que no se genere automáticamente el listado de archivos.
2. **Proteger los archivos sensibles** almacenar copias de seguridad, credenciales y archivos de configuración fuera del directorio público del sitio web.
3. **Aplicar permisos adecuados**, restringir el acceso a archivos y directorios según el principio de mínimo privilegio. 
4. **Implementar controles de acceso** utilizando mecanismos de autenticación y autorización para proteger los recursos que no deben ser públicos.
5. **Revisar periódicamente el servidor** se comprueba que no existan archivos confidenciales publicados accidentalmente y verificar que las configuraciones de seguridad sean correctas.
