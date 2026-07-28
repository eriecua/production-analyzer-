---
tags: [python, aprendizaje, semana-9, bloque-3]
tipo: bloque
semana: 9
bloque: S09-B3
estado: validado
fecha: 2026-07-26
---

# S09-B3 - Exportar resultados por producto

## Objetivo

Transferir el patrón de exportación CSV a la agrupación por producto, generando `resumen_por_producto.csv`.

## Conocimiento esencial

- El patrón completo de exportación (acumular, construir lista de filas, escribir con `DictWriter`) es reutilizable: solo cambian la clave de agrupación, los `fieldnames` y el nombre del archivo.
- Recorrer un diccionario con `for clave in diccionario` itera únicamente sobre sus claves; si dos acumuladores se llenaron en el mismo recorrido comparten las mismas claves y da igual cuál se use como fuente del bucle.
- Al construir un diccionario con `{clave: valor}` no se usan corchetes: la clave literal va entre comillas y el valor es la variable que aporta el contenido; los corchetes solo aparecen al acceder a un diccionario ya existente.

## Lo que construyó el estudiante

Creó los acumuladores `unidades_por_producto` y `defectos_por_producto`, armó `filas_por_producto` con las columnas `producto`, `unidades_producidas` y `unidades_defectuosas`, y exportó el resultado a `resumen_por_producto.csv`.

## Evidencia

- Archivo: `practica_s09.py`; salida: `resumen_por_producto.csv`
- Revisión: acumuladores por producto, construcción de filas y bloque de escritura con la indentación correcta desde el primer intento.
- Ejecución: observada; el CSV contiene `Producto A,220,17`, `Producto B,80,8`, `Producto D,90,3` y `Producto C,50,0`.
- Comprobación manual: prevista antes de ejecutar (A = 220/17, B = 80/8, D = 90/3, C = 50/0) y coincidente con la salida real.
- Explicación: demostrada; el estudiante preguntó y comprendió por qué cualquiera de los dos acumuladores sirve como fuente del `for`, al compartir las mismas claves.
- Método de validación: revisión estática, ejecución real, lectura del CSV y verificación manual previa.

## Pendiente

Nada para este bloque.

## Conexiones

- [[29 - S09-B2 - Exportar resultados por turno]]
- [[24 - S08-B2 - Agrupar datos por producto]]
- [[Python desde 0 - Índice]]
