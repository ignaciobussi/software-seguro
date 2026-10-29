# La única mitigación definitiva (Prepared Statements)

## ¿Cómo funcionan las consultas parametrizadas?

Cuando se construye una consulta SQL concatenando directamente los datos ingresados por el usuario, existe el riesgo de que estos alteren la estructura de la consulta y permitan ejecutar instrucciones no deseadas.

En cambio, una **consulta parametrizada (Prepared Statement)** separa la estructura SQL de los datos recibidos. Los valores se envían por separado y se interpretan como datos, no como instrucciones SQL, evitando que el usuario altere la consulta mediante esos parámetros.

## ¿Por qué son más efectivas que las listas negras?

Las listas negras intentan bloquear palabras o caracteres sospechosos, como `SELECT`, `UNION` o las comillas simples, pero pueden evadirse mediante diferentes formas de construir una inyección.

En cambio, **las consultas parametrizadas separan el código SQL de los datos recibidos**, por lo que los caracteres especiales y las palabras reservadas se interpretan como parte del valor y no como instrucciones SQL.

Esta técnica previene las inyecciones a través de los parámetros correctamente implementados, aunque otros elementos dinámicos de una consulta pueden necesitar validaciones adicionales.
