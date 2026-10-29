# Automatización vs Explotación manual (sqlmap)

## Escenario 1: Peticiones complejas

sqlmap puede tener dificultades cuando una aplicación requiere modificaciones específicas en la petición, como gestionar tokens, cookies o condiciones particulares de una sesión.

En cambio, un pentester puede analizar la petición con Burp Suite, modificarla manualmente y observar cómo responde el servidor para identificar posibles vulnerabilidades.

## Escenario 2: Filtros que bloquean las inyecciones

Algunas aplicaciones utilizan filtros que bloquean patrones habituales de inyección SQL. Esto puede impedir que sqlmap detecte una vulnerabilidad mediante sus pruebas iniciales.

Sin embargo, un pentester puede analizar el comportamiento del filtro y adaptar sus pruebas para comprobar si la vulnerabilidad sigue siendo explotable. Por eso, **que sqlmap no detecte una vulnerabilidad no significa necesariamente que esta no exista**.
