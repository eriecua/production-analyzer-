---
tags: [python, aprendizaje, semana-12, bloque-4]
tipo: bloque
semana: 12
bloque: S12-B4
estado: validado
fecha: 2026-08-17
---

# S12-B4 - Demostración y retrospectiva

## Objetivo

Demostrar el analizador de punta a punta con entradas válidas e inválidas, y escribir la
retrospectiva del proyecto.

## Conocimiento esencial

- **Su propio diagnóstico, y es el hallazgo del bloque: los conceptos por separado están, lo
  que cuesta es la integración de uno dentro de otro.** Sus palabras: «los conceptos uno por
  uno los sé, pero la integración de esos conceptos, un concepto dentro de otro concepto, es
  lo que más me dificulta». Nombró tres dificultades por separado —diccionarios,
  acumuladores, `for`— y luego vio solo que las tres son la misma: un diccionario dentro de
  un bucle con un acumulador dentro no es la suma de tres conceptos, es uno nuevo. Explica
  por qué `datos[turno]["unidades"]` de S11-B4 costó tanto y por qué la segunda función salió
  sin esqueleto.
- **«El 20 % es código y el 80 % es manejo de errores.»** Conclusión suya sobre el proyecto
  completo. Nadie la formula en la Semana 1; se aprende chocando con entradas reales.
- **La distinción entre no entender y no recordar, aplicada a él mismo.** Sobre `try`: sabe
  para qué sirve —«cuando sucede un error»— y no recuerda cómo se escribe. Son dos problemas
  con remedios distintos: el segundo se recupera reconstruyendo, no releyendo. Escribió
  cuatro `except` distintos en este programa (`FileNotFoundError`, `PermissionError`,
  `ValueError`, `UnicodeDecodeError`), el último por transferencia ante un error nunca visto.
- **`git status` en silencio es una prueba, no una ausencia de resultado.** Que no diga nada
  sobre `datos/produccion.csv` después de ejecutar es la verificación del criterio nº4 de
  `PROYECTO.md`. La misma comprobación había fallado horas antes, cuando Excel reescribió el
  archivo: mismo comando, resultado opuesto.

## Lo que construyó el estudiante

Nada nuevo: el bloque es de demostración. El entregable es la evidencia de que el programa
terminado se comporta como debe ante cinco entradas distintas, y la retrospectiva.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py` (sin cambios en este bloque).
- Ejecución: **observada, cinco entradas y las pruebas**, todas en esta sesión y con
  `; $LASTEXITCODE` a la vista:
  - `demo.csv` → `Registros válidos: 5`, `Registros rechazados: 1`, código **0**. Los nueve
    números de `salidas/resumen_por_turno.csv` coinciden con `datos/demo_esperado.md` sobre un
    reporte recién generado, no sobre el de una ejecución anterior.
  - `produccion.csv` → 5 válidos, 1 rechazado, código **0**, y `git status --short` sin
    salida: el original intacto.
  - `prueba_falta_columna.csv` → `Falta la columna obligatoria: producto`, código **4**.
  - `prueba_campo_vacio.csv` → 1 válido, 1 rechazado, código **0**.
  - `produccion_falla.csv` → `Falta la columna obligatoria: id_registro`, código **4**.
  - `python -m pytest tests/` → **11 passed**.
- Explicación: **demostrada.** Retrospectiva dada por él en audio, con los tres puntos
  pedidos y sin apoyo del tutor.
- Método de validación: ejecución observada de las cinco entradas más la suite completa, y
  retrospectiva oral.

## Errores y correcciones

- **Diagnóstico equivocado del tutor, corregido mirando el archivo.** Ante
  `Falta la columna obligatoria: id_registro` de `produccion_falla.csv`, el tutor sospechó el
  BOM de Excel —el síntoma es idéntico, porque el BOM se pega al primer nombre de columna—.
  Se comprobó con `Get-Content -TotalCount 1` y la cabecera real es
  `turno,producto,horas_trabajadas`: le faltan cinco columnas de verdad. El comportamiento
  del programa era correcto; lo erróneo era la suposición de que ese archivo servía para
  probar filas malas.
- **Se le propuso hacer él mismo la validación semanal y se rechazó, con motivo.** Ejecutar
  su propio programa «usando solo el README» no mide nada: ya sabe lo que el README no dice
  —que hay que estar en `analizador-produccion/`, que el argumento es una ruta a un CSV, que
  el botón de VS Code no sirve—. Es el problema del chat contaminado por cuarta vez. Se le
  ofrecieron dos vías: una persona con Python instalado, o un chat de Claude en frío con solo
  el README.
- **Corrección de un dato del tutor.** Se había dicho que S12-B3 estaba «cumplido de facto»;
  el plan de ProjectLibre lo marca al 0 %. El README existe y él lo revisó línea por línea el
  2026-08-13, pero el porcentaje lo lleva él.

## Su retrospectiva

**Lo que puede hacer hoy y en la Semana 1 no:** funciones con `def`, condicionales,
diccionarios, variables, bucles `while` con `break`, `for`, acumuladores, leer CSV y manejar
errores. Su añadido: «con otro tipo de proyectos ya podría afinar esto».

**Lo que más costó:** los diccionarios, y en concreto los anidados dentro de funciones y
bucles. También los acumuladores y el `for`.

**Deuda consciente, dicha por él:** los diccionarios necesitan más ejercicios; quiere conocer
mejor los `import` y las herramientas —«entiendo que es una herramienta, pero quisiera
conocer más»—; no recuerda cómo se escribe `try`; y la integración de conceptos entre sí es
lo que más pesa.

## Pendiente

- **La `VALIDACIÓN SEMANAL 12` sigue abierta y no la cierra este bloque.** Pide que *otra
  persona* ejecute el programa usando solo el README. Al cierre de S12-B4 no tiene a nadie
  todavía. **La Semana 12 no está completa.**
- **Deuda de retención, ya vista el 2026-08-13 y confirmada por él hoy:** no recuerda la
  forma de `try`/`except` aunque escribió cuatro ramas en este programa. Es conocimiento
  procedimental, no conceptual; se recupera reconstruyendo de memoria, no releyendo la
  explicación. Conviene un repaso de su propio código al abrir material nuevo.
- **Su dificultad nombrada —la integración de conceptos— debe gobernar el diseño de la ruta
  de pandas.** No introducir conceptos aislados y confiar en que los combine: los ejercicios
  tienen que ser de composición desde el principio.
- Observación registrada, sin abrir tarea: el programa reporta **una** columna faltante y no
  la lista completa. Con `produccion_falla.csv`, al que le faltan cinco, quien reciba el
  mensaje arreglará `id_registro`, volverá a ejecutar y se encontrará `fecha`, cinco veces.
  El mensaje es cierto y el código de salida correcto; el proyecto está cerrado y no se
  reabre.
- Sigue abierto de antes: `resumen_por_turno.csv` no calcula tasa de defectos (hallazgo suyo
  de S12-B2), y el fallo silencioso de la carpeta `salidas` creada en el nivel de arriba
  (hallazgo suyo de S10-B4).

## Conexiones

- [[44 - S12-B2 - CSV de demostracion y resultados esperados]]
- [[43 - S11-B4 - Corregir errores y simplificar el codigo]]
- [[42 - Cierre del proyecto - Explicar el flujo principal]]
- [[Próxima ruta - Análisis de datos (post-fundamentos)]]
- [[Python desde 0 - Índice]]
