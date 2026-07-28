---
tags: [python, aprendizaje, semana-5, bloque-4, csv, int, float]
tipo: bloque
semana: 5
bloque: S05-B4
estado: validado
fecha: 2026-07-17
---

# S05-B4 - Convertir filas a tipos correctos

## Objetivo

Convertir los valores numéricos leídos como texto para utilizarlos en cálculos de producción.

## Conocimiento esencial

- `DictReader` entrega inicialmente los valores del CSV como texto.
- `int()` convierte identificadores y cantidades enteras.
- `float()` convierte horas que pueden contener decimales.
- `fila["clave"]` obtiene el valor antes de convertirlo y guardarlo en una variable.
- Las conversiones permiten calcular unidades buenas con unidades producidas menos defectuosas.

## Lo que construyó el estudiante

Convirtió `id_registro`, meta, unidades producidas, defectos y horas; calculó `816` y `780` unidades buenas.

## Evidencia

- Archivo: `practica_s05.py`
- Revisión: conversiones con `int()` y `float()` dentro del recorrido.
- Ejecución: observada; Producto A produjo `816` unidades buenas y Producto B `780`.
- Explicación: demostró el orden búsqueda por clave, conversión, asignación y operación.
- Método de validación: revisión estática, ejecución y explicación propia.

## Pendiente

Nada para este bloque.

## Conexiones

- [[12 - S05-B3 - Leer CSV con DictReader]]
- [[09 - S04-B4 - Totales y promedios]]
- [[Python desde 0 - Índice]]
