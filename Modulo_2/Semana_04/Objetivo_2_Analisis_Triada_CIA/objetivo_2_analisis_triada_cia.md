# Analisis Triada CIA 

## Confidencialidad:

Asegura que solo las personas puedan ver o usar los datos. Se protege con contraseñas, cifrado y control de accesos.

### Tipo de ataque relacionado:

Una vulnerabilidad seria **IDOR/Broken Access Control**: Si estuvieras logueado con un usuario por ejemplo el usuario/1 y cambias por el /usuario/2 y el sistema te lo permite aunque no estes autorizado.

## Integridad:

Garantiza que los datos sean exactos, reales y que no hayan sido cambiados por error o malicia. Se protege con firmas digitales y códigos hash.

### Tipo de ataque relacionado:

Una vulnerabilidad seria **SQLInjection**: Si una aplicacion construye una consulta SQL insegura, un atacante podria modificar registros de una base de datos

## Disponibilidad:

Permite que los sistemas y datos estén listos y funcionando para los usuarios autorizados cuando los necesiten. Se apoya en copias de seguridad y sistemas de respaldo.

### Tipo de ataque relacionado:

Una vulnerabilidad seria un ataque **DDoS**: Si un atacante consigue saturar el servidor, haciendo que los usuarios no puedan utilizar el servicio.