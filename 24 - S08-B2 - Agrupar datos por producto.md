---
tags: [python, aprendizaje, semana-8, bloque-2]
tipo: bloque
semana: 8
bloque: S08-B2
estado: validado
fecha: 2026-07-22
---

# S08-B2 - Agrupar datos por producto

## Objetivo

Transferir el patrón de agrupación por turno para acumular unidades producidas por producto.

## Conocimiento esencial

- La clave `registro["producto"]` reemplaza a `registro["turno"]` como criterio de agrupación.
- Dos registros con el mismo producto comparten el mismo acumulador aunque pertenezcan a turnos diferentes.
- `unidades_por_producto` debe crearse antes del `for` y una sola vez para no borrar los resultados parciales.
- Un producto nuevo se crea automáticamente mediante `if producto not in unidades_por_producto`.
- El `print` final fuera del `for` muestra el resumen completo una sola vez.

## Lo que construyó el estudiante

Reutilizó el agrupador dinámico por turno para crear `unidades_por_producto`. Hizo que Producto A apareciera en dos registros y obtuvo el total acumulado por producto.

## Evidencia

- Archivo: `practica_s08.py`
- Revisión: clave de producto, acumulador independiente, segundo recorrido y `print` fuera del ciclo.
- Ejecución: observada; produjo `{'Producto A': 220, 'Producto B': 80, 'Producto D': 90}`.
- Explicación: demostrada; explicó por qué Producto A suma `100 + 120` y cómo se crea un producto nuevo.
- Método de validación: revisión estática, ejecución real y transferencia del patrón de agrupación.

## Errores y correcciones

- El agrupamiento por producto quedó inicialmente dentro del recorrido que imprimía productos; se corrigió la indentación para calcularlo una sola vez.
- Se aclaró que Producto A se agrupa por su producto, no por sus turnos.

## Pendiente

Nada para este bloque.

## Conexiones

- [[23 - S08-B1 - Agrupar datos por turno]]
- [[07 - S04-B2 - Lista de registros]]
- [[09 - S04-B4 - Totales y promedios]]
- [[Python desde 0 - Índice]]
