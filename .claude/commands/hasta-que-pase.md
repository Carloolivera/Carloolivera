---
description: Itera sobre el último cambio hasta que la verificación pase, siguiendo el protocolo loop-verificacion
---

Aplicá el protocolo de la skill `loop-verificacion` al trabajo actual.

Criterio de éxito: $ARGUMENTS

Si no pasé criterio como argumento, deducí el criterio objetivo del contexto
(tests del proyecto, build, o el flujo que se estaba tocando) y decláralo
antes de la primera iteración.

Reglas: leé el error real en cada iteración, una hipótesis por fix, re-ejecutá
la verificación completa antes de declarar éxito, y si dos intentos no mueven
el error frená y re-diagnosticá desde cero. Al terminar, abrí el reporte con
el resultado y la salida de la verificación final.
