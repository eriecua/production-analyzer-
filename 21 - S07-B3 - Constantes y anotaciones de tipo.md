---
tags: [python, aprendizaje, semana-7, bloque-3]
tipo: bloque
semana: 7
bloque: S07-B3
estado: validado
fecha: 2026-07-22
---

# S07-B3 - Constantes y anotaciones de tipo

## Objetivo

Usar constantes y anotaciones de tipo para comunicar con claridad los valores reutilizables, los datos que reciben las funciones y el resultado que devuelven.

## Conocimiento esencial

- Una constante se escribe por convención con mayúsculas y representa un valor que no debería cambiar durante la ejecución.
- `parametro: int` anota el tipo esperado para un parámetro.
- `-> int` o `-> str` anota el tipo que se espera devolver mediante `return`.
- Las anotaciones documentan el código, pero no convierten ni validan automáticamente los valores.
- Una operación entre valores `float` devuelve un `float`, aunque la función esté anotada con `int`.

## Lo que construyó el estudiante

Clasificó registros usando las constantes `ESTADO_ACEPTADO` y `ESTADO_RECHAZADO`. También anotó `clasificar_registro` con parámetros `int` y retorno `str`, y `calcular_unidades_buenas` con parámetros y retorno `int`.

## Evidencia

- Archivo: `practica_s07.py`
- Revisión: constantes reutilizadas, dos funciones anotadas y responsabilidades conservadas.
- Ejecución: observada.
- Explicación: demostrada.
- Método de validación: revisión estática, ejecución del archivo y prueba deliberada con dos valores decimales.

## Errores y correcciones

- Inicialmente faltaba la anotación del retorno; se identificó que `-> int` describe lo que sale de la función.
- Se aclaró que los valores decimales no fueron convertidos por la anotación: ya eran `float` y Python realizó la resta con ellos.

## Pendiente

Los módulos no forman parte de la evidencia de este bloque porque todavía no fueron practicados.

## Conexiones

- [[18 - S07-B1 - Separar responsabilidades]]
- [[19 - S07-B2 - Nombres y responsabilidades]]
- [[Python desde 0 - Índice]]
