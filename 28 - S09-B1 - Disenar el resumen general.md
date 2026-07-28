---
tags: [python, aprendizaje, semana-9, bloque-1]
tipo: bloque
semana: 9
bloque: S09-B1
estado: validado
fecha: 2026-07-26
---

# S09-B1 - Diseñar el resumen general

## Objetivo

Acumular los totales generales de todos los registros, sin agrupar por turno ni por producto.

## Conocimiento esencial

- Un resumen general usa acumuladores simples (`total = 0` antes del bucle, `total += valor` dentro), sin diccionarios ni claves.
- El patrón `if clave not in diccionario` solo es necesario cuando las etiquetas se descubren dinámicamente durante el recorrido; si el número de acumuladores es fijo y conocido de antemano, el espacio ya existe desde su inicialización y no hay nada que comprobar.
- Comparar un número contra un diccionario con `in` evalúa contra sus claves, no contra sus valores; si las claves son texto, la condición resulta siempre verdadera y el `if` no filtra nada.

## Lo que construyó el estudiante

Creó `practica_s09.py` reutilizando los cinco registros de la Semana 8 y acumuló `total_producido`, `total_defectuoso` y `total_horas` con un único `for` sin condicionales.

## Evidencia

- Archivo: `practica_s09.py`
- Revisión: inicialización de acumuladores antes del bucle y suma directa dentro del `for`.
- Ejecución: observada; salida real `El total producido fue 440 unidades producidas, el total de defectos fue 28 defectos, y el total de horas trabajadas fue 34 horas`.
- Comprobación manual: 100+80+120+90+50 = 440; 5+8+12+3+0 = 28; 8+7+8+6+5 = 34.
- Explicación: demostrada; el estudiante explicó que el espacio ya estaba creado con las variables en cero antes del `for`, por lo que no había nada que condicionar.
- Método de validación: revisión estática, ejecución real y verificación aritmética manual.

## Errores y correcciones

Primera versión incluía `if total_producido not in registro:` antes de cada suma. La condición comparaba un número contra las claves de texto del registro, por lo que siempre era verdadera y el `if` no filtraba nada; el resultado era correcto por casualidad, no por lógica. Se corrigió eliminando los tres condicionales.

## Pendiente

Nada para este bloque.

## Conexiones

- [[09 - S04-B4 - Totales y promedios]]
- [[Python desde 0 - Índice]]
