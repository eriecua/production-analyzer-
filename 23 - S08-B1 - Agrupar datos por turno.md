---
tags: [python, aprendizaje, semana-8, bloque-1]
tipo: bloque
semana: 8
bloque: S08-B1
estado: validado
fecha: 2026-07-22
---

# S08-B1 - Agrupar datos por turno

## Objetivo

Agrupar dinámicamente las unidades producidas de varios registros según el turno al que pertenecen.

## Conocimiento esencial

- La clave `turno` actúa como criterio de agrupación para decidir qué acumulador debe aumentar.
- `if turno not in unidades_por_turno` comprueba si el grupo todavía no existe.
- `unidades_por_turno[turno] = 0` crea un acumulador nuevo sin escribir previamente el nombre del turno.
- `unidades_por_turno[turno] += registro["unidades_producidas"]` suma solamente las unidades del registro actual al turno correspondiente.
- Los corchetes acceden por posición en una lista y por clave en un diccionario; una variable dentro de los corchetes aporta la clave actual.

## Lo que construyó el estudiante

Creó cuatro registros de producción y un agrupador dinámico que acumuló unidades para los turnos Mañana, Noche y Tarde. El turno Tarde fue reconocido sin añadirlo manualmente al diccionario acumulador.

## Evidencia

- Archivo: `practica_s08.py`
- Revisión: lista de cuatro diccionarios, clave de agrupación, creación dinámica de acumuladores y suma dentro del `for`.
- Ejecución: observada; produjo `{'Mañana': 220, 'Noche': 80, 'Tarde': 90}`.
- Explicación: demostrada.
- Método de validación: revisión estática, ejecución real, prueba con un turno nuevo y explicación paso a paso.

## Errores y correcciones

- La lista se llamó inicialmente `registro` y la clave usó espacios; se ajustaron a `registros` y `unidades_producidas` para conservar la estructura oficial del proyecto.
- Primero se escribieron los turnos manualmente en el acumulador; después se reemplazaron por un diccionario vacío y creación dinámica con `not in`.
- Se corrigió la idea de que Mañana sumaba los tres registros: únicamente acumula `100 + 120`; las `80` unidades pertenecen a Noche.

## Pendiente

Nada para este bloque.

## Conexiones

- [[07 - S04-B2 - Lista de registros]]
- [[08 - S04-B3 - Recorrer registros con for]]
- [[09 - S04-B4 - Totales y promedios]]
- [[Python desde 0 - Índice]]
