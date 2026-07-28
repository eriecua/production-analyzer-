---
tags: [python, aprendizaje, semana-6, bloque-1]
tipo: bloque
semana: 6
bloque: S06-B1
estado: validado
fecha: 2026-07-18
---

# S06-B1 - Excepciones concretas y ValueError

## Objetivo

Comprender qué ocurre cuando una conversión de texto a número falla y capturar específicamente `ValueError`.

## Conocimiento esencial

- Los valores leídos desde un CSV llegan inicialmente como texto.
- `int("850")` convierte una cadena numérica en el entero `850`.
- `int("ochocientos")` no puede convertir letras a un entero y produce `ValueError`.
- `try` intenta ejecutar un bloque; `except ValueError` responde cuando aparece ese error concreto.
- La conversión debe estar dentro de `try`; si está fuera, el programa se detiene antes de llegar a `except`.

## Lo que construyó el estudiante

Un ejemplo que recibe `valor_csv`, intenta convertirlo con `int()` y muestra el resultado válido o un mensaje comprensible para un valor inválido.

## Evidencia

- Archivo: `practica_s06.py`
- Revisión: se inspeccionó el archivo guardado.
- Ejecución: observada con `valor_csv = "ochocientos"` (mensaje del `except`) y con `valor_csv = "850"` (salida `850`).
- Explicación: demostrada; explicó la diferencia entre texto numérico y texto con letras y el papel de `try/except`.
- Método de validación: revisión estática, ejecución desde PowerShell y explicación del estudiante.

## Errores y correcciones

- `except: ValueError:` produjo `SyntaxError`; se corrigió a `except ValueError:`.
- Una conversión colocada fuera de `try` produjo `ValueError` antes de alcanzar `except`; se movió la conversión dentro del bloque protegido.

## Pendiente

Nada para este bloque.

## Conexiones

- [[13 - S05-B4 - Convertir filas a tipos correctos]]
- [[Python desde 0 - Índice]]
