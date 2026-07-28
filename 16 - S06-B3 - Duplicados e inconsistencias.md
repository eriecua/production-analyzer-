---
tags: [python, aprendizaje, semana-6, bloque-3]
tipo: bloque
semana: 6
bloque: S06-B3
estado: validado
fecha: 2026-07-19
---

# S06-B3 - Duplicados e inconsistencias

## Objetivo

Detectar identificadores repetidos y cantidades que contradicen las reglas de producción.

## Conocimiento esencial

- Un identificador debe ser único para distinguir cada registro.
- `==` permite comparar dos identificadores y detectar si están duplicados.
- Un valor repetido no siempre es un error; depende de la regla del campo.
- Los defectos no pueden superar las unidades producidas.
- Las cantidades negativas no tienen sentido para estos registros y deben rechazarse.

## Lo que construyó el estudiante

Ejemplos que comparan dos identificadores y validan defectos superiores a la producción y unidades negativas mediante condiciones `if`.

## Evidencia

- Archivo: `practica_s06.py`
- Revisión: se inspeccionó el archivo guardado.
- Ejecución: observada con identificadores diferentes, defectos mayores y cantidades negativas; también se probaron las rutas coherentes y válidas.
- Explicación: demostrada; distinguió duplicados de inconsistencias y explicó por qué los errores humanos requieren validación.
- Método de validación: revisión estática, ejecución desde PowerShell y explicación del estudiante.

## Errores y correcciones

- Se corrigió la etiqueta de salida `Indentificadores` a `Identificadores`.

## Pendiente

Nada para este bloque.

## Conexiones

- [[15 - S06-B2 - Campos faltantes y tipos invalidos]]
- [[Python desde 0 - Índice]]
