---
tags: [python, aprendizaje, semana-10, bloque-4]
tipo: bloque
semana: 10
bloque: S10-B4
estado: pendiente-de-validacion
fecha: 2026-08-05
---

# S10-B4 - Probar rutas válidas e inválidas

## Objetivo

Encontrar al menos una entrada con la que el programa todavía revienta con traceback, en lugar de fallar de forma controlada.

## Estado

**Pendiente de validación.** La ejecución está completa y la hizo él; lo que falta es la explicación con sus palabras. Ver la sección «Lo que falta para validar».

## Conocimiento esencial

Las tres primeras ideas están comprobadas por ejecución. La cuarta la enunció él.

- Un programa recibe información por **tres vías distintas**, no solo una: qué archivo le pasas (la ruta), desde dónde lo ejecutas (el directorio del terminal) y qué lleva dentro el archivo. Las pruebas de S10-B1 y S10-B2 cubrían solo la primera. Las dos roturas encontradas hoy están en las otras dos.
- **`DictReader` solo crea las claves que vienen en la cabecera.** Un CSV al que le falta una columna se lee sin protestar y produce filas sin esa clave; el fallo aparece más tarde y lejos, al pedir `registro["producto"]`, como `KeyError: 'producto'`. El programa incluso llegó a imprimir `Registro válidos: 1` antes de morir: contó como válida una fila que no lo era.
- **Una ruta relativa no es un lugar, es una indicación desde donde estés parado.** Las tres escrituras a `salidas/...` están escritas a mano dentro del código y no se adaptan al directorio del terminal, a diferencia de la ruta de entrada, que la escribe el usuario. Ejecutar desde otra carpeta produce `FileNotFoundError` al escribir, no al leer. Y `open(..., "w")` crea el archivo si falta, pero **nunca crea la carpeta** que lo contiene.
- **No existe ningún código de salida para «al archivo le falta una columna».** Formulación suya: «no identificamos que falta una variable». Las dos roturas de hoy terminan con el `1` por defecto de Python —el que devuelve al morir con una excepción no atrapada—, que **choca** con `SALIDA_NO_EXISTE_ARCHIVO = 1` definido en S10-B3. Desde fuera, un archivo con la columna ausente y un archivo inexistente cuentan la misma mentira.

## Lo que construyó el estudiante

`analizador-produccion/datos/prueba_falta_columna.csv`: cabecera con siete columnas en lugar de ocho —falta `producto`— y una fila de datos. Es un CSV válido en forma y no lo es en contenido. Queda versionado como fixture: sirve tal cual para el paso previo a S11-B1.

No escribió código Python en este bloque. El objetivo era descubrir casos, no corregirlos.

## Evidencia

- Archivo probado: `analizador-produccion/analizador_produccion.py` sin modificar; entrada nueva `datos/prueba_falta_columna.csv`.
- Ejecución: observada, reportada por él desde su terminal.
  - Columna ausente: `Registro válidos: 1`, totales `100 5 95 8`, y después `KeyError: 'producto'` en la línea 46, dentro de `calcular_resumen_por_producto`. Código `1`.
  - Desde otro directorio, con la ruta de entrada correcta: lee bien el CSV (`440 28 412 34`) y luego `FileNotFoundError: [Errno 2] No such file or directory: 'salidas/resumen_por_producto.csv'` en la línea 125. Código `1`.
  - Restauración comprobada: desde `analizador-produccion/`, `datos/produccion.csv` vuelve a devolver `440 28 412 34` y código `0`. El tutor leyó los tres archivos de `salidas/` antes y después: quedaron reparados.
- Daño colateral verificado, no supuesto: tras el `KeyError`, `resumen_por_producto.csv` quedó **solo con la cabecera** —el modo `"w"` lo había vaciado antes de morir— mientras `resumen_por_turno.csv` y `resumen_general.csv` conservaban datos de la ejecución anterior. Los tres reportes dejaron de contar la misma historia sin que nada lo avisara.
- Explicación: **no demostrada.** Pidió explícitamente la explicación («explícame qué pasó aquí») y, después de recibirla, siguió diagnosticando el segundo fallo como «tenemos mal la ruta». Los dos diagnósticos son del tutor.
- Método de validación: ejecución observada en cuatro caminos y lectura directa de `salidas/` por el tutor.

## Lo que falta para validar

Que explique con sus palabras, **en frío y en un chat nuevo**, las dos roturas que encontró:

1. Por qué un CSV al que le falta una columna revienta en `calcular_resumen_por_producto` y no al abrir el archivo.
2. Por qué el mismo comando funciona desde `analizador-produccion/` y falla desde la carpeta de arriba.

Preguntárselo en esta misma sesión mediría la memoria de la conversación, no la comprensión.

## Errores y correcciones

- Primer intento del comando ejecutado en **cmd**, no en PowerShell. El `;` de PowerShell no es un separador en cmd, así que se pegó al nombre del archivo y el programa respondió con toda razón `No existe un archivo llamado: datos/prueba_falta_columna.csv;`, con el punto y coma dentro. Se detectó mirando el final del mensaje de error y el prompt, `C:\...>` en lugar de `PS C:\...>`. Es la tercera vez en la Semana 10 que el lanzador, y no el código, explica una salida rara.
- Al proponer casos que probar, los primeros tres que dio eran el mismo caso —la ruta— con distinta ropa, más «mal escrito el código», que no es una entrada sino un fallo propio. Hizo falta darle los tres ejes explícitamente.
- Confundió el eje del contenido con la salida del programa: entendió que el CSV de entrada podría sobrescribirse con los datos calculados. Se aclaró con el diagrama entrada → programa → salida y recordando que el archivo se abre en modo `"r"`.
- Atribuyó el `KeyError` a `DictWriter`. La pieza que reparte columnas a nombres al leer es `DictReader`.

## Pendiente

Arreglar las dos roturas **no** es de este bloque. Corresponde al paso previo a S11-B1, junto con las ocho reglas de validación de `PROYECTO.md` que faltan.

## Conexiones

- [[36 - S10-B3 - Codigos y mensajes de salida]]
- [[35 - S10-B2 - Validar que el archivo exista y sea legible]]
- [[Python desde 0 - Índice]]
