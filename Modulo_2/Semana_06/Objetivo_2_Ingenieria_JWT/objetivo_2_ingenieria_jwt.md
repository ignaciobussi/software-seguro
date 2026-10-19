# Ingeniería Inversa a JSON Web Tokens (JWT)

Utilice un laboratorio de PortSwigger para poder obtener un JWT de prueba. Mediante las herramientas de desarrollo del navegador, se inspeccionó una respuesta HTTP y se identificó un token en el encabezado `Set-Cookie`, asociado a la cookie `session`.

Posteriormente, se decodificaron el Header y el Payload para identificar el algoritmo de firma declarado y analizar la información contenida en el token.
 
## JWT obtenido 

### HEADER:

{
    "kid": "83aa092b-fa1d-4ac4-b39e-51a395222fc4",
    "alg": "RS256"
}

### PAYLOAD:

{
    "iss": "portswigger",
    "exp": 1792091172,
    "sub": "wiener"
}

## Header

En el Header podemos identificar el campo `alg`, que declara el algoritmo de firma utilizado por el token. En este caso, el valor es `RS256`.
También encontramos el campo `kid`, que identifica la clave que el sistema puede seleccionar para verificar la firma.

## Playload

En el Payload podemos identificar tres campos:

- `iss` (Issuer): identifica al emisor declarado del token. En este caso, 
  su valor es `portswigger`.

- `exp` (Expiration Time): indica la fecha y hora de vencimiento del token.

- `sub` (Subject): identifica al sujeto al que hace referencia el token. 
  En este caso, su valor es `wiener`, que corresponde al usuario utilizado 
  en el laboratorio.

El Payload contiene información que puede leerse después de decodificar el token, como el emisor, el identificador del usuario y la fecha de vencimiento.
En el contenido analizado no se identificaron contraseñas, credenciales ni roles explícitos.