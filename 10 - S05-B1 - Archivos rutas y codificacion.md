---
tags: [python, aprendizaje, semana-5, bloque-1, archivos, rutas, utf-8]
tipo: bloque
semana: 5
bloque: S05-B1
estado: validado
fecha: 2026-07-17
---

# S05-B1 - Archivos, rutas y codificación

## Objetivo

Comprender cómo Python localiza, abre, usa y cierra un archivo CSV con codificación UTF-8.

## Conocimiento esencial

- Una ruta absoluta indica la ubicación completa; una relativa parte de la carpeta actual.
- `open()` abre el archivo y `with` administra su cierre automático.
- `as archivo` asigna un nombre temporal al recurso abierto.
- `encoding="utf-8"` permite leer correctamente caracteres del español.

## Lo que construyó el estudiante

Abrió `produccion_ejemplo.csv` desde `practica_s05.py` usando una ruta relativa y verificó la salida `Archivo abierto`.

## Evidencia

- Archivo: `practica_s05.py`
- Revisión: estructura `with open(...) as archivo` y ruta del CSV.
- Ejecución: observada; el archivo fue localizado y abierto.
- Explicación: demostró el papel de `open`, `with`, `as`, los dos puntos y la sangría.
- Método de validación: revisión estática, ejecución y explicación propia.

## Errores y correcciones

- La primera ejecución produjo `FileNotFoundError`; se corrigió ejecutando desde la carpeta que contiene el script y el CSV.

## Pendiente

Nada para este bloque.

## Conexiones

- [[09 - S04-B4 - Totales y promedios]]
- [[Python desde 0 - Índice]]
