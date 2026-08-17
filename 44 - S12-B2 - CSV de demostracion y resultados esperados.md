---
tags: [python, aprendizaje, semana-12, bloque-2]
tipo: bloque
semana: 12
bloque: S12-B2
estado: validado
fecha: 2026-08-17
---

# S12-B2 - CSV de demostración y resultados esperados

## Objetivo

Construir un CSV de ejemplo pequeño y escribir, **antes de ejecutar el programa**, los
resultados que debería producir; después contrastar ambas fuentes.

## Conocimiento esencial

- **Verdad de referencia (*ground truth*): un resultado calculado después de ver la salida
  no es una comprobación, es una copia.** Es el principio de S11-B1 —una prueba que pasa no
  dice nada hasta verla fallar cuando debía— aplicado a los datos en lugar de al código.
  Para saber si un número es correcto hace falta una segunda fuente independiente.
- **Método para elegir números de prueba limpios, y el orden importa:** fijar primero
  `unidades_producidas` y `unidades_defectuosas`, restar para obtener las buenas, y solo
  entonces elegir `horas_trabajadas` entre los divisores de ese resultado. Al revés hay que
  confiar en la suerte. Un caso cuyos porcentajes son redondos delata un error de cálculo;
  uno con `100/110 = 90,909…%` lo esconde.
- **Un agregado no hereda las propiedades de sus partes.** Las filas 1 y 3 del turno Mañana
  dan productividades enteras por separado (10 y 6), pero el turno suma 120 buenas entre 18
  horas y da 6,67. Refuerza por otra vía lo demostrado en la nota 42: el agregado no se
  puede calcular durante la lectura.
- **Antes de cruzar dos fuentes hay que comprobar que ambas filtran igual.** El desfase entre
  Excel y el programa en el turno Tarde no era un error de ninguno de los dos: Excel suma lo
  que hay en el archivo, el programa suma lo que pasó la validación. `SUMAR.SI` no sabe nada
  de las reglas de validación, y un `groupby` de pandas sobre datos sin limpiar dará el mismo
  desfase sin avisar.
- **Un campo que no participa en ningún cálculo puede cambiar todos los números.** `fecha` no
  se suma ni se divide ni aparece en los reportes, pero su ausencia en la fila 4 borra esa
  fila entera de las cuentas del turno Tarde.

## Lo que construyó el estudiante

`analizador-produccion/datos/demo.csv`: seis filas de datos con la cabecera de
`produccion.csv`. Meta fija en 160 en todas las filas —decisión suya, y buena: fija el
denominador y hace comparables los cumplimientos de un vistazo—, turnos repetidos dos veces
cada uno para que los reportes por turno tengan que sumar de verdad, y la fila 4 con la
`fecha` vacía como caso de rechazo.

Las cinco filas sanas cumplen las tres cuentas limpias, verificadas una por una:
`producidas / meta` da porcentaje redondo, `defectuosas / producidas` también, y
`(producidas - defectuosas) / horas` da entero.

`analizador-produccion/datos/demo_esperado.md`: la verdad de referencia escrita, con tres
apartados —los conteos esperados, la tabla de los tres turnos en Markdown, y dos notas—.
Los nueve números de la tabla coinciden con `resumen_por_turno.csv`. La tabla se construyó
primero en Excel con `SUMAR.SI` **antes de ejecutar el programa**, y se pasó a Markdown
después de contrastarla.

Las dos notas del final son las que un CSV no podría llevar, y son la mitad del valor del
documento: que la fila 4 se descarta por falta de fecha, y que el reporte por turno no
calcula tasa de defectos.

## Evidencia

- Archivos: `analizador-produccion/datos/demo.csv` y
  `analizador-produccion/datos/demo_esperado.md`
- Revisión: leídas las seis filas y comprobadas a mano las tres cuentas de cada fila sana.
  Los nueve números de `demo_esperado.md` verificados uno por uno contra
  `salidas/resumen_por_turno.csv`.
- Ejecución: **observada.** `python .\analizador_produccion.py .\datos\demo.csv` da
  `Registros válidos: 5` y `Registros rechazados: 1`, que coincide con lo que él predijo
  antes de ejecutar. `Get-ChildItem .\salidas\` confirma los tres reportes regenerados
  (8/17 9:43). `resumen_por_turno.csv` da Mañana 160/18/120/6.67, Noche 200/20/100/5.0,
  Tarde 80/10/20/2.0.
- Explicación: **demostrada en el punto central del bloque.** Diagnosticó él la discrepancia
  entre su tabla y el reporte: «en Tarde en el programa no la suma porque le falta la fecha
  a uno». Tres pasos encadenados —la fila no pasa la validación, por eso no entra en el
  agregado, por eso las dos fuentes difieren sin que ninguna esté rota.
- Método de validación: contraste de dos fuentes independientes (tabla escrita a mano antes
  de ejecutar, contra la salida real del programa) más ejecución observada. Suite completa:
  `python -m pytest tests/` da **11 passed**.

## Errores y correcciones

- **Primera versión del `demo.csv`: los mismos números de `produccion.csv` con las fechas
  cambiadas.** No servía, y el motivo es de método: esos resultados ya los había visto salir
  por pantalla muchas veces, así que escribirlos habría sido recordar, no predecir. Es el
  problema del chat contaminado (notas 37 y 42) trasladado a los datos.
- Segunda versión: números redondos pero la fila 3 con `50 / 12 = 4,1666…`. Corregida a 10
  horas. **El fallo lo señaló el tutor al hacer la cuenta que él no llegó a hacer**; la
  pregunta se le formuló pero no la contestó.
- Comillas en todos los campos de texto y en la cabecera, en las dos primeras versiones. Las
  quitó él. El origen se descubrió después: Excel.
- **Su tabla de esperados falló en dos turnos, y ese fallo es el hallazgo del bloque.** En
  Noche contó una sola fila de las dos (80 en vez de 200); en Tarde sumó la fila descartada
  (120 en vez de 80). El primero lo corrigió pasando de sumar a ojo a usar `SUMAR.SI`; el
  segundo resultó no ser un error suyo sino la diferencia de filtro entre las dos fuentes.
  **Sin tabla escrita, el 200 del reporte habría pasado sin que nadie lo mirara.** A la
  pregunta de por qué una tabla que se equivoca sigue siendo mejor que no tenerla contestó
  «por este error»; la formulación completa —el error sale a la luz al chocar con otra
  fuente, y una fuente sola nunca discrepa consigo misma— la puso el tutor.
- **Al escribir `demo_esperado.md` hizo falta revisarlo tres veces, y el patrón es el mismo
  que en S11-B3: al sustituir un bloque, sobra lo viejo o falta parte de lo nuevo.** Primera
  versión: tabla escrita con comas en lugar de sintaxis Markdown. Segunda: la tabla nueva
  correcta, pero **desaparecieron las filas de Noche y Tarde** y quedó además la vieja
  cabecera con comas encima. Tercera: recuperadas las filas, la cabecera sobrante seguía ahí.
  Cuarta: limpio. Ninguno de los tres tropiezos fue de contenido —los nueve números fueron
  correctos desde el principio—, todos de reemplazo incompleto. Se corrige mirando el archivo
  completo después de editar, no solo la parte recién escrita.
- **`datos/produccion.csv` quedó modificado sin que él lo pretendiera: lo abrió en Excel
  para hacer el `SUMAR.SI` y al guardar Excel le puso comillas a todos los campos de texto y
  le cambió las seis fechas.** El criterio de aceptación nº4 de `PROYECTO.md` —el archivo
  original nunca se sobrescribe— lo cumple el programa, pero no lo cumplió Excel. Quitó él
  las comillas; las fechas se restauraron con `git restore` a petición suya, porque no
  recordaba las originales. `11 passed` después de restaurar. **Abrir un CSV en Excel no es
  una operación de solo lectura.**

## Pendiente

- **Hallazgo abierto, y es suyo: `resumen_por_turno.csv` no calcula tasa de defectos.** Su
  tabla llevaba esa columna y el reporte no la trae —solo producidas, horas, buenas y
  productividad—. Su predicción del 25% para Mañana no era falsa: era una columna
  inexistente. Sin decidir si se añade al programa o se documenta como límite.
- La `ñ` de «Mañana» sale partida en dos caracteres al leer el reporte con `Get-Content` en
  PowerShell. Es la consola mostrando UTF-8 como cp1252, no un defecto del archivo. Sin
  resolver, sin impacto en los datos. (La secuencia no se reproduce aquí a propósito: el
  verificador de codificación del vault la detectaría como si la nota estuviera corrupta.)
- Sigue abierto de la Semana 12: S12-B4 (demostración y retrospectiva) y la validación
  semanal 12, que pide que **otra persona ejecute el programa usando solo el README**. Se le
  avisó al abrir el bloque para que vaya buscando a quién pedírselo.

## Conexiones

- [[42 - Cierre del proyecto - Explicar el flujo principal]]
- [[43 - S11-B4 - Corregir errores y simplificar el codigo]]
- [[39 - S11-B1 - Aprender pruebas unitarias basicas]]
- [[Próxima ruta - Análisis de datos (post-fundamentos)]]
- [[Python desde 0 - Índice]]
