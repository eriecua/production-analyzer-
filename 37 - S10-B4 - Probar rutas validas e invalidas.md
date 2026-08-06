---
tags: [python, aprendizaje, semana-10, bloque-4]
tipo: bloque
semana: 10
bloque: S10-B4
estado: validado
fecha: 2026-08-05
fecha_validacion: 2026-08-06
---

# S10-B4 - Probar rutas válidas e inválidas

## Objetivo

Encontrar al menos una entrada con la que el programa todavía revienta con traceback, en lugar de fallar de forma controlada.

## Estado

**Validado el 2026-08-06.** La parte ejecutable se cerró el 2026-08-05. La explicación que faltaba —la de la ruta relativa— se midió al día siguiente con un experimento nuevo, no repitiendo la pregunta. Ver «Cómo se validó la segunda rotura».

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
- Explicación: **demostrada, las dos roturas.**
  - **Primera rotura, el `KeyError`: demostrada** el 2026-08-05, en la misma sesión. Tras tres intentos llegó con analogía propia — «yo llamo a un auxiliar a buscar un archivo que otra persona debió entregar; al no encontrarlo me señala que no está» — y cerró con la distinción correcta cuando se le contrastó clave inexistente contra clave vacía: «no existe producto, ni el contenido de él». La analogía es suya y captura lo esencial: el hueco existía desde el principio y nadie se enteró hasta que alguien fue a pedirlo.
  - **Segunda rotura, la ruta relativa: demostrada** el 2026-08-06, con un caso nuevo. Ese día sus dos primeros intentos habían apuntado a navegar entre carpetas y a «algo escribí en la terminal, no me fijé»; la explicación de entonces era del tutor.
- Método de validación: ejecución observada en cuatro caminos y lectura directa de `salidas/` por el tutor.

## Cómo se validó la segunda rotura

La sesión del 2026-08-05 quedó comprometida para medir esto: la explicación ya se había dado en voz alta. Preguntar lo mismo al día siguiente habría medido memoria. Se sustituyó por un **caso nuevo que nunca se había visto**, diseñado para que la respuesta no pudiera recordarse:

```powershell
cd "C:\Users\MSI ERICK\Documents\Python desde 0"
mkdir salidas
python analizador-produccion\analizador_produccion.py analizador-produccion\datos\produccion.csv; $LASTEXITCODE
dir salidas
```

El caso discrimina las dos hipótesis sin ambigüedad: si la ruta se completa con la carpeta del `.py`, los reportes aparecen en `analizador-produccion\salidas\`; si se completa con la del terminal, aparecen en la carpeta nueva de arriba. Son sitios distintos.

Secuencia real de la medición:

1. Se le preguntó qué carpeta usa Windows para completar `"salidas/..."`. Eligió **la del archivo `.py`**. Respuesta incorrecta y muy común.
2. Se le puso delante la tabla de sus dos ejecuciones del día anterior: el `.py` no se había movido, solo el terminal, y el resultado cambió. Es un experimento controlado y él ya tenía los datos.
3. Propuso entonces una hipótesis propia: que funciona «dado que dentro del directorio ya existe la carpeta salidas». Es correcta en su mitad y comprobable, así que se ejecutó.
4. Resultado observado por él: los tres reportes aparecieron en `C:\Users\MSI ERICK\Documents\Python desde 0\salidas\`, con código de salida `0`.
5. Conclusión suya, sin ayuda: **«la que yo indiqué en el terminal. Le dije abre hasta aquí y crea esto y luego ejecuta esto.»**
6. Cierre sobre la asimetría entrada/salida: identificó que la ruta de entrada la adapta él porque pasa por sus manos en cada ejecución.

Vale más que la respuesta pedida: cambió de hipótesis ante la evidencia en lugar de defender la primera.

Hallazgo del experimento, digno de registro: **con la carpeta creada, el programa no falla — escribe los reportes en el sitio equivocado y devuelve `0`.** Un fallo silencioso es peor que el `FileNotFoundError` original, que al menos gritaba.

Antes de ese paso hubo dos respuestas que describían el flujo general —«lee de `datos` y escribe en `salidas`»— sin responder *cuál* `salidas`. Se rechazaron señalando el hueco exacto en lugar de aceptarlas.

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
- [[38 - Paso previo a S11-B1 - Validar la cabecera del CSV]]
- [[Python desde 0 - Índice]]
