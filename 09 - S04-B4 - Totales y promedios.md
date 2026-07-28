---
tags: [python, aprendizaje, semana-4, bloque-4, acumuladores, promedios]
tipo: bloque
semana: 4
bloque: S04-B4
estado: validado
fecha: 2026-07-17
---

# S04-B4 - Acumular totales y promedios

## Objetivo

Acumular unidades de todos los registros y calcular un promedio para el resumen del analizador.

## Conocimiento esencial

- Un acumulador comienza en `0` y conserva el total entre vueltas del `for`.
- Cada métrica necesita su propio acumulador: `total_unidades` y `total_defectuosas` no se mezclan.
- `len(registros)` cuenta los elementos de la lista; aquí cuenta los diccionarios de producción.
- El promedio se calcula después del recorrido: total dividido entre cantidad de registros.
- La indentación determina si una instrucción se repite dentro del `for` o se ejecuta una sola vez después.

## Lo que construyó el estudiante

Recorrió los registros, acumuló unidades producidas y defectuosas y calculó el promedio de unidades producidas.

## Evidencia

- Archivo: `practica_s04.py`
- Revisión: acumuladores antes del `for`, sumas dentro y promedio fuera del ciclo.
- Ejecución: observada; total producido `1650`, total defectuoso `54` y promedio `825.0`.
- Explicación: comprendió el acumulador, `len()` y la ubicación correcta del promedio.
- Método de validación: revisión estática, ejecución y explicación propia.

## Errores y correcciones

- El promedio estuvo inicialmente dentro del `for`; se corrigió la indentación para calcularlo una sola vez después del recorrido.

## Pendiente

Nada para este bloque.

## Conexiones

- [[08 - S04-B3 - Recorrer registros con for]]
- [[07 - S04-B2 - Lista de registros]]
- [[Python desde 0 - Índice]]
