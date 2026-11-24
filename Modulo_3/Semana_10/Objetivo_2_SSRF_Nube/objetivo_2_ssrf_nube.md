# SSRF y el Peligro en la Nube (AWS/GCP)

Una vulnerabilidad SSRF permite que un atacante manipule las peticiones realizadas por un servidor, aprovechando su acceso a recursos internos que normalmente no son accesibles desde Internet.

## Servicio de metadatos de AWS

En AWS, la dirección `169.254.169.254` corresponde al servicio Instance Metadata Service (IMDS), utilizado por las instancias EC2 para consultar información sobre su configuración.

Esta dirección es de tipo Link-Local, por lo que no es accesible directamente desde Internet. Sin embargo, mediante una vulnerabilidad SSRF, un atacante podría conseguir que el servidor realice una petición hacia dicho servicio.

## Información sensible que puede obtener el atacante

La información que podría quedar expuesta incluye:

- Identificador de la instancia EC2.
- Dirección IP privada.
- Región y zona de disponibilidad.
- Roles IAM asociados a la instancia.
- Credenciales temporales de AWS.

Las credenciales temporales representan el mayor riesgo y están compuestas por:

- **AccessKeyId:** identificador de la clave de acceso.
- **SecretAccessKey:** clave secreta de autenticación.
- **Token:** token de seguridad de las credenciales temporales.

## Impacto del ataque

Dependiendo de los permisos asignados al rol IAM, el atacante podría:

- Acceder a información privada almacenada en buckets S3.
- Consultar o modificar recursos de la infraestructura.
- Acceder a secretos almacenados en servicios de AWS.
- Eliminar recursos o información.
- Comprometer otros componentes de la infraestructura Cloud.

## Protección mediante IMDSv2

AWS dispone de una segunda versión del servicio de metadatos denominada IMDSv2, que requiere un token de sesión para acceder a la información.

A diferencia de IMDSv1, una petición GET simple no resulta suficiente cuando IMDSv2 es obligatorio, lo que dificulta considerablemente la explotación mediante SSRF.