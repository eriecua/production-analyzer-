---
tags: [python, aprendizaje, practica-transferencia, calculadora]
tipo: practica-transferencia
estado: validado
fecha: 2026-07-22
---

# Práctica de transferencia - Calculadora validada

## Objetivo

Construir una calculadora interactiva que valide números, operadores y la decisión de continuar o terminar sin cerrar el programa ante entradas incorrectas.

## Conocimiento esencial

- `while True` permite repetir una solicitud hasta que el dato sea válido.
- `break` termina únicamente el ciclo más cercano en el que se encuentra.
- `continue` vuelve al comienzo del ciclo más cercano para solicitar nuevamente el dato.
- `.lower()` normaliza una respuesta a minúsculas; no valida por sí mismo.
- `if valor in [opciones]` comprueba si la respuesta pertenece al conjunto de opciones permitidas.

## Lo que construyó el estudiante

Una calculadora con validaciones independientes para el primer número, el segundo número, el operador y la respuesta `S/N`. El programa permite repetir cálculos con `s`, rechaza respuestas no válidas y termina solamente con `n`.

## Evidencia

- Archivo: `calculadora.py`
- Revisión: ciclos anidados, validación de operadores, control de división entre cero y decisión de continuar.
- Ejecución: observada.
- Explicación: demostrada durante la construcción y corrección del flujo.
- Método de validación: revisión estática y prueba completa de consola con una respuesta inválida, continuación con `s` y cierre con `n`.

## Errores y correcciones

- La respuesta `S/N` terminaba el programa ante cualquier entrada; se separó la validación de la decisión final.
- Se aclaró que una cadena vacía no es `None` y que `.lower()` transforma texto, pero no decide si es válido.
- Se comprobó que cada `break` afecta solamente al `while` más cercano.

## Pendiente

Esta práctica no valida S07-B3 ni aumenta por sí sola el progreso oficial de la Semana 7.

## Conexiones

- [[14 - S06-B1 - Excepciones concretas y ValueError]]
- [[18 - S07-B1 - Separar responsabilidades]]
- [[Python desde 0 - Índice]]
