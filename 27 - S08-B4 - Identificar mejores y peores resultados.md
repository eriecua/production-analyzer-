---
tags: [python, aprendizaje, semana-8, bloque-4]
tipo: bloque
semana: 8
bloque: S08-B4
estado: validado
fecha: 2026-07-25
---

# S08-B4 - Identificar mejores y peores resultados

## Objetivo

Identificar el mejor y el peor resultado agrupado, tanto por turno como por producto, a partir de los acumuladores ya construidos en bloques anteriores.

## Conocimiento esencial

- `max(diccionario, key=...)` y `min(diccionario, key=...)` recorren las claves del diccionario y usan la función pasada en `key` para decidir cuál es mayor o menor; el valor que devuelven siempre es la clave ganadora, no su valor asociado.
- `key` es un parámetro con nombre (keyword argument) de las funciones incorporadas `max`/`min`, no una palabra reservada del lenguaje; recibe una función que traduce cada clave a un valor comparable.
- `lambda parametro: expresión` crea una función anónima de una sola línea, útil cuando la función solo se necesita una vez y no amerita un `def` con nombre propio.
- Los corchetes (`diccionario[algo]`) son siempre un buscador: evalúan primero el contenido de `algo` y luego buscan una clave que coincida exactamente con ese contenido; no convierten ni transforman la variable usada como índice.
- Anotar el tipo de retorno de una función (`-> dict[str, int]`) permite que el verificador de tipos (Pylance) confirme que `.get()` o el indexado por clave son seguros de usar más adelante.

## Lo que construyó el estudiante

Usó `max()`/`min()` con `key=lambda` sobre `resultado_prueba` (defectos por turno) para identificar el turno con más y con menos defectos, y repitió el mismo patrón sobre `unidades_por_producto` para identificar el producto con mayor y menor producción. Corrigió un aviso de Pylance (`reportCallIssue`) anotando el tipo de retorno de `obtener_defectos_por_turno` y cambiando `.get` por indexado directo dentro del `lambda`.

## Evidencia

- Archivo: `practica_s08.py`
- Revisión: uso correcto de `max`/`min` con `key`, anotación de tipo de retorno, e indexado por clave en los `print` finales.
- Ejecución: observada; salida real: `Turno con más defectos es de Mañana con 17 defectos/turno`, `Turno con menos defectos es de Tarde con 3 defectos/turno`, `La mayor produccion por producto es Producto A con 220 unidades`.
- Explicación: demostrada; el estudiante explicó con sus propias palabras qué es `lambda`, para qué sirve `key`, la diferencia entre palabra reservada y función incorporada, y por qué los corchetes son un buscador y no un conversor (incluyendo una prueba propia con una clave inexistente que produjo `KeyError` y otra con clave existente que sí funcionó).
- Método de validación: revisión estática, ejecución real y explicación conceptual verificada con preguntas de seguimiento.

## Pendiente

Nada para este bloque.

## Conexiones

- [[25 - S08-B3 - Comparar productividad y calidad]]
- [[26 - Practica adicional - Funciones y cumplimiento por producto]]
- [[Python desde 0 - Índice]]
