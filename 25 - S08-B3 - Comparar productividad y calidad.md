---
tags: [python, aprendizaje, semana-8, bloque-3]
tipo: bloque
semana: 8
bloque: S08-B3
estado: validado
fecha: 2026-07-23
---

# S08-B3 - Comparar productividad y calidad

## Objetivo

Calcular y comparar indicadores de productividad y calidad por producto y turno.

## Conocimiento esencial

- `unidades_buenas` se calcula restando las unidades defectuosas a las producidas.
- La productividad bruta usa `unidades_producidas / horas_trabajadas`.
- El rendimiento usa `unidades_buenas / unidades_producidas * 100`.
- La tasa de defectos usa `unidades_defectuosas / unidades_producidas * 100`.
- Un `if` dentro del `for` permite etiquetar cada registro según tenga defectos.
- Para un resumen por producto o turno, los datos se acumulan por separado (en diferentes diccionarios acumuladores) usando la misma clave (el nombre del turno o del producto).
- Al iterar sobre un diccionario de acumuladores para realizar cálculos o divisiones secundarias, se debe usar una variable temporal distinta al diccionario para no destruir el acumulador en la primera iteración.

## Lo que construyó el estudiante

Amplió el recorrido de los registros para acumular unidades, horas y unidades buenas por producto y por turno. Calculó la productividad y el rendimiento globales de cada producto, y la tasa de defectos de calidad agrupada por turno.

## Evidencia

- Archivo: `practica_s08.py`
- Revisión: fórmulas, acumuladores, indentación del `for`, lógica de división secundaria y control del ciclo.
- Ejecución: observada; el rendimiento de calidad global por turno produjo `Mañana 7.73 %`, `Noche 10.0 %` y `Tarde 2.14 %`.
- Explicación: demostrada; el estudiante analizó que el turno Tarde, aunque produce menos unidades por hora, tiene un desempeño superior en calidad al tener una menor tasa de defectos por turno (2.14%).
- Método de validación: revisión estática y ejecución real.

## Pendiente

Nada para este bloque.

## Conexiones

- [[23 - S08-B1 - Agrupar datos por turno]]
- [[24 - S08-B2 - Agrupar datos por producto]]
- [[Python desde 0 - Índice]]
