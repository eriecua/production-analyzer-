---
tags: [python, aprendizaje, log]
tipo: log
---


# Log de aprendizaje — Python desde 0

Registro cronológico y acumulativo. Las entradas nuevas se agregan al final; no se reemplazan las anteriores.

## [2026-07-16 16:27] sistema-creado | agente de cierre

- Habilidad: `cerrar-bloque-aprendizaje`
- Función: registrar conocimientos esenciales y evidencia al cerrar cada bloque o módulo.
- Índice: [[Python desde 0 - Índice]]
- Regla: no inventar ejecuciones, pruebas, explicaciones ni porcentajes.
- Fuente de diseño: patrón LLM Wiki de Karpathy.

## [2026-07-16 16:27] bloque-validado | S03-B2

- Evidencia: `practica_s03.py`
- Verificación: revisión estática del archivo guardado.
- Ejecución observada: no.
- Nota: [[03 - S03-B2 - Funciones para cada KPI]]
- Índice actualizado: sí.
- ProjectLibre: pendiente de actualización.
- Observación: se validó la separación de un segundo KPI en una función; no se afirma que todos los KPI finales estén construidos.

## [2026-07-16 17:05] bloque-pendiente | S03-B3

- Evidencia: `practica_s03.py`
- Verificación: revisión estática y ejecución observada.
- Nota: [[04 - S03-B3 - Validar registros]]
- Índice actualizado: sí.
- ProjectLibre: no solicitado.
- Observación: `validar_defectos(...)` ya prueba cuatro casos, pero sigue rechazando `0` y falta integrar `validar_registro(...)`.

## [2026-07-16 17:18] bloque-pendiente | S03-B3

- Evidencia: `practica_s03.py`
- Verificación: revisión estática y ejecución observada.
- Nota: [[04 - S03-B3 - Validar registros]]
- Índice actualizado: no requirió cambios.
- ProjectLibre: no solicitado.
- Observación: `validar_meta(...)` y `validar_defectos(...)` ya funcionan a nivel básico; falta `validar_registro(...)` para validar el bloque completo.

## [2026-07-16 17:28] bloque-pendiente | S03-B3

- Evidencia: `practica_s03.py`
- Verificación: revisión estática y ejecución observada.
- Nota: [[04 - S03-B3 - Validar registros]]
- Índice actualizado: no requirió cambios.
- ProjectLibre: no solicitado.
- Observación: quedó validado el subpaso de funciones simples `validar_meta`, `validar_defectos` y `validar_horas`; la integración en `validar_registro(...)` se pospone para evitar saltos de dificultad.

## [2026-07-16 18:11] bloque-pendiente | S03-B3

- Evidencia: `practica_s03.py`
- Verificación: revisión estática, ejecución observada y explicación de resultados.
- Nota: [[04 - S03-B3 - Validar registros]]
- Índice actualizado: sí.
- ProjectLibre: no solicitado.
- Observación: el estudiante guardó correctamente en variables los valores devueltos por `validar_meta`, `validar_defectos` y `validar_horas`; falta integrar `validar_registro(...)`.

## [2026-07-17 10:14] bloque-pendiente | S03-B3

- Evidencia: `practica_s03.py`
- Verificación: revisión estática y ejecución observada de cinco casos.
- Nota: [[04 - S03-B3 - Validar registros]]
- Índice actualizado: sí.
- ProjectLibre: no solicitado.
- Observación: la integración devuelve `OK` para el caso válido y los mensajes correctos para meta, defectos excesivos, horas inválidas y defectos negativos; faltaba la explicación del estudiante.

## [2026-07-17 10:18] bloque-validado | S03-B3

- Evidencia: `practica_s03.py`
- Verificación: revisión estática, ejecución observada de cinco casos y explicación del estudiante.
- Nota: [[04 - S03-B3 - Validar registros]]
- Índice actualizado: sí.
- ProjectLibre: no solicitado.
- Observación: S03-B3 validado; la función coordina las tres validaciones y el estudiante explicó las reglas de aceptación y rechazo.

## [2026-07-17 11:58] bloque-validado | S03-B4

- Evidencia: `practica_s03.py`
- Verificación: revisión estática, ejecución observada de seis casos y explicación del estudiante.
- Nota: [[05 - S03-B4 - Integrar funciones y validar registros]]
- Índice actualizado: sí.
- ProjectLibre: pendiente.
- Observación: S03-B4 validado. La función coordinadora reutiliza `validar_meta`, `validar_defectos` y `validar_horas`, devuelve el primer error y entrega `OK` en el caso válido. La conexión de ProjectLibre no estuvo disponible en esta sesión.

## [2026-07-17 12:04] recordatorio-manual | Semana 3

- Estado: cuatro bloques validados y evaluación semanal aprobada como recomendación.
- Recordatorio: actualizar manualmente ProjectLibre para S03-B1, S03-B2, S03-B3, S03-B4 y `VALIDACIÓN SEMANAL 3`.
- Alcance: este registro no modifica el archivo `.pod`; solo recuerda la tarea pendiente.

## [2026-07-17 12:48] bloque-validado | S04-B1

- Evidencia: `practica_s04.py`
- Verificación: revisión estática, ejecución observada y explicación del estudiante.
- Nota: [[06 - S04-B1 - Registro con diccionario]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 4.
- Observación: el estudiante representó las ocho columnas del registro de producción con pares clave-valor y recuperó valores usando corchetes.

## [2026-07-17 13:06] bloque-validado | S04-B2

- Evidencia: `practica_s04.py`
- Verificación: revisión estática, ejecución observada y explicación del estudiante.
- Nota: [[07 - S04-B2 - Lista de registros]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 4.
- Observación: dos diccionarios de producción fueron almacenados en una lista; el estudiante explicó `registros[1]["producto"]`.

## [2026-07-17 16:15] bloque-validado | S04-B3

- Evidencia: `practica_s04.py`
- Verificación: revisión estática, ejecución observada y explicación del estudiante.
- Nota: [[08 - S04-B3 - Recorrer registros con for]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 4.
- Observación: el ciclo recorrió los dos registros y mostró Producto A (850) y Producto B (800).

## [2026-07-17 17:21] bloque-validado | S04-B4

- Evidencia: `practica_s04.py`
- Verificación: revisión estática, ejecución observada y explicación del estudiante.
- Nota: [[09 - S04-B4 - Totales y promedios]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 4.
- Observación: se obtuvieron total producido `1650`, total defectuoso `54` y promedio `825.0`; se corrigió la indentación del promedio.

## [2026-07-17 17:21] evaluacion-semanal | Semana 4

- Comprensión conceptual: Demostrado — explicó listas, diccionarios, `for`, acumuladores y `len()`.
- Construcción: Demostrado — construyó y recorrió registros de producción y calculó totales y promedio.
- Pruebas y depuración: Demostrado — detectó y corrigió el promedio colocado dentro del ciclo.
- Explicación y transferencia: Demostrado — relacionó el recorrido con múltiples productos y subproductos industriales.
- Autonomía y retención: En desarrollo — resolvió los ejercicios con guía gradual y explicó el resultado.
- Fortaleza: modelado de registros y lectura del flujo de un `for`.
- Punto a reforzar: practicar más acumuladores cuando se incorporen datos desde CSV.
- Repaso breve: repetir un total y un promedio con tres registros antes de leer archivos.
- Recomendación: aprobar.
- Recordatorio: actualizar manualmente ProjectLibre para S04-B1, S04-B2, S04-B3, S04-B4 y `VALIDACIÓN SEMANAL 4`.

## [2026-07-17 19:09] bloque-validado | S05-B1

- Evidencia: `practica_s05.py`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[10 - S05-B1 - Archivos rutas y codificacion]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 5.
- Observación: se comprendieron ruta absoluta, ruta relativa, UTF-8 y apertura segura con `with`.

## [2026-07-17 19:09] bloque-validado | S05-B2

- Evidencia: `produccion_ejemplo.csv`
- Verificación: lectura directa y uso posterior desde Python.
- Nota: [[11 - S05-B2 - CSV de ejemplo]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 5.
- Observación: ocho columnas y dos registros completos verificados.

## [2026-07-17 19:09] bloque-validado | S05-B3

- Evidencia: `practica_s05.py` y `produccion_ejemplo.csv`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[12 - S05-B3 - Leer CSV con DictReader]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 5.
- Observación: las dos filas fueron cargadas y mostradas sin escribir los registros en el script.

## [2026-07-17 19:09] bloque-validado | S05-B4

- Evidencia: `practica_s05.py`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[13 - S05-B4 - Convertir filas a tipos correctos]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 5.
- Observación: los campos numéricos fueron convertidos y se calcularon `816` y `780` unidades buenas.

## [2026-07-17 19:09] evaluacion-semanal | Semana 5

- Comprensión conceptual: Demostrado — explicó archivos, rutas, `with`, lectores, filas, claves y conversiones.
- Construcción: Demostrado — creó el CSV y un script que lo lee y procesa.
- Pruebas y depuración: Demostrado — corrigió un `FileNotFoundError` y comprobó conversiones con operaciones.
- Explicación y transferencia: Demostrado — explicó cómo cada fila se convierte en diccionario y luego en valores numéricos utilizables.
- Autonomía y retención: En desarrollo — construyó las piezas con guía gradual y pidió aclaraciones antes de copiar sintaxis nueva.
- Fortaleza: insistió en comprender la estructura antes de avanzar y pudo explicarla con sus palabras.
- Punto a reforzar: distinguir con rapidez el lector, la fila actual, la clave y el valor obtenido.
- Repaso breve: retirar las operaciones de prueba y dejar una salida de producción legible.
- Recomendación: aprobar.
- Recordatorio: actualizar manualmente ProjectLibre para S05-B1, S05-B2, S05-B3, S05-B4 y `VALIDACIÓN SEMANAL 5`.

## [2026-07-18 00:00] bloque-validado | S06-B1

- Evidencia: `practica_s06.py`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[14 - S06-B1 - Excepciones concretas y ValueError]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 6.
- Observación: comprobó un valor válido (`850`) y un valor inválido (`ochocientos`) con `try/except ValueError`.

## [2026-07-19 00:00] bloque-validado | S06-B2

- Evidencia: `practica_s06.py`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[15 - S06-B2 - Campos faltantes y tipos invalidos]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 6.
- Observación: comprobó campo vacío, valor válido `80` y texto inválido `ochocientos`.

## [2026-07-19 00:00] bloque-validado | S06-B3

- Evidencia: `practica_s06.py`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[16 - S06-B3 - Duplicados e inconsistencias]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 6.
- Observación: comprobó identificadores diferentes, duplicados, defectos superiores a producción y cantidades negativas.

## [2026-07-19 00:00] bloque-validado | S06-B4

- Evidencia: `practica_s06.py`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[17 - S06-B4 - Resumen de filas aceptadas y rechazadas]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 6.
- Observación: cuatro resultados produjeron dos aceptados y dos rechazados mediante una función y acumuladores.

## [2026-07-19 00:00] evaluacion-semanal | Semana 6

- Comprensión conceptual: Demostrado — explicó `ValueError`, campos vacíos, duplicados, inconsistencias y acumuladores.
- Construcción: Demostrado — construyó validaciones, una función clasificadora y un resumen de aceptados/rechazados.
- Pruebas y depuración: Demostrado — comprobó casos válidos, vacíos, inválidos, duplicados y cantidades incoherentes.
- Explicación y transferencia: Demostrado — distinguió la responsabilidad de la función, el `if` y el acumulador, y anticipó el uso de `for`.
- Autonomía y retención: En desarrollo — necesitó guía para integrar la función con los contadores.
- Fortaleza: relacionó los errores de los registros con fallas humanas reales.
- Punto a reforzar: reemplazar la repetición manual por un recorrido con `for`.
- Repaso breve: recorrer una colección de registros y aplicar una función a cada fila.
- Recomendación: aprobar.
- Recordatorio: actualizar manualmente ProjectLibre para S06-B1, S06-B2, S06-B3, S06-B4 y `VALIDACIÓN SEMANAL 6`.

## [2026-07-20 00:00] bloque-validado | S07-B1

- Evidencia: `practica_s06.py` y explicación del estudiante.
- Verificación: revisión conceptual de piezas existentes y explicación demostrada.
- Nota: [[18 - S07-B1 - Separar responsabilidades]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre al cerrar la Semana 7.
- Observación: clasificó correctamente recepción, validación, cálculo y presentación; aún falta reorganizar el código.

## [2026-07-20 00:00] bloque-validado | S07-B2

- Evidencia: `practica_s07.py`
- Verificación: revisión estática, ejecución observada y explicación.
- Nota: [[19 - S07-B2 - Nombres y responsabilidades]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 7 aún no está completa.
- Observación: distinguió datos de producción de contadores de registros y construyó funciones separadas para clasificar y calcular unidades buenas.

## [2026-07-22 12:11] practica-validada | Calculadora interactiva

- Evidencia: `calculadora.py`
- Verificación: revisión estática, ejecución observada y explicación previa del estudiante.
- Nota: [[20 - Practica de transferencia - Calculadora validada]]
- Índice actualizado: sí.
- Recordatorio: no aplica; no corresponde al cierre de una semana oficial.
- Observación: rechazó una respuesta S/N inválida, repitió con `s` y cerró correctamente con `n`. No valida S07-B3.

## [2026-07-22 12:29] bloque-validado | S07-B3

- Evidencia: `practica_s07.py`
- Verificación: revisión estática, ejecución observada y explicación del estudiante.
- Nota: [[21 - S07-B3 - Constantes y anotaciones de tipo]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 7 aún no está completa.
- Observación: utilizó constantes, anotó parámetros y retornos, y comprobó que las anotaciones no convierten ni validan automáticamente.

## [2026-07-22 14:14] bloque-validado | S07-B4

- Evidencia: `practica_s07.py`
- Verificación: revisión estática, ejecución observada, salida de `help()` y explicación del estudiante.
- Nota: [[22 - S07-B4 - Documentar funciones importantes]]
- Índice actualizado: sí.
- Recordatorio: pendiente de evaluación semanal.
- Observación: documentó dos funciones y distinguió entre propósito de la docstring y tipo de retorno anotado.

## [2026-07-22 14:15] evaluacion-semanal | Semana 7

- Comprensión conceptual: Demostrado — distinguió recepción, validación, cálculo y presentación; explicó constantes, anotaciones y docstrings.
- Construcción: Demostrado — creó funciones separadas para clasificar registros y calcular unidades buenas, con nombres descriptivos, constantes, tipos y documentación.
- Pruebas y depuración: Demostrado — ejecutó casos aceptado/rechazado, comprobó advertencias de tipos con decimales y verificó ambas funciones mediante `help()`.
- Explicación y transferencia: Demostrado — diferenció contadores de registros y unidades, y explicó la diferencia entre propósito de una función y tipo de retorno.
- Autonomía y retención: En desarrollo — construyó y corrigió el código, pero necesitó guía gradual para la flecha de retorno y para precisar la docstring.
- Fortaleza: relaciona los nombres y las responsabilidades con el significado real de los datos de producción.
- Punto a reforzar: describir con precisión entradas, comparación interna y valor devuelto sin mezclar sus tipos.
- Repaso breve: antes de documentar una función, responder qué recibe, qué decisión o cálculo realiza y qué devuelve.
- Recomendación: aprobar.
- Recordatorio: actualizar manualmente ProjectLibre para S07-B1, S07-B2, S07-B3, S07-B4 y `VALIDACIÓN SEMANAL 7`.

## [2026-07-22 16:23] bloque-validado | S08-B1

- Evidencia: `practica_s08.py`
- Verificación: revisión estática, ejecución observada, prueba con un turno nuevo y explicación del estudiante.
- Nota: [[23 - S08-B1 - Agrupar datos por turno]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 8 aún no está completa.
- Observación: agrupó dinámicamente `Mañana: 220`, `Noche: 80` y `Tarde: 90` sin declarar previamente los turnos en el acumulador.

## [2026-07-22 18:40] bloque-validado | S08-B2

- Evidencia: `practica_s08.py`
- Verificación: revisión estática, ejecución observada y explicación del estudiante.
- Nota: [[24 - S08-B2 - Agrupar datos por producto]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 8 aún no está completa.
- Observación: acumuló Producto A como `100 + 120 = 220` y conservó Producto B y Producto D como grupos independientes.

## [2026-07-23 12:19] bloque-pendiente | S08-B3  - Evidencia: practica_s08.py - Verificación: revisión estática y ejecución observada. - Nota: [[25 - S08-B3 - Comparar productividad y calidad]] - Índice actualizado: sí. - Recordatorio: no aplica; la Semana 8 aún no está completa. - Observación: se calcularon y mostraron unidades buenas, productividad bruta, tasa de defectos y rendimiento. Falta comparar entre grupos, demostrar un caso sin defectos y explicar los indicadores.

## [2026-07-23 17:53] bloque-pendiente | S08-B3  - Evidencia: practica_s08.py - Verificación: revisión estática y ejecución observada. - Nota: [[25 - S08-B3 - Comparar productividad y calidad]] - Índice actualizado: sí; conserva estado pendiente de validación. - Recordatorio: no aplica; la Semana 8 aún no está completa. - Observación: se demostró el rendimiento global por producto y se explicó el uso de acumuladores y claves. Queda pendiente el cumplimiento agrupado y la comparación por turno.

## [2026-07-23 20:25] bloque-validado | S08-B3

- Evidencia: `practica_s08.py`
- Verificación: revisión estática, ejecución observada y explicación demostrada por el estudiante.
- Nota: [[25 - S08-B3 - Comparar productividad y calidad]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 8 aún no está completa.
- Observación: calculó la tasa de defectos agrupada por turno e interpretó que el turno Tarde ofrece el mejor desempeño general en calidad (2.14% de defectos) a pesar de producir menos.

## [2026-07-25 00:00] practica-validada | Funciones y cumplimiento por producto

- Evidencia: `practica_s08.py`
- Verificación: revisión estática, ejecución observada y explicación del estudiante.
- Nota: [[26 - Practica adicional - Funciones y cumplimiento por producto]]
- Índice actualizado: sí.
- Recordatorio: no aplica; no corresponde al cierre de un bloque oficial.
- Observación: empaquetó `obtener_defectos_por_turno(lista_registro)` con `return` fuera del `for`, y construyó `meta_unidades_por_producto` para calcular cumplimiento por producto (resultado con metas de prueba: 100 % en los cuatro productos). Explicó con analogías propias la diferencia entre clave literal y clave por variable en un diccionario.

## [2026-07-25 00:05] correccion-de-registro | S08-B4

- Motivo: se cargó `Plan_completo_ProjectLibre_para_Claude.pdf` y el XML exportado del `.pod`, revelando que el objetivo oficial de S08-B4 es "Identificar mejores y peores resultados" (0 % completado en ProjectLibre), no "empaquetar reportes en funciones" como se había registrado por error.
- Acción: la nota 26 fue renombrada de "S08-B4 - Empaquetar reportes en funciones" a "Práctica adicional - Funciones y cumplimiento por producto", removida del bloque oficial S08-B4 y reclasificada como práctica complementaria.
- Índice actualizado: sí; S08-B4 vuelve a listarse como pendiente, no iniciado.
- Observación: el trabajo del estudiante sigue siendo evidencia real y válida, solo estaba mal etiquetado como bloque oficial.

## [2026-07-25 01:00] bloque-validado | S08-B4

- Evidencia: `practica_s08.py`
- Verificación: revisión estática, ejecución observada y explicación demostrada por el estudiante.
- Nota: [[27 - S08-B4 - Identificar mejores y peores resultados]]
- Índice actualizado: sí.
- Recordatorio: Semana 8 completa; actualizar manualmente ProjectLibre para S08-B1, S08-B2, S08-B3, S08-B4 y `VALIDACIÓN SEMANAL 8`.
- Observación: identificó mejor/peor turno por defectos (Mañana 17, Tarde 3) y mayor/menor producto por unidades producidas (Producto A con 220) usando `max`/`min` con `key=lambda`. Corrigió un aviso real de Pylance anotando el tipo de retorno de una función. Explicó con sus palabras la diferencia entre palabra reservada y función incorporada, y probó por sí mismo el comportamiento de los corchetes como buscador (caso `KeyError` y caso exitoso).

## [2026-07-25 01:00] evaluacion-semanal | Semana 8

- Comprensión conceptual: Demostrado — explicó agrupación dinámica por clave, acumuladores paralelos, `max`/`min` con `key`, `lambda` y la diferencia entre buscar por clave y convertir un valor.
- Construcción: Demostrado — construyó agrupaciones por turno y por producto, indicadores de productividad/calidad, y la identificación de mejores/peores resultados en ambas dimensiones.
- Pruebas y depuración: Demostrado — corrigió un error real de Pylance (`reportCallIssue`) anotando el tipo de retorno de una función, y probó por sí mismo un caso de `KeyError` para confirmar el comportamiento del indexado.
- Explicación y transferencia: Demostrado — explicó con analogías propias (archivador, buscador, "post-it") por qué una variable no se "convierte" en clave, y por qué `key` es un traductor para `max`/`min`.
- Autonomía y retención: Demostrado — escribió sin ayuda el patrón `max()`/`min()` con `key=lambda` para el caso de producto, reutilizando lo aprendido con turnos.
- Fortaleza: no se conforma con que el código funcione; insiste en explicar el mecanismo interno (evaluación de variables, indexado, tipos) hasta entenderlo con precisión.
- Punto a reforzar: diferenciar con mayor rapidez entre lo que una función recibe, lo que devuelve, y lo que el `key` usa solo para comparar.
- Repaso breve: antes de la Semana 9, repetir de memoria (sin ver código previo) el patrón `max(diccionario, key=lambda clave: diccionario[clave])`.
- Recomendación: aprobar.
- Recordatorio: actualizar manualmente ProjectLibre para S08-B1, S08-B2, S08-B3, S08-B4 y `VALIDACIÓN SEMANAL 8`.

## [2026-07-26 00:00] bloque-validado | S09-B1

- Evidencia: `practica_s09.py`
- Verificación: revisión estática, ejecución observada, comprobación aritmética manual y explicación del estudiante.
- Nota: [[28 - S09-B1 - Disenar el resumen general]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 9 aún no está completa.
- Observación: acumuló 440 unidades producidas, 28 defectuosas y 34 horas. Se corrigió un `if ... not in registro` que comparaba un número contra claves de texto y por eso nunca filtraba; el estudiante explicó que el espacio ya existía al inicializar las variables en cero.

## [2026-07-26 00:10] bloque-validado | S09-B2

- Evidencia: `practica_s09.py` y `resumen_por_turno.csv`
- Verificación: revisión estática, ejecución observada, lectura del CSV generado y explicación del estudiante.
- Nota: [[29 - S09-B2 - Exportar resultados por turno]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 9 aún no está completa.
- Observación: generó el CSV con Mañana 220/16, Noche 80/7 y Tarde 140/11. Se corrigieron tres errores reales: sintaxis de `with open`, el bloque de escritura indentado dentro del bucle de construcción, y una suma dirigida al diccionario equivocado. El estudiante explicó que sin `with` habría que cerrar el archivo con `.close()`.

## [2026-07-26 00:20] bloque-validado | S09-B3

- Evidencia: `practica_s09.py` y `resumen_por_producto.csv`
- Verificación: revisión estática, ejecución observada, comprobación manual previa y lectura del CSV.
- Nota: [[30 - S09-B3 - Exportar resultados por producto]]
- Índice actualizado: sí.
- Recordatorio: no aplica; la Semana 9 aún no está completa.
- Observación: transferencia limpia del patrón, sin errores de indentación esta vez. El CSV coincidió con la comprobación manual anticipada: A 220/17, B 80/8, D 90/3, C 50/0.

## [2026-07-26 00:30] bloque-validado | S09-B4

- Evidencia: `practica_s09.py`
- Verificación: revisión estática y ejecución observada.
- Nota: [[31 - S09-B4 - Mostrar un resumen legible en consola]]
- Índice actualizado: sí.
- Recordatorio: Semana 9 completa; actualizar manualmente ProjectLibre para S09-B1, S09-B2, S09-B3, S09-B4 y `VALIDACIÓN SEMANAL 9`.
- Observación: construyó tres tablas alineadas en consola y retiró los `print` de diccionarios crudos. Se corrigió una desalineación por usar anchos distintos entre encabezado y filas de datos. La explicación de `with open`/`DictWriter` quedó a cargo del tutor más que del estudiante; se registra como punto a reforzar.

## [2026-07-26 00:30] evaluacion-semanal | Semana 9

- Comprensión conceptual: Demostrado — distinguió acumuladores simples de acumuladores por clave, y explicó el papel del `with`, el modo `"w"` y la lista de filas.
- Construcción: Demostrado — generó dos archivos CSV reales y tres tablas legibles en consola a partir de los mismos registros.
- Pruebas y depuración: Demostrado — corrigió cinco errores reales durante la semana (condicional inútil, sintaxis de `open`, indentación del bloque de escritura, diccionario equivocado en una suma, y anchos inconsistentes de formato).
- Explicación y transferencia: Demostrado — transfirió sin ayuda el patrón de exportación de turno a producto, y anticipó los valores esperados antes de ejecutar.
- Autonomía y retención: En desarrollo — el estudiante señaló por sí mismo que la sintaxis de `with open` y `csv.DictWriter` todavía no está memorizada y depende de consultar el molde previo.
- Fortaleza: pide el modelo mental detrás de la sintaxis en lugar de conformarse con copiar formatos, lo que produjo una regla propia de decisión sobre indentación y dependencia.
- Punto a reforzar: reconstruir de memoria el bloque completo de escritura CSV, sin consultar código anterior.
- Repaso breve: antes de la Semana 10, escribir desde cero un `with open(...) as f:` con `csv.DictWriter` para exportar cualquier diccionario de prueba.
- Recomendación: aprobar.
- Recordatorio: actualizar manualmente ProjectLibre para S09-B1, S09-B2, S09-B3, S09-B4 y `VALIDACIÓN SEMANAL 9`.

## [2026-07-26 01:00] auditoria-de-planificacion | pre-Semana 10

- Alcance: comparación entre lo construido hasta la Semana 9, la especificación `analizador-produccion/PROYECTO.md` y los objetivos oficiales de las Semanas 10 a 12 en ProjectLibre.
- Nota: [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]]
- Índice actualizado: sí, en [[Capa 2 - Wiki/Índice de conocimientos]].
- Resultado: los temas de S10, S11 y S12 son congruentes con los objetivos declarados; el desajuste está en la deuda acumulada, no en el temario.
- Desajustes registrados: `analizador_produccion.py` y `datos/produccion.csv` no existen; las Semanas 8 y 9 usaron datos escritos a mano en lugar de CSV; faltan los campos `id_registro` y `fecha`; la fórmula de productividad practicada difiere de la especificada; falta exportar `resumen_general.csv` y los CSV generados no están en `salidas/`.
- Tensión metodológica: la regla del vault pide pruebas graduales, pero el plan las concentra en la Semana 11.
- Corrección aplicada: se actualizó la condición de activación en [[Próxima ruta - Análisis de datos (post-fundamentos)]], que aún citaba S08-B4 como última nota.
- Acción acordada: ejecutar un bloque puente de seis pasos antes de abrir S10-B1. Ningún paso se ha ejecutado todavía.

## [2026-07-27] bloque-puente | pasos 1 a 4 completados

- Alcance: ejecución del plan de seis pasos definido en [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]].
- Evidencia: `analizador-produccion/analizador_produccion.py`, `analizador-produccion/datos/produccion.csv`, `analizador-produccion/salidas/`
- Verificación: ejecución observada y comprobación manual de valores.
- Paso 1 — creado `datos/produccion.csv` con los ocho campos obligatorios de la especificación, metas variadas y una fila deliberadamente inválida (70 producidas / 90 defectuosas).
- Paso 2 — lectura con `csv.DictReader`, conversión de tipos y rechazo de la fila inválida con `continue`. Resultado: 5 válidos, 1 rechazado.
- Paso 3 — migrados a datos reales los cálculos de las Semanas 8 y 9: totales generales, agrupación por turno y por producto.
- Paso 4 — completados los tres reportes en `salidas/`: `resumen_general.csv` (exportado por primera vez), `resumen_por_turno.csv` y `resumen_por_producto.csv`.
- Deuda resuelta: se adoptó la fórmula de la especificación, `Productividad = unidades buenas / horas trabajadas`, en lugar de la practicada con unidades producidas.
- Comprobaciones que pasan: Mañana 203 buenas / 16 h = 12.69; totales 440 producidas − 28 defectuosas = 412 buenas; 5 válidos + 1 rechazado = 6 filas del origen; `datos/produccion.csv` nunca se sobrescribió.
- Autonomía: el estudiante escribió los tres bloques de exportación por su cuenta y aplicó sin ayuda la regla de cuándo hace falta una lista (`resumen_general` sin lista, por ser una sola fila). Detectó por sí mismo, con una sola pista, que sobrescribía en lugar de acumular en `buenas_por_producto`.
- Paso 5 — iniciado, no cerrado. Extrajo correctamente `calcular_resumen_por_turno(registros)`, pero como copia y no como mudanza: la lógica quedó duplicada y el CSV sigue alimentándose del código suelto. Pendiente eliminar el original y enrutar la exportación por la función.
- Paso 6 — pendiente.
- Nota: [[32 - Refactorizar a funcion y para que sirve un test]]
- Índice actualizado: sí.
- Observación metodológica: el estudiante señaló con razón que el paso del test «apareció de la nada». El tutor reconoció el fallo de explicación propio: el paso venía en el plan, pero nunca se justificó su propósito antes de pedir el trabajo. La nota 32 registra la explicación resultante y queda marcada como explicación del tutor, no como comprensión demostrada.
- Recordatorio: sigue pendiente actualizar manualmente ProjectLibre para los bloques de las Semanas 8 y 9 y sus dos validaciones semanales.

## [2026-07-27] correccion-de-metodo | skill tutor-adaptativo-python

- Origen: el estudiante señaló una caída de calidad en la segunda mitad de la sesión del bloque puente.
- Diagnóstico compartido: la skill `tutor-adaptativo-python` ya contenía la regla que habría evitado cada fallo. El problema no fue la skill, sino que el tutor no la aplicó ni una vez durante la sesión.
- Fallos concretos del tutor: pedir deducir la sintaxis de `assert` sin haberla enseñado; formular preguntas y responderlas en el mismo mensaje; acumular varias tareas y varios conceptos por mensaje; repetir la misma corrección tres veces sin cambiar la representación; introducir `sys.path.append` en medio de una confusión abierta.
- Patrón común: al acercarse el final del bloque, el tutor aceleró y empezó a resolver en lugar de enseñar.
- Huecos reales encontrados en la skill: no indicaba en qué nivel de la escalera de ayuda entrar cuando el concepto es enteramente nuevo; no obligaba a esperar la respuesta del estudiante; no limitaba la carga por mensaje; no trataba la explicación con palabras propias como paso normal de cierre.
- Cambios aplicados a `.agents/skills/tutor-adaptativo-python/SKILL.md`: nueva regla 5 en «Intervención adaptativa» sobre el nivel de entrada según lo ya conocido; nueva sección «Turnos de conversación» con cinco reglas; nueva sección «Comprobación de comprensión» con cinco reglas.
- Preferencia declarada por el estudiante: aprende explicando lo complejo de forma sencilla; quiere ayuda inmediata si se atasca al explicar; quiere que los temas nuevos se enseñen antes de pedirle aplicarlos.
- Resumen de la sesión: `analizador-produccion/../resumen-sesion-2026-07-27.md`
- Codificación UTF-8 verificada.

## [2026-07-27 23:30] bloque-validado | Bloque puente pre-Semana 10

- Evidencia: `analizador-produccion/analizador_produccion.py`, `analizador-produccion/datos/produccion.csv`, `analizador-produccion/salidas/`, `analizador-produccion/tests/test_resumen_por_turno.py`, `practica_memoria.py`
- Verificación: ejecución observada, comprobación manual de valores y prueba de sabotaje del acumulador.
- Nota: [[33 - Bloque puente - Proyecto real, reportes y primera prueba]]
- Índice actualizado: sí.
- Recordatorio: actualizar manualmente ProjectLibre sigue pendiente para los bloques de las Semanas 8 y 9 y sus dos validaciones semanales. Este bloque puente no figura en el plan de ProjectLibre y no requiere entrada allí.
- Alcance: se ejecutaron los seis pasos del plan definido en [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]].
- Salidas reales observadas: `Registro válidos: 5`, `Registro rechazados: 1`, totales `440 28 412 34`, y `OK - test_resumen_por_turno`.
- Prueba de sabotaje: al sustituir `+=` por `=` en `buenas_por_turno`, la prueba falló señalando `assert resultado[0]["unidades_buenas"] == 340`. El archivo se restauró y se volvió a comprobar que los reportes dan los valores originales.
- Retención comprobada: reconstruyó de memoria el bloque completo de escritura CSV, sin consultar código anterior. Único fallo, los paréntesis de llamada en `writeheader` y `writerow`. Esto cierra el repaso pendiente que él mismo pidió al evaluar la Semana 9.
- Autonomía destacable: escribió `for fila in calcular_resumen_por_turno(registros):`, más limpio que la versión sugerida por el tutor; y detectó que la forma de construir listas de diccionarios que se le pedía contradecía la practicada en la Semana 4, teniendo razón en que ambas son válidas.
- Explicación demostrada: describió con sus palabras qué hace `with open` y por qué el `DictWriter` debe estar dentro del bloque. Se le añadió la precisión del cierre automático, comprobada con un `ValueError: I/O operation on closed file`.
- No demostrado todavía: escribir un `assert` sin que se entregue la sintaxis, y extraer una función desde cero sin molde.
- Observación: la nota 32 permanece marcada como explicación del tutor, no como comprensión demostrada, conforme a la regla de integridad del método.

## [2026-07-27] fuente-evaluada | roadmap.sh Python

- Origen: el estudiante propuso https://roadmap.sh/python como recurso de aprendizaje.
- Método: se consultaron la página principal y la sección de proyectos antes de emitir la valoración; no se opinó de memoria.
- Qué es: un mapa de temas en diagrama, sin lecciones propias, más un banco de 40+ enunciados de proyectos sin solución (28 principiante, 8 intermedio, 4 avanzado). Acceso gratuito.
- Decisión: no adoptarlo ahora. Es el roadmap de desarrollador de Python, no de analista de datos; incluye Django, Flask, FastAPI y OOP, ajenos al objetivo declarado. Resuelve un problema ya resuelto por el plan vigente y puede inducir falsa sensación de atraso.
- Activación condicionada: usar solo la sección de proyectos, después de cerrar la Semana 12, filtrando por análisis de datos, consumo de API y automatización.
- Mapa de temas: descartado de forma permanente. Los nueve libros de la Capa 1, en particular Python for Data Analysis de Wes McKinney, son mejor material y ya están evaluados y ordenados.
- Nota: [[Capa 2 - Wiki/Fuente evaluada - roadmap.sh Python]]
- Índice actualizado: sí, en [[Capa 2 - Wiki/Índice de conocimientos]]. Se corrigió además el estado de la auditoría, que seguía como pendiente de comprobar tras haberse ejecutado sus seis pasos.
- Observación: se registró en la nota un criterio general de tres preguntas para evaluar recursos externos futuros, aplicable a propuestas similares durante el plan vigente.

## [2026-07-27] fuentes-incorporadas | Pedagogia y tecnica Feynman

- Alcance: incorporación del libro de Marzano y de cuatro artículos web sobre la técnica Feynman, con su síntesis aplicada.
- Libro: `The Art and Science of Teaching` (Robert J. Marzano, ASCD, 2007). 234 páginas, 1.60 MiB, SHA-256 verificado con `pypdf`. Sus metadatos internos están corruptos (autor `debra`, título `10408-00_FM.indd`); autor y título se tomaron de la portada.
- Naturaleza distinta: los nueve libros previos son fuentes de contenido; este es fuente de método. No se sintetiza para un bloque del plan, sino para fundamentar la skill `tutor-adaptativo-python`.
- Artículos consultados directamente, no de memoria: Virginia Law (el más riguroso, único que declara límites del método), Todoist (en español), Thomas Oppong (citas directas de Feynman), Wispr Flow (sin aporte propio; se registra por completitud).
- Nota de Capa 1: [[Capa 1 - Fuentes originales/Fuentes web/Tecnica Feynman - cuatro articulos]]
- Nota de Capa 2: [[Capa 2 - Wiki/Tecnica Feynman aplicada a la programacion]]
- Índices actualizados: sí, ambos.
- Hallazgo principal: Marzano distingue conocimiento declarativo de procedimental (cap. 3, pp. 60-61). Resuelve una tensión real del proyecto: la preferencia declarada de Erick por «entender la lógica en lugar de memorizar formatos» es correcta para los conceptos, pero la sintaxis es conocimiento procedimental y solo se gana practicando. Virginia Law lo confirma desde el otro lado al advertir que la técnica Feynman es menos eficaz para temas de memorización.
- Confirmación independiente: Rosenshine (2002), citado por Marzano en p. 61, sostiene que los profesores más eficaces presentan poco material cada vez. Coincide con la regla de «una sola tarea por mensaje» añadida hoy a la skill a partir de la experiencia de la sesión, no de la lectura.
- Hallazgo aplicable a la IA: Virginia Law recomienda usarla como herramienta de prueba y no de instrucción durante el aprendizaje inicial. Coincide con la regla de integridad del método de no contar la explicación del tutor como comprensión demostrada.
- Deuda de método atendida en parte: hasta hoy ninguna nota citaba libro y página, pese a exigirlo la regla de crecimiento de la Capa 2. La nota nueva sí lo hace. Las notas 32 y 33 siguen sin citas.
- Configuración del entorno: se creó `CLAUDE.md` en la raíz del proyecto y una unión de directorio `.claude\skills` hacia `.agents\skills`, para que las skills sean descubribles por Claude sin duplicar archivos. Los 24 archivos de práctica se movieron de `LocalState` a `Python desde 0\practicas\`, verificando checksums antes de borrar los originales.

## [2026-07-27] configuracion-de-entorno | Control de versiones y limpieza

- Alcance: dejar el entorno listo antes de abrir la Semana 10. Ningun archivo de aprendizaje se modifico.
- Repositorio accidental eliminado: `C:\Users\MSI ERICK\.git` tenia 0 commits, 0 ramas y 0 stashes, sin `.gitignore` y con un remoto de marcador de posicion (`github.com/TU_USUARIO/TU_REPOSITORIO.git`) procedente de un tutorial copiado a medias. Ocupaba 11 GB de objetos sueltos y un `git add .` habria intentado indexar 498.641 archivos, incluido `.claude.json` con credenciales de sesion. Se verifico que no contenia historial antes de borrarlo; se recuperaron 11 GB de disco.
- Carpetas `.close-*-staging` eliminadas: las seis contenian copias de notas ya presentes en el vault. Se compararon una a una; cinco identicas y la de S08-B3 mas antigua que la del vault (`estado: pendiente-de-validacion`). No se perdio nada.
- Proyecto versionado: primer commit `f144f18` con 49 archivos. Se anadieron `.gitignore` y `.gitattributes`. Quedan ignoradas las salidas regeneradas, los `.pod` binarios y la union de directorio `.claude/skills`, que duplicaba las skills.
- Vault versionado: primer commit `ce42026` con 48 notas, y remoto privado en `github.com/eriecua/python-desde-0-vault`.
- Los PDF de la Capa 1 quedan fuera del repositorio: son 97 MB de los 98 totales, y proceden de z-library. Subirlos a GitHub seria redistribuir obra con derechos de autor, aunque el repositorio sea privado. Se comprobo contra la API de GitHub que el remoto no contiene ningun PDF. El indice de fuentes si se versiona, con el hash SHA-256 de cada libro.
- Identidad de git configurada por primera vez: `eriecua` con la direccion de privacidad `eriecua@users.noreply.github.com`, para no exponer el correo personal en los commits. Rama por defecto `main`.
- Documentacion: seccion de control de versiones anadida a `CLAUDE.md`, y `practicas/README.md` creado con la advertencia de ejecutar los scripts desde su propia carpeta.
- Verificacion posterior a los cambios: el analizador sigue dando 5 validos, 1 rechazado y totales `440 28 412 34`; la prueba sigue dando `OK - test_resumen_por_turno`; `practica_memoria.py` regenera su CSV. Identicos a antes de tocar nada.
- Pendiente menor: enlace roto `karpathy` en las fuentes de la Capa 1, preexistente. Para el proximo mantenimiento del vault.

## [2026-07-28] auditoria-de-alineacion | plan oficial vs trabajo real

- Origen: el estudiante pidio el `analizador_produccion.py` completo con las doce semanas para juzgar si el aprendizaje va alineado con la planificacion. Al aclarar el objetivo resulto ser una auditoria, no codigo.
- No se escribio el programa. Dos razones del propio proyecto: `PROYECTO.md` exige que el estudiante explique el flujo sin copiarlo, y S12-B1 es literalmente «Integrar la version final», es decir el programa completo es el entregable de la Semana 12.
- Fuentes verificadas en disco: el XML del `.pod` con los 78 elementos del plan, `PROYECTO.md`, el codigo medido con recuentos, los 24 archivos de `practicas/` y las 33 notas de bloque.
- Nota: [[Capa 2 - Wiki/Auditoria de alineacion - plan oficial vs trabajo real (pre-Semana 10)]]
- Indice actualizado: si, en [[Capa 2 - Wiki/Índice de conocimientos]].
- Veredicto: la alineacion de temario es correcta, todos los bloques de S03 a S09 tienen su nota validada y en orden. La alineacion de producto es incompleta.
- Hallazgo principal: las Semanas 3, 6 y 7 estan validadas en `practicas/` pero nunca llegaron al programa real. Medicion: 138 lineas, 1 funcion, 0 docstrings, 1 anotacion de tipo, 0 `try/except`, 0 constantes, 1 de 9 reglas de validacion. Contraste: `practica_s06.py` si tiene `try/except` y `practica_s07.py` si tiene funciones y anotaciones.
- Hueco del plan, no del estudiante: ningun bloque de S10 a S12 dice «implementar las validaciones». S11-B3 dice «probar validaciones» y presupone que existen.
- `id_registro` y `fecha` se cargan en cada registro pero no se referencian nunca. Son los dos campos que necesitan las validaciones de duplicados y de fechas invalidas.
- Ritmo: la Semana 9 se cerro 57 dias antes de lo planificado, con un maximo de once bloques validados el 17 de julio. No es desviacion: el estudiante estudia a diario y cierra cada semana conforme entiende los temas, con unas 10 h diarias disponibles. Las fechas del `.pod` son una estimacion superada, no un objetivo incumplido.
- Las Semanas 0, 1 y 2 no tienen notas porque se hicieron antes de que existiera el vault, como demuestran las fechas de `Prueba 1.py` (14 jul) y `practica_s02.py` (16 jul). No hay nada que rehacer.
- Plan de accion acordado: no crear un segundo bloque puente. Los huecos se reparten dentro de S10-B1 a S10-B3, mas un paso previo al inicio de la Semana 11 para escribir las ocho validaciones que faltan antes de probarlas.
- Auditoria anterior marcada como saldada, con nota de que detectaba un desajuste distinto por comparar contra la especificacion y no contra el plan de bloques.
- `CLAUDE.md` actualizado con el reparto de huecos, para que no se pierda entre sesiones.

## [2026-07-29 18:23] bloque-validado | S10-B1

- Evidencia: `analizador-produccion/analizador_produccion.py`
- Verificación: revisión estática, ejecución observada en los tres caminos y explicación del estudiante.
- Nota: [[34 - S10-B1 - Recibir la ruta CSV como argumento]]
- Índice actualizado: sí, nueva seccion «Semana 10 — Programa de consola».
- Cerró el pendiente que dejó abierto la sesión anterior: explicó `__name__` con sus palabras, en frío. Acertó sin ayuda que el valor lo pone Python y que la comparación es falsa al importar. Su formulación: «si el nombre coincide con la ejecución en el terminal entonces entra al bloque, si no se lo salta». Las tres analogías previas no se reutilizaron; funcionó la observación directa: imprimir `__name__`, `sys.argv[0]` y `sys.argv[1]` a la vez, y desactivar el guardián en una copia para ver `pytest` fallar con `PermissionError` al abrir `tests/`.
- Detalle menor cerrado: el mensaje de uso pasó de `<salidas/analizador>` a `<ruta_csv>`.
- Errores reales del bloque: `except` sin `sys.exit(1)` (el programa seguía y sobrescribía `salidas/` con ceros) y `open("ruta_csv")` con comillas, que producía un mensaje de error correcto en forma y falso en contenido.
- Trabajo adelantado en la misma sesión, fuera del reparto de S10-B1: extracción de `calcular_resumen_por_producto` (hueco «Funciones», sí corresponde a S10-B1); `try` / `except ValueError` por fila con `continue`, que salva las filas buenas de un CSV sucio; y las tres guardias de división entre cero devolviendo `None`. Las dos últimas son reglas de `PROYECTO.md` asignadas al paso previo a S11-B1, cerradas antes de tiempo. Anotarlo allí para que la contabilidad del plan no las cuente dos veces.
- Pruebas: de 1 a 4. Añadidos `tests/test_resumen_por_producto.py` con `test_resumen_por_producto` y `test_producto_sin_meta`, y `test_turno_sin_horas` en el archivo de turno. Los cuatro pasan con `python -m pytest tests/ -q`. Sin cubrir todavía: la guardia de `unidades_producidas == 0`, verificada solo con un CSV temporal.
- Nota 01 ampliada: la sección 6 incluye ahora el caso de `return` dentro de un bucle, con la traza de las tres vueltas. Salió de un error real del estudiante en `prueba def.py`.
- Observación de método: el tutor dirigió la sesión sin leer las skills del proyecto, porque no se cargan solas cuando el directorio de trabajo no es `Python desde 0`. El estudiante tuvo que señalarlo. Se incumplieron las reglas de turno (una tabla, una pregunta, una tarea por mensaje) y se anunció el cierre de S10-B1 sin invocar `cerrar-bloque-aprendizaje`. Registrado en la memoria persistente del asistente.

## [2026-08-04 18:25] bloque-validado | S10-B2

- Evidencia: `analizador-produccion/analizador_produccion.py`, líneas 101-103.
- Verificación: revisión estática, ejecución observada en los tres caminos y transferencia a un error nuevo.
- Nota: [[35 - S10-B2 - Validar que el archivo exista y sea legible]]
- Índice actualizado: sí, dentro de «Semana 10 — Programa de consola».
- El bloque se resolvió con una sola rama nueva, `except PermissionError`, escrita y alineada por el estudiante a la primera. Los tres caminos los ejecutó él en su terminal: carpeta `datos` devuelve `No se puede leer: datos`; `datos/no_existe.csv` devuelve el mensaje de `FileNotFoundError`; `datos/produccion.csv` devuelve 5 válidos, 1 rechazado y `440 28 412 34`.
- Obstáculo principal, y no era de código: reportó dos veces el mensaje de uso como salida de `python analizador_produccion.py datos`. Ejecutaba con el botón ▶ de VS Code, que lanza `python archivo.py` sin argumentos, entra por el guardián de `len(sys.argv) < 2` y no llega al `try`. El diagnóstico apuntaba en falso al `except` mientras el código ya estaba correcto y guardado. Se resolvió comparando la salida del botón con la del comando escrito a mano en la terminal integrada. Merece recordarse en S10-B4, que es precisamente «probar rutas válidas e inválidas en PowerShell».
- Explicación: su primera formulación de dónde sale el nombre del error fue imprecisa, «en el código de error». Acertaba en lo esencial —la información la da Python— pero esa expresión señala igual de bien al `Errno 13`, que no sirve. Tras afinar qué trozo de la última línea del traceback se copia, transfirió sin ayuda: ante `UnicodeDecodeError: 'utf-8' codec can't decode byte 0xf1...` escribió `except UnicodeDecodeError:`.
- Observación de método: se perdió el hilo a mitad de sesión y el estudiante lo dijo con estas palabras, «me siento muy perdido en este punto, no sé qué hacer». La causa fue intercalar tareas ajenas al bloque entre pasos: instalar la skill `find-skills`, revisar la lista de skills y mirar configuración. Funcionó reducir el alcance a cinco pasos numerados y una sola acción concreta.
- Fuera del bloque, a petición del estudiante: instalada la skill `find-skills` de `vercel-labs/skills` en `.agents/skills/find-skills`, con `skills-lock.json` nuevo en la raíz del repositorio. El instalador mostró `Gen: Safe`, `Socket: 0 alerts` y `Snyk: Med Risk`, sin motivo detallado. La skill es un único `SKILL.md` sin código ejecutable.
- Pendiente heredado a S10-B3: docstrings y anotaciones de tipo de las dos funciones, más las constantes con nombre para los códigos de salida.

## [2026-08-05 19:24] bloque-validado | S10-B3

- Evidencia: `analizador-produccion/analizador_produccion.py`, líneas 4-7, 9-10, 39-40, 81, 106, 110 y 152.
- Verificación: revisión estática, ejecución observada en las cuatro rutas con `$LASTEXITCODE` y explicación del estudiante.
- Nota: [[36 - S10-B3 - Codigos y mensajes de salida]]
- Índice actualizado: sí, dentro de «Semana 10 — Programa de consola».
- Cuatro constantes escritas por el estudiante: `SALIDA_OK = 0`, `SALIDA_NO_EXISTE_ARCHIVO = 1`, `SALIDA_COMANDO_ERRADO = 2`, `SALIDA_NO_LEE = 3`. Los tres `sys.exit(1)` existentes pasaron a usar la constante que les toca, y añadió un `sys.exit(SALIDA_OK)` explícito al final del bloque `if __name__ == "__main__":`.
- Ejecución reportada por él desde su terminal, en `analizador-produccion/`, con `; $LASTEXITCODE` detrás de cada comando: sin argumento devuelve `2`; `inventado.csv` devuelve `1`; la carpeta `datos` devuelve `3`; `datos/produccion.csv` devuelve `0` con 5 válidos, 1 rechazado y los totales `440 28 412 34`. Las cuatro coinciden con el mapa. Tras añadir el `sys.exit(SALIDA_OK)`, el tutor reejecutó el camino válido sobre el archivo guardado: sigue en `0`. `python -m pytest tests/ -q` pasa las 4 pruebas.
- Obstáculo principal, y era conceptual heredado de S10-B2: creía que `PermissionError` significaba ruta mal escrita. Repetir la explicación no funcionó; funcionó el contraste con un caso donde el comando es impecable —el CSV correcto abierto en Excel y bloqueado por Windows—, porque ahí se ve que reescribir el comando no arregla nada. Conclusión suya: «recibe un número nuevo porque es tipo diferente de error».
- Otro tropiezo: entendió «el 2 está reservado para el mal uso del comando» como «no uses el 2», y lo dejó vacío saltando al 3 y al 4 en lugar de asignárselo a esa causa.
- Nombres: los escribió primero en inglés, con dos falsos amigos reales, `FAIL_COMMENT` (comment es comentario, no comando) y `NOT_FOUND_ARCHIVE` (archive es archivo comprimido, no file). Al pasarlos al español, su primer intento `SALIDA_MAL_ESCRITA` volvía a codificar la confusión de arriba, porque en femenino apunta a «la ruta» y ese código salta cuando no hay ruta ninguna. Prueba útil que se usó para detectarlo: poner un comentario al lado del nombre y luego borrarlo; si la línea deja de entenderse sola, el nombre no sirve.
- Deuda de S07-B3 y S07-B4 saldada en el mismo bloque: docstring de una línea y anotaciones en las dos funciones, `registros: list` y `-> list[dict]`. Concepto nuevo para él, porque solo había anotado `int` y `str`: una lista también es un tipo. Anotó primero `registros: dict`, con fundamento —dentro sí hay diccionarios— pero confundiendo el recipiente con el contenido. Se aclaró leyendo su propio bucle: `registros` en plural es la caja, `registro` en singular es lo que se saca.
- Explicación final, con sus palabras: «el mensaje es para el usuario, y el programa puede detectar qué falló». Antes de eso había deducido solo de dónde salía el `0` de la cuarta prueba sin que `SALIDA_OK` apareciera en el código: «eso viene por defecto cuando se ejecuta el código».
- Aciertos propios sin que se le pidieran: reordenó las constantes por número de menos a más grave, renombró `SALIDA_NO_EXISTE` a `SALIDA_NO_EXISTE_ARCHIVO` para que se entendiera leída sola, eligió `list[dict]` en vez de `list` a secas, y decidió con argumento que `SALIDA_OK` fuera explícita: «prefiero que quede definido, luego limpiamos código».
- Observación de método: pidió dos veces que se le dieran los nombres hechos. Se le dio el prefijo y una constante de ejemplo, y los otros tres los escribió él. El vocabulario nuevo —la palabra `list` como tipo— sí se le dio directamente, porque no era deducible.
- Pendiente para el paso previo a S11-B1: las ocho reglas de validación de `PROYECTO.md` que faltan, leyendo `id_registro` y `fecha`. Detalle menor sin cerrar: comentario suelto `#int` en la línea 32.

## [2026-08-05 19:52] fuente-incorporada | Capa 1

- Fuente: `Capa 1 - Fuentes originales/Libros de programación/SQL Queries for Mere Mortals - John L. Viescas.pdf`
- Verificación: `pypdf` confirma 1051 páginas y autor `John L. Viescas` en los metadatos. SHA-256 `8B0B3E72E2E1182F4E87A98E70F6CA9F776E17FDAEF34E4BB3F6DB6483ACC217`, 12.24 MiB.
- Índice actualizado: sí, `Capa 1 - Fuentes originales/Índice de fuentes` — fila en la tabla, entrada de procedencia y una sección nueva con la estructura del libro.
- Procedencia distinta a la del resto: biblioteca local de Calibre en `D:\Libros\Calibre\John L. Viescas\`, no z-library. Copiado al vault con un nombre limpio, sin el `(r)` del original.
- Aviso registrado en el índice de fuentes: los metadatos declaran `calibre 9.12.0` como creador y productor, así que el PDF es una conversión y sus 1051 páginas no coinciden con la paginación impresa. Las citas `#page=N` valen para este archivo, no para la edición en papel.
- Conexión al grafo: enlazado desde `Índice de fuentes` (a su vez enlazado desde `Python desde 0 - Índice`) y desde [[Capa 2 - Wiki/Próxima ruta - Análisis de datos (post-fundamentos)]], donde se añadió como punto de entrada de la sección de SQL. No queda huérfano.
- Por qué entra: es el escalón que faltaba. Tanimura y el `SQL Cookbook` dan por sabida la sintaxis; este es el único de los tres que enseña SQL desde cero. Su estructura se leyó del índice del propio PDF, no se supuso: Parte I modelo relacional, Parte II `SELECT` y filtrado, Parte III joins y subconsultas, Parte IV agrupación, Parte V modificación de datos, Parte VI hasta funciones de ventana.
- Sin sintetizar en la Capa 2. Regla de la Capa 3: queda como fuente disponible hasta que un bloque del plan la requiera.

## [2026-08-05 21:10] bloque-pendiente | S10-B4

- Evidencia: `analizador-produccion/analizador_produccion.py` (sin modificar) y `analizador-produccion/datos/prueba_falta_columna.csv` (nuevo, escrito por él).
- Verificación: ejecución observada en cuatro caminos, reportada por él, más lectura directa de `salidas/` por el tutor antes y después.
- Nota: [[37 - S10-B4 - Probar rutas validas e invalidas]]
- Índice actualizado: sí, dentro de «Semana 10 — Programa de consola».
- Evidencia que falta para validar: la explicación con sus palabras. Pidió la explicación de forma explícita y, tras recibirla, siguió diagnosticando el segundo fallo como «tenemos mal la ruta». Los dos diagnósticos son del tutor, no suyos. Debe preguntarse **en frío, en un chat nuevo**: por qué un CSV sin una columna revienta dentro de `calcular_resumen_por_producto` y no al abrir el archivo, y por qué el mismo comando funciona desde `analizador-produccion/` y falla desde la carpeta de arriba.
- Objetivo del bloque cumplido en lo ejecutable: encontró dos entradas que revientan el programa con traceback, ninguna cubierta hasta hoy. CSV con siete columnas en vez de ocho, sin `producto`, da `KeyError: 'producto'` en la línea 46 después de haber impreso `Registro válidos: 1`. Ejecutar desde la carpeta de arriba con la ruta de entrada correcta da `FileNotFoundError` en la línea 125, al **escribir** los reportes, no al leer.
- Hallazgo verificado leyendo los archivos, no supuesto: tras el `KeyError`, `resumen_por_producto.csv` quedó solo con la cabecera porque el modo `"w"` lo vacía antes de escribir, mientras los otros dos reportes conservaban datos de la corrida anterior. Los tres dejaron de contar la misma historia sin aviso. Se repararon volviendo a ejecutar el camino bueno desde `analizador-produccion/`: `440 28 412 34` y código 0.
- Choque de códigos detectado y no resuelto: las dos roturas terminan con el `1` por defecto de Python al morir con excepción no atrapada, que colisiona con `SALIDA_NO_EXISTE_ARCHIVO = 1` de S10-B3. Es el argumento concreto para las validaciones del paso previo a S11-B1.
- Lo único que enunció él: «no identificamos que falta una variable», es decir, que no existe código de salida para un archivo mal formado. Es la semilla de la Semana 11 y se le reconoció como suyo.
- Tercer incidente de lanzador en la Semana 10: ejecutó el primer comando en cmd en vez de PowerShell. El `;` no separa en cmd, se pegó al nombre del archivo y el programa contestó `No existe un archivo llamado: datos/prueba_falta_columna.csv;`. Se detectó por el punto y coma final del mensaje y por el prompt `C:\...>` en lugar de `PS C:\...>`. Sirvió de ejemplo real del eje 2 que él mismo había propuesto.
- Dificultades de comprensión del bloque: sus primeros casos propuestos eran todos la ruta con distinta ropa; confundió el eje del contenido con la salida, creyendo que el CSV de entrada podría sobrescribirse; y atribuyó el `KeyError` a `DictWriter` en lugar de `DictReader`. Los tres ejes hubo que dárselos explícitos.
- `datos/prueba_falta_columna.csv` queda versionado a propósito: es fixture útil tal cual para las ocho validaciones del paso previo a S11-B1.
- La barra semanal no sube: sigue en 3 de 4 bloques validados. La evaluación semanal de la Semana 10 no se ejecuta hasta que S10-B4 quede validado.

## [2026-08-05 21:45] avance-de-bloque | S10-B4

- Nota: [[37 - S10-B4 - Probar rutas validas e invalidas]] — sigue en `pendiente-de-validacion`.
- Erick pidió resolver la explicación en esta misma sesión en lugar de esperar al chat nuevo. Se le advirtió una vez que preguntarlo en caliente mide memoria de conversación y no comprensión; decidió seguir y se respetó su decisión. Queda anotado que la demostración fue en caliente.
- **Primera rotura explicada por él.** Sobre por qué el CSV sin columna revienta en la línea 46 y no al abrir el archivo, llegó con analogía propia: «yo llamo a un auxiliar a buscar un archivo que otra persona debió entregar, pero esa persona no lo entregó; entonces al decirle al auxiliar que lo busque y no encuentra, me señala que ese archivo no está». Cerró con la distinción correcta al contrastarle clave inexistente contra clave presente y vacía: «no existe producto, ni el contenido de él». Le costó tres intentos y en dos de ellos atribuyó la lectura a `DictWriter` en vez de `DictReader`; el error de nombre se corrigió, la idea es suya.
- **Segunda rotura no explicada.** Sobre por qué el mismo comando falla desde otra carpeta, sus dos intentos fueron «tendría que ejecutar un comando para volver, así funciona la terminal» y «pienso que está buscando la clave o algo escribí en la terminal, no me fijé». La explicación de las rutas relativas es del tutor. Queda como única pregunta pendiente para el arranque de la Semana 11.
- Señal de fatiga clara al final de la sesión: mayúsculas involuntarias, «no me fijé», y respuestas que mezclaban la rotura anterior con la nueva. La sesión ya había cubierto un cierre de bloque completo (S10-B3), la incorporación de una fuente a la Capa 1 y todo el trabajo de descubrimiento de S10-B4. Se paró ahí en lugar de insistir.

## [2026-08-05 22:40] bloque-pendiente | paso-previo-S11-B1

- Evidencia: `analizador-produccion/analizador_produccion.py`, líneas 8-9 y 92-99.
- Verificación: ejecución observada por él y repetida por el tutor sobre el archivo guardado, más tres casos límite probados por el tutor con archivos temporales.
- Nota: [[38 - Paso previo a S11-B1 - Validar la cabecera del CSV]]
- Índice actualizado: sí, sección nueva «Semana 11 — Validaciones y pruebas».
- Erick pidió no cerrar la sesión y seguir trabajando. Como la pregunta pendiente de S10-B4 no podía medir nada en caliente, se abrió en su lugar el paso previo a S11-B1. Escribió la primera de las nueve validaciones: `SALIDA_FALTA_DATO = 4`, la lista `COLUMNAS_OBLIGATORIAS` con los ocho nombres, y las dos comprobaciones encadenadas entre el `DictReader` y el bucle de filas.
- Resultado comprobado: `prueba_falta_columna.csv` pasa de `KeyError` con código 1 a `Falta la columna obligatoria: producto` con código 4, sin traceback y sin tocar `salidas/`. `produccion.csv` sigue en `440 28 412 34` y código 0. Las 4 pruebas siguen pasando.
- Pylance señaló `lector.fieldnames` y esta vez el aviso **era real**, no como el falso positivo conocido de `tests/test_resumen_por_turno.py`: si el archivo está vacío, `fieldnames` vale `None` y `not in` lanzaría `TypeError`. Se cubrió con una guardia previa. Verificado por el tutor con un CSV de 0 bytes: imprime `El archivo no tiene cabecera` y devuelve 4.
- **Objeción suya, y era correcta:** al proponerle la guardia de `None` entendió que sustituía a su bucle y avisó de que así se perdería el mensaje que dice qué columna falta. No sustituía —va delante y encadena—, pero la observación era buena y defendía lo importante. Queda registrado como acierto propio.
- **Dos hallazgos abiertos, ninguno resuelto.** Primero: un CSV correcto guardado en UTF-8 **con BOM**, que es como exporta Excel, se rechaza con `Falta la columna obligatoria: id_registro` porque los tres bytes iniciales se pegan al primer nombre de columna. Se corregiría con `encoding="utf-8-sig"`. Segundo: un CSV con cabecera correcta y ninguna fila de datos pasa la validación, produce totales en cero, **sobrescribe los tres reportes** con contenido vacío y devuelve 0 como si todo hubiera ido bien.
- Fricción de método corregida en esta sesión, y él la nombró: «vamos paso a paso, que si me dices que haga algo me pierdo» y «para cada explicación tienes que ser literal». Describirle el objetivo de una tarea no basta; hay que darle la línea exacta, dónde va y el comando exacto, dejándole lo que hay que decidir. Guardado en la memoria persistente del asistente.
