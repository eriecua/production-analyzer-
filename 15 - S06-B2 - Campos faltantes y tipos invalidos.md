---
tags: [python, aprendizaje, semana-6, bloque-2]
tipo: bloque
semana: 6
bloque: S06-B2
estado: validado
fecha: 2026-07-19
---

# S06-B2 - Campos faltantes y tipos inválidos

## Objetivo

Detectar un campo vacío antes de convertirlo y distinguirlo de un texto con formato numérico inválido.

## Conocimiento esencial

- `valor_csv == ""` comprueba si una variable contiene texto vacío.
- `""` no es lo mismo que `None`: el primero es texto sin caracteres y el segundo representa ausencia de valor.
- `if` permite separar el caso sin dato del caso que sí debe procesarse.
- La conversión con `int()` debe ejecutarse dentro de `try` cuando el contenido puede ser inválido.
- `except ValueError` muestra un mensaje claro cuando hay texto, pero no representa un número entero.

## Lo que construyó el estudiante

Un flujo que comprueba `valor_csv`, informa si falta el dato y, cuando hay contenido, intenta convertirlo y captura `ValueError`.

## Evidencia

- Archivo: `practica_s06.py`
- Revisión: se inspeccionó el archivo guardado.
- Ejecución: observada con campo vacío (mensaje de falta de dato), valor válido `80` (salida `80`) y texto inválido `ochocientos` (mensaje del `except`).
- Explicación: demostrada; distinguió texto vacío, valor válido y texto no convertible.
- Método de validación: revisión estática, ejecución desde PowerShell y explicación del estudiante.

## Errores y correcciones

- La conversión se ejecutaba aunque el campo estuviera vacío; se colocó el bloque `try` dentro de `else`.
- Se corrigió la errata `ochosientos` a `ochocientos`.

## Pendiente

Nada para este bloque.

## Conexiones

- [[14 - S06-B1 - Excepciones concretas y ValueError]]
- [[Python desde 0 - Índice]]
