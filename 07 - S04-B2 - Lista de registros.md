---
tags: [python, aprendizaje, semana-4, bloque-2, listas, diccionarios]
tipo: bloque
semana: 4
bloque: S04-B2
estado: validado
fecha: 2026-07-17
---

# S04-B2 - Guardar varios registros en una lista

## Objetivo

Almacenar varios registros de producción (diccionarios) dentro de una lista y recuperar un valor concreto.

## Conocimiento esencial

- Cada registro de producción es un diccionario con las ocho columnas del CSV.
- `registros = [registro_1, registro_2]` es una lista de diccionarios.
- Los índices de una lista empiezan en cero: `registros[1]` selecciona el segundo registro.
- `registros[1]["producto"]` primero selecciona el diccionario y después busca la clave `producto`.
- Los corchetes sirven para seleccionar por índice en una lista o buscar una clave en un diccionario, según el objeto.

## Lo que construyó el estudiante

En `practica_s04.py` creó `registro_1`, `registro_2` y `registros`, y mostró el producto del segundo registro.

## Evidencia

- Archivo: `practica_s04.py`
- Revisión: se confirmaron dos diccionarios dentro de una lista.
- Ejecución: salida observada: `Producto B`.
- Explicación: el estudiante explicó correctamente el índice `1` y la clave `producto`.
- Método: revisión, ejecución y explicación propia.

## Pendiente

Nada para este bloque.

## Conexiones

- [[06 - S04-B1 - Registro con diccionario]]
- [[Python desde 0 - Índice]]
- [[Capa 2 - Wiki/Índice de conocimientos]]
