---
tags: [python, aprendizaje, semana-7, bloque-2]
tipo: bloque
semana: 7
bloque: S07-B2
estado: validado
fecha: 2026-07-20
---

# S07-B2 - Nombres y responsabilidades

## Objetivo

Usar nombres que describan los datos reales y separar las responsabilidades de clasificación, cálculo, conteo y presentación.

## Conocimiento esencial

- Los parámetros `unidades_producidas` y `unidades_defectuosas` representan datos de un registro de producción.
- Los contadores `cantidad_registros_aceptados` y `cantidad_registros_rechazados` cuentan resultados; no representan unidades.
- `clasificar_registro()` tiene una responsabilidad: devolver `Aceptado` o `Rechazado`.
- `calcular_unidades_buenas()` tiene una responsabilidad distinta: restar defectuosas a producidas.
- El recorrido `for` cuenta resultados y `print()` los presenta en consola.

## Lo que construyó el estudiante

Construyó desde un archivo nuevo una función clasificadora, un recorrido de resultados con contadores descriptivos y una función independiente para calcular unidades buenas.

## Evidencia

- Archivo: `C:\Users\MSI ERICK\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\practica_s07.py`
- Revisión: se inspeccionaron nombres, función clasificadora, acumuladores, recorrido y función de cálculo.
- Ejecución: observada; produjo `Aceptado`, `Rechazado`, `Registros aceptados: 1`, `Registros rechazados: 1` y `Unidades buenas: 80`.
- Explicación: demostrada; explicó que los contadores miden cantidad de registros aprobados, mientras la función clasifica con unidades de producción.
- Método de validación: revisión estática, salida real de consola y explicación del estudiante.

## Errores y correcciones

- Inicialmente renombró los parámetros de la función como si fueran contadores. Se corrigió al distinguir datos de un registro (unidades) de resultados acumulados (cantidad de registros).

## Pendiente

Nada para este bloque.

## Conexiones

- [[18 - S07-B1 - Separar responsabilidades]]
- [[17 - S06-B4 - Resumen de filas aceptadas y rechazadas]]
- [[Python desde 0 - Índice]]
