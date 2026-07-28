---
tags: [python, funciones, kpi, semana-3, bloque-2]
tipo: bloque
semana: 3
bloque: S03-B2
estado: validado
fecha: 2026-07-16
---

# S03-B2 - Crear funciones para cada KPI

## Objetivo

Crear una función independiente para calcular un KPI y devolver su resultado sin mezclarla con la presentación en consola.

## Conocimiento esencial

- Cada KPI puede tener su propia función y una responsabilidad concreta.
- Los datos que necesita el cálculo entran mediante parámetros.
- `return` entrega el resultado al código que llamó la función.
- El cumplimiento puede representarse como una proporción decimal: `unidades_producidas / meta_unidades`.
- El valor devuelto se puede guardar en una variable y usar después.

## Lo que construyó el estudiante

En `practica_s03.py` creó `calcular_cumplimiento(unidades_producidas, meta_unidades)` y conservó la función anterior `calcular_unidades_buenas(...)`. La nueva función devuelve el cociente entre unidades producidas y meta.

## Evidencia

- Archivo: `C:\Users\MSI ERICK\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\practica_s03.py`
- Revisión: se leyó el archivo realmente guardado y se comprobó la definición, llamada y uso del valor devuelto.
- Ejecución: no observada en esta sesión.
- Explicación: el uso de parámetros y `return` ya fue explicado por el estudiante en el bloque anterior; la comprensión completa de todos los KPI aún se seguirá practicando.
- Método de validación: revisión estática del código guardado contra el objetivo observable de S03-B2.

## Error y corrección

En un primer intento el cálculo devolvía el porcentaje multiplicado por `100`. Se corrigió para devolver la proporción decimal acordada para este proyecto.

## Alcance de la validación

S03-B2 queda validado porque se demostró la separación de un segundo KPI en una función propia. Esto no significa que todos los KPI finales del analizador ya estén implementados; se construirán progresivamente.

## Pendiente

- Observar una ejecución real desde la terminal en un bloque posterior.
- Añadir y validar los KPI restantes conforme avance el proyecto.

## Conexiones

- [[01 - Funciones - def y return]]
- [[02 - S03-B1 - Parametros, argumentos y variables externas]]
- [[Python desde 0 - Índice]]

