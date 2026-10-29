# Diferencia entre Boolean-Based y Time-Based Blind SQLi

La diferencia es que **Boolean-Based utiliza condiciones verdaderas o falsas y observa los cambios en las respuestas de la aplicación**. En cambio, **Time-Based se basa en el tiempo de respuesta**: si se cumple una condición, se provoca un retraso; si no se cumple, la respuesta debería tardar lo habitual.

# ¿Cómo logra un atacante extraer el nombre de una base de datos letra por letra cuando la aplicación solo responde con una pantalla genérica de "Cargando..."?

El atacante puede realizar pruebas para comprobar qué letra ocupa cada posición del nombre de la base de datos. Para ello, utiliza condiciones verdaderas o falsas y observa los cambios en las respuestas (**Boolean-Based**) o compara los tiempos de respuesta (**Time-Based**). Repitiendo este proceso, **puede reconstruir el nombre letra por letra**, aunque la aplicación solo muestre una pantalla genérica de «Cargando...».
