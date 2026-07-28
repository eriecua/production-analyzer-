---
tags: [python, aprendizaje, semana-7, bloque-4]
tipo: bloque
semana: 7
bloque: S07-B4
estado: validado
fecha: 2026-07-22
---

# S07-B4 - Documentar funciones importantes

## Objetivo

Documentar las funciones importantes para que otra persona pueda comprender su propósito, sus entradas y el resultado esperado.

## Conocimiento esencial

- Una *docstring* se coloca inmediatamente debajo del `def` y dentro del bloque de la función.
- La *docstring* explica qué hace la función y para qué sirve.
- Una anotación como `-> str` indica el tipo de dato esperado como retorno; no explica por sí sola el propósito de la función.
- `help(funcion)` muestra la firma, las anotaciones y la *docstring* sin ejecutar la función.
- La documentación debe describir el comportamiento real y no afirmar que se devuelve un booleano cuando se devuelve texto.

## Lo que construyó el estudiante

Documentó `clasificar_registro` y `calcular_unidades_buenas`. Después utilizó `help()` para inspeccionar la firma, las anotaciones y la documentación de ambas funciones.

## Evidencia

- Archivo: `practica_s07.py`
- Revisión: dos *docstrings* dentro de sus funciones, anotaciones coherentes y dos llamadas de demostración a `help()`.
- Ejecución: observada.
- Explicación: demostrada.
- Método de validación: revisión estática, ejecución completa y lectura de la salida de `help()`.

## Errores y correcciones

- La primera descripción afirmaba que la función comparaba booleanos; se corrigió para explicar que compara unidades y devuelve `Aceptado` o `Rechazado`.
- La prueba con decimales generaba dos advertencias de Pylance; se comentó después de demostrar que las anotaciones no validan durante la ejecución.

## Pendiente

Nada para este bloque.

## Conexiones

- [[18 - S07-B1 - Separar responsabilidades]]
- [[19 - S07-B2 - Nombres y responsabilidades]]
- [[21 - S07-B3 - Constantes y anotaciones de tipo]]
- [[Python desde 0 - Índice]]
