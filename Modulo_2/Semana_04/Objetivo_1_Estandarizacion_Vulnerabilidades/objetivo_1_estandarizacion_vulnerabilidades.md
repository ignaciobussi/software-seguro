# Que es el CVE (Common Vulnerabilities and Exposures)?

El CVE se podria decir de una manera mas criolla que seria como un DNI, osea que es un **identificador unico** donde su estructura esta compuesta con el prefijo CVE, cuando se descubrio y un numero secuencial **(ejmplo: CVE-2026-XXXXX)**. Este **ID** permite que todos puedan referirse a ese mismo problema sin equivocarse. Los mismos registros de las vulnerabilidades tiene una descripcion del problema de seguridad y referencias a avisos oficiales, pero sin detallar como explotar la falla,

# Que es el CWE (Common Weakness Enumeration)?

El CWE no identifica una vulnerabilidad especifica sino que **clasifica que tipo de error o debilidad que existe** (ejemplo CWE-89 = SQL injection) refiriendose a la categoria que representa ese tipo de debilidad.

## Diferencias entre CVE y CWE

El CVE es la vulnerabilidad en concreto y el CWE es la categoria de la vulnerabilidad/tipo de debilidad.

# CNA (CVE Numbering Authority)

Son organizaciones autorizadas para asignar identificadores unicos (codigos CVE) a las vulnerabilidades, algunas de las organizaciones que pueden asignar dicho identificador son: Microsoft, Google, Apple, Cisco, entre otros.
Pueden buscarse en dos lugares **CVE.org** que es la pagina oficial del programa CVE y **NVD — National Vulnerability Database** que es una base de datos del **NIST** que permite consultar vulnerabilidades y proporciona información adicional sobre ellas.
Las herramientas que pueden utilizarse para poder analizar automaticamente un sistema y detectar vulnerabilidades conocidas pueden ser: **Nessus**: Es un escáner de vulnerabilidades. Analiza máquinas, servicios y software instalados y puede detectar vulnerabilidades conocidas, mostrando los CVE asociados. Tambien **OpenVAS**:También es un sistema de análisis de vulnerabilidades. Escanea sistemas y puede identificar vulnerabilidades conocidas y relacionarlas con sus identificadores CVE.
