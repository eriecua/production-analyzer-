---
tags: [python, aprendizaje, semana-6, bloque-4]
tipo: bloque
semana: 6
bloque: S06-B4
estado: validado
fecha: 2026-07-19
---

# S06-B4 - Resumen de filas aceptadas y rechazadas

## Objetivo

Contar registros aceptados y rechazados a partir del resultado de una función de validación.

## Conocimiento esencial

- Un acumulador empieza en cero y conserva lo contado entre registros.
- La función `clasificar_registro` devuelve una etiqueta: `"Aceptado"` o `"Rechazado"`.
- El código principal interpreta esa etiqueta con `if`.
- Cada resultado aceptado aumenta `aceptados`; cada resultado rechazado aumenta `rechazados`.
- Repetir manualmente el patrón funciona, pero un `for` permitirá recorrer muchos registros después.

## Lo que construyó el estudiante

Un resumen que procesa cuatro resultados de `clasificar_registro` y acumula dos aceptados y dos rechazados.

## Evidencia

- Archivo: `practica_s06.py`
- Revisión: se inspeccionó el archivo guardado.
- Ejecución: observada; salida `Aceptados por función: 2` y `Rechazados por función: 2`.
- Explicación: demostrada; explicó la separación entre función clasificadora, decisión y acumuladores, y razonó cuántas vueltas daría un `for` sobre cuatro registros.
- Método de validación: revisión estática, ejecución desde PowerShell y explicación del estudiante.

## Errores y correcciones

Nada relevante para este bloque.

## Pendiente

Nada para este bloque.

## Conexiones

- [[16 - S06-B3 - Duplicados e inconsistencias]]
- [[Python desde 0 - Índice]]
