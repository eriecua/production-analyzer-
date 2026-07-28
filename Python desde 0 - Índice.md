---
tags: [python, aprendizaje, indice]
---

# Python desde 0

Este apartado reúne exclusivamente las notas del programa de Python. Está separado de `English Learning Notes`.

## Sistema

- [[Python desde 0 - Log]] — Historial cronológico de cierres y validaciones.

## Base de conocimiento de tres capas

- [[Capa 1 - Fuentes originales/Índice de fuentes]] — Libros originales, inmutables y verificados.
- [[Capa 2 - Wiki/Índice de conocimientos]] — Conceptos sintetizados y conectados con la práctica.
- [[Capa 3 - Esquema/Constitución de la Wiki]] — Reglas que deben seguir los agentes de IA.
- [[Capa 2 - Wiki/Próxima ruta - Análisis de datos (post-fundamentos)]] — Ruta futura planificada (Python/pandas → SQL → Power BI); pendiente de activación hasta cerrar el plan vigente.

## Fundamentos

- [[01 - Funciones - def y return]]

## Semana 3 — Funciones

- [[02 - S03-B1 - Parametros, argumentos y variables externas]] — Diferencia entre parámetros, argumentos y variables externas. Estado: validado.
- [[03 - S03-B2 - Funciones para cada KPI]] — Separación del cálculo de cumplimiento en una función propia. Estado: validado por revisión estática.
- [[04 - S03-B3 - Validar registros]] — Integración de meta, defectos y horas con cinco casos ejecutados y explicados. Estado: validado.
- [[05 - S03-B4 - Integrar funciones y validar registros]] — Función coordinadora, retorno del primer error y pruebas de casos válidos e inválidos. Estado: validado.

## Semana 4 — Listas y diccionarios

- [[06 - S04-B1 - Registro con diccionario]] — Registro de producción con ocho columnas y acceso mediante claves. Estado: validado.
- [[07 - S04-B2 - Lista de registros]] — Dos diccionarios de producción almacenados en una lista y acceso por índice y clave. Estado: validado.
- [[08 - S04-B3 - Recorrer registros con for]] — Recorrido de registros de producción con `for` e identificación de datos por clave. Estado: validado.
- [[09 - S04-B4 - Totales y promedios]] — Acumuladores para totales y promedio de registros de producción. Estado: validado.

## Semana 5 — Lectura de CSV

- [[10 - S05-B1 - Archivos rutas y codificacion]] — Apertura segura, rutas relativas y codificación UTF-8. Estado: validado.
- [[11 - S05-B2 - CSV de ejemplo]] — Archivo con ocho columnas y dos registros de producción. Estado: validado.
- [[12 - S05-B3 - Leer CSV con DictReader]] — Lectura de filas como diccionarios y acceso mediante claves. Estado: validado.
- [[13 - S05-B4 - Convertir filas a tipos correctos]] — Conversión de texto a `int` y `float` para realizar cálculos. Estado: validado.

## Proyecto principal

- Analizador de producción

## Semana 6 — Errores y limpieza

- [[14 - S06-B1 - Excepciones concretas y ValueError]] — Conversión segura de datos y captura específica de `ValueError`. Estado: validado.
- [[15 - S06-B2 - Campos faltantes y tipos invalidos]] — Detección de campos vacíos y tipos numéricos inválidos. Estado: validado.
- [[16 - S06-B3 - Duplicados e inconsistencias]] — Detección de identificadores repetidos y cantidades incoherentes. Estado: validado.
- [[17 - S06-B4 - Resumen de filas aceptadas y rechazadas]] — Acumulación de resultados devueltos por una función clasificadora. Estado: validado.

## Semana 7 — Organización del código

- [[18 - S07-B1 - Separar responsabilidades]] — Distinción entre recibir, validar, calcular y presentar. Estado: validado.
- [[19 - S07-B2 - Nombres y responsabilidades]] — Nombres descriptivos para datos y contadores; funciones con una responsabilidad clara. Estado: validado.
- [[21 - S07-B3 - Constantes y anotaciones de tipo]] — Constantes reutilizables y anotaciones para parámetros y retornos de funciones. Estado: validado.
- [[22 - S07-B4 - Documentar funciones importantes]] — Docstrings y uso de help() para comprender funciones sin ejecutar su lógica. Estado: validado.

## Semana 8 — Análisis por grupos

- [[23 - S08-B1 - Agrupar datos por turno]] — Agrupación dinámica y acumulación de unidades producidas por turno. Estado: validado.
- [[24 - S08-B2 - Agrupar datos por producto]] — Transferencia del agrupamiento dinámico para acumular unidades por producto. Estado: validado.
- [[25 - S08-B3 - Comparar productividad y calidad]] — Indicadores por registro y primera etiqueta de calidad. Estado: validado.
- [[27 - S08-B4 - Identificar mejores y peores resultados]] — Mejor/peor turno por defectos y mejor/menor producto por unidades producidas con `max`/`min`/`lambda`. Estado: validado.

## Semana 9 — Reportes

- [[28 - S09-B1 - Disenar el resumen general]] — Acumuladores simples para totales generales, sin agrupar por clave. Estado: validado.
- [[29 - S09-B2 - Exportar resultados por turno]] — Escritura de `resumen_por_turno.csv` con `csv.DictWriter` y `with open`. Estado: validado.
- [[30 - S09-B3 - Exportar resultados por producto]] — Transferencia del patrón de exportación a la agrupación por producto. Estado: validado.
- [[31 - S09-B4 - Mostrar un resumen legible en consola]] — Tablas alineadas con especificadores de formato en f-strings. Estado: validado.

## Bloque puente (previo a la Semana 10)

- [[33 - Bloque puente - Proyecto real, reportes y primera prueba]] — CSV real con los ocho campos, los tres reportes en `salidas/`, y la primera prueba automatizada del proyecto. Estado: validado.
- [[32 - Refactorizar a funcion y para que sirve un test]] — Por qué extraer una función habilita el test, alcance local de los acumuladores, y cuándo hace falta una lista con `append`. Estado: explicación del tutor; pendiente de demostración por el estudiante.

## Prácticas de transferencia

- [[20 - Practica de transferencia - Calculadora validada]] — Calculadora interactiva con validación de números, operadores y repetición S/N. Estado: validado como práctica complementaria; no cierra un bloque oficial.
- [[26 - Practica adicional - Funciones y cumplimiento por producto]] — Función `obtener_defectos_por_turno` y cumplimiento por producto con `meta_unidades`. Estado: validado como práctica complementaria; no cierra S08-B4 (el objetivo oficial de S08-B4 es identificar mejores y peores resultados).
