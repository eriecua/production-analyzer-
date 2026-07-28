---
tags: [python, aprendizaje, semana-5, bloque-3, csv, dictreader, for]
tipo: bloque
semana: 5
bloque: S05-B3
estado: validado
fecha: 2026-07-17
---

# S05-B3 - Leer CSV con DictReader

## Objetivo

Leer las filas del CSV como diccionarios y acceder a sus valores mediante claves.

## Conocimiento esencial

- `csv.DictReader(archivo)` usa los encabezados para formar diccionarios.
- El lector entrega una fila por vez; no necesita almacenar todas simultáneamente.
- `for fila in lector` asigna temporalmente cada diccionario a `fila`.
- `fila["producto"]` busca el valor relacionado con la clave `producto`.

## Lo que construyó el estudiante

Recorrió las dos filas del CSV y mostró `Producto A`, `850`, `Producto B` y `800` sin escribir esos registros en el código.

## Evidencia

- Archivo: `practica_s05.py`
- Revisión: importación de `csv`, `DictReader`, `for` y acceso por claves.
- Ejecución: observada con las dos filas del archivo.
- Explicación: demostró cómo el lector entrega diccionarios y cómo cambia `fila` en cada vuelta.
- Método de validación: revisión estática, salida de consola y explicación propia.

## Pendiente

Nada para este bloque.

## Conexiones

- [[11 - S05-B2 - CSV de ejemplo]]
- [[08 - S04-B3 - Recorrer registros con for]]
- [[Python desde 0 - Índice]]
