---
tags: [python, aprendizaje, semana-9, bloque-4]
tipo: bloque
semana: 9
bloque: S09-B4
estado: validado
fecha: 2026-07-26
---

# S09-B4 - Mostrar un resumen legible en consola

## Objetivo

Presentar los resultados generales, por turno y por producto como tablas alineadas y legibles, en lugar de diccionarios crudos.

## Conocimiento esencial

- Dentro de una f-string, `{valor:<12}` alinea a la izquierda, `{valor:>12}` a la derecha y `{valor:^12}` al centro, ocupando el ancho indicado.
- Para que una tabla quede alineada, la línea de encabezado y las líneas de datos deben usar exactamente los mismos anchos y las mismas alineaciones en cada columna.
- Convención de lectura: el texto se alinea a la izquierda y los números a la derecha, de modo que unidades, decenas y centenas queden justificadas.
- Al recorrer una lista de diccionarios, la variable del `for` es un diccionario completo en cada vuelta, y sus datos se extraen con corchetes (`fila["turno"]`); dentro de una f-string delimitada por comillas dobles se usan comillas simples para la clave.

## Lo que construyó el estudiante

Añadió tres secciones de salida en consola: un resumen general con los totales, una tabla por turno y una tabla por producto, todas con títulos centrados y columnas alineadas. Comentó los `print` de diccionarios crudos que quedaban de bloques anteriores.

## Evidencia

- Archivo: `practica_s09.py`
- Revisión: uso de especificadores de formato en encabezados y filas, y consistencia de anchos entre ambas líneas.
- Ejecución: observada; salida real con las tres tablas alineadas, incluyendo `Mañana 220 16`, `Noche 80 7`, `Tarde 140 11` y las cuatro filas de producto.
- Explicación: parcialmente demostrada; el estudiante aplicó correctamente la regla de anchos consistentes tras una corrección, pero la teoría de `with open` y `DictWriter` fue expuesta por el tutor más que reconstruida por el estudiante.
- Método de validación: revisión estática y ejecución real.

## Errores y correcciones

La primera versión usaba anchos distintos entre el encabezado (`<18`, `<18`, `<24`) y las filas de datos (`<16`, `>10`, `>14`), lo que desalineaba las columnas. Se corrigió unificando anchos y alineaciones en ambas líneas de cada tabla.

## Pendiente

- Repasar la sintaxis de `with open` y `csv.DictWriter` hasta poder reconstruirla sin consultar el archivo, según lo señaló el propio estudiante.

## Conexiones

- [[28 - S09-B1 - Disenar el resumen general]]
- [[30 - S09-B3 - Exportar resultados por producto]]
- [[Python desde 0 - Índice]]
