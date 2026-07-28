---
tags: [python, aprendizaje, semana-9, bloque-2]
tipo: bloque
semana: 9
bloque: S09-B2
estado: validado
fecha: 2026-07-26
---

# S09-B2 - Exportar resultados por turno

## Objetivo

Escribir en un archivo CSV los resultados agrupados por turno, generando `resumen_por_turno.csv`.

## Conocimiento esencial

- `csv.DictWriter(archivo, fieldnames=[...])` escribe diccionarios como filas CSV; los `fieldnames` deben coincidir exactamente con las claves de cada diccionario y definen el orden de las columnas.
- `with open(ruta, "w", newline="", encoding="utf-8") as archivo:` abre el archivo y garantiza su cierre automático al salir del bloque, incluso si ocurre un error; sin `with` habría que llamar a `archivo.close()` manualmente.
- El modo `"w"` borra el contenido previo y escribe desde cero; `newline=""` evita que Windows inserte líneas en blanco entre filas.
- `lista = []` crea una lista vacía; `lista.append(elemento)` agrega al final. A diferencia de `diccionario[clave] = valor`, no requiere indicar una posición o etiqueta.
- La indentación expresa dependencia: lo que se ejecuta una sola vez va directo en el `with`, y lo que se repite por cada dato va dentro de un `for` anidado. Colocar el `with` dentro del bucle de construcción reabre y reescribe el archivo en cada vuelta.

## Lo que construyó el estudiante

Recreó los acumuladores `unidades_por_turno` y `horas_por_turno` en el nuevo archivo, combinó ambos en una lista de diccionarios `filas_por_turno` mediante `.append()`, y la exportó a `resumen_por_turno.csv` con `csv.DictWriter`.

## Evidencia

- Archivo: `practica_s09.py`; salida: `resumen_por_turno.csv`
- Revisión: sintaxis de `open`, uso de `fieldnames`, construcción de la lista de filas e indentación del bloque de escritura.
- Ejecución: observada; el CSV generado contiene `turno,unidades_producidas,horas_trabajadas` seguido de `Mañana,220,16`, `Noche,80,7` y `Tarde,140,11`.
- Comprobación manual: Mañana 100+120=220 unidades y 8+8=16 horas; Noche 80 y 7; Tarde 90+50=140 y 6+5=11.
- Explicación: demostrada; el estudiante explicó que sin `with` tendría que cerrar el archivo con `.close()`.
- Método de validación: revisión estática, ejecución real, lectura del CSV generado y verificación aritmética manual.

## Errores y correcciones

- Error de sintaxis inicial en `with open("resumen_por_turno.csv"), "w", ... as a archivo:`: paréntesis de `open` cerrado antes de los demás argumentos y una palabra sobrante tras `as`. Corregido a `with open("resumen_por_turno.csv", "w", newline="", encoding="utf-8") as archivo:`.
- El bloque `with` quedó indentado dentro del `for` que construía las filas, reabriendo y reescribiendo el archivo en cada vuelta. El resultado final era correcto porque el modo `"w"` reescribe todo cada vez, pero se corrigió sacándolo del bucle para escribir una sola vez.
- En el acumulador de horas se sumaba a `unidades_por_turno` en lugar de `horas_por_turno`, lo que dejaba las horas en cero y contaminaba las unidades ya calculadas. Corregido.

## Pendiente

- El estudiante señaló que la sintaxis de `with open` y `csv.DictWriter` aún no está memorizada y requiere repaso adicional en próximas sesiones.

## Conexiones

- [[12 - S05-B3 - Leer CSV con DictReader]]
- [[28 - S09-B1 - Disenar el resumen general]]
- [[Python desde 0 - Índice]]
