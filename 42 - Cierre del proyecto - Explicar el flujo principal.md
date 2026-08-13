---
tags: [python, aprendizaje, semana-11, bloque-3, proyecto]
tipo: bloque
semana: 11
bloque: S11-B3
estado: validado
fecha: 2026-08-13
---

# Cierre del proyecto - Explicar el flujo principal

Cierra [[41 - S11-B3 - Probar validaciones]] y con él **el analizador de producción
completo**. Es el séptimo y último criterio de aceptación de `PROYECTO.md`, el único que no
puede cumplir el tutor.

## Objetivo

Que Erick cuente el recorrido de un CSV desde el comando en la terminal hasta los tres
archivos de `salidas/`, sin el código delante y **en un chat en frío**.

Lo de «en frío» no es un detalle de forma. La sesión del 2026-08-11 explicó cada pieza del
programa, así que preguntarlo allí habría medido la memoria de la conversación. Esta sesión
se abrió sin haber explicado nada previamente, y él no abrió el archivo.

## Conocimiento esencial

- **Un indicador agregado no se puede calcular mientras se lee.** La productividad de un
  turno necesita todas las filas de ese turno, y mientras el archivo sigue abierto no se
  sabe cuántas quedan. De ahí sale la forma del programa entero: leer y acumular primero,
  calcular después.
- **La columna vertebral: revisar → acumular → calcular → escribir.** Durante la lectura el
  programa no calcula; revisa cada fila, descarta las malas y guarda las buenas en una
  lista. Cuando el archivo se acaba, recorre lo guardado.
- **Escribir reportes vacíos es peor que fallar.** Unos reportes de ceros sustituyen a los
  correctos del día anterior y nadie se entera: el dato incorrecto tiene la misma cara que
  el correcto. Es un **fallo silencioso**, y por eso la guardia de cero registros válidos
  está antes de abrir ningún archivo de salida.
- **Contar rechazos no es explicarlos.** El programa dice *cuántas* filas se cayeron, no
  *cuáles* ni por qué. Con 153 de 2.000 hay que abrir el CSV a mano. Es una limitación real
  y aceptada, y es justo el problema que resuelve pandas.

## Lo que demostró el estudiante

Narración suya, sin ayuda, con el archivo cerrado:

1. Comprobar que se dio la ruta como argumento. Lo ancló a una observación propia: el botón
   ▶ de VS Code lanza el programa pelado, y por eso siempre sale el mensaje de uso.
2. Abrir el CSV y validar la cabecera contra la constante de columnas obligatorias, antes de
   mirar ninguna fila de datos.
3. Revisar fila a fila; la mala se rechaza y se cuenta, sin detener el programa.
4. Guardar las buenas en una lista.
5. Al acabar el archivo, calcular.
6. Informar de válidos y rechazados.

Frase suya, cuando se le pidió completarla:

> «Por cada fila que lee, el programa la lee, y si está bien la guarda en una lista. Cuando
> el archivo se acaba, entonces la calcula.»

**El hallazgo del bloque, y llegó con un ejemplo propio.** Se le dio una tabla de tres filas
—dos del turno mañana— y se le preguntó qué productividad saldría si el programa la
escribiera tras leer solo la primera. Sumó por su cuenta las dos filas de mañana, sumó sus
horas y las dividió, y vio que el número no coincide con el de la fila 1 aislada. De ahí
concluyó que el cálculo no puede ocurrir durante la lectura. La aritmética le falló (dijo 30
donde salía 15); **el método era correcto y es lo que se registra.**

**Explicó el fallo silencioso desde su objetivo profesional**, sin que se le pidiera ese
enfoque: *«si los datos de antes están bien pero el archivo lo va a reemplazar, entonces la
información es incorrecta [...] tiene que haber una coherencia.»* El nombre técnico lo puso
el tutor; el razonamiento es suyo.

**Nombró la limitación de los contadores por sí mismo.** Ante `1.847 válidos / 153
rechazados`: *«para ver los registros rechazados tendría que ir al CSV y revisarlos».*

### Lo que necesitó ayuda

Se registra aparte, como en la nota 41:

- **Su primera respuesta al momento del cálculo fue «durante la lectura».** Se corrigió sola
  con el ejemplo de las tres filas, pero la respuesta inicial era incorrecta.
- **Creía que el caso «campo vacío en una fila» no estaba definido en el programa**, y lo
  escribió él en la sesión anterior. Retención floja de su propio código a dos días.
- **Su relato final se paró antes de escribir los reportes.** Llegó hasta «calcula al final»
  y cerró con «esto sería todo». Los tres reportes y sus nombres los dio a continuación, ya
  con una pregunta directa. La columna vertebral es suya sin ayuda; el paso de escritura,
  solo tras preguntárselo.

## Deuda saldada en esta sesión

**Revisó el README línea por línea** —requisitos, formato de entrada, validaciones, los tres
reportes, la tabla de códigos de salida, la estructura y las limitaciones conocidas— y lo
dio por bueno. Con eso queda cerrado el punto 2 del «Pendiente» de la nota 41, abierto desde
el 2026-08-11 porque el README lo redactó el tutor.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py` y
  `analizador-produccion/README.md`.
- Revisión: el tutor contrastó el README contra el código —tabla de códigos de salida, lista
  de validaciones y fórmulas de los indicadores— antes de pedirle la suya.
- Ejecución: `python -m pytest tests/` da **11 passed**, comprobado en esta sesión.
- Explicación: **demostrada**, en chat en frío y sin el archivo abierto.
- Método de validación: explicación oral contrastada contra el código por el tutor, con dos
  preguntas discriminantes que no se pueden contestar de memoria (el ejemplo de las tres
  filas y el caso de las cuarenta filas malas).

## Estado del proyecto

**Los siete criterios de aceptación de `PROYECTO.md` se cumplen.** Los seis primeros ya
estaban verificados por ejecución el 2026-08-11; el séptimo se cumple hoy.

Quedan como deuda documentada en el README, aceptada por decisión suya: fechas inválidas e
identificadores duplicados. 7 de las 9 reglas de validación implementadas.

## Pendiente

- La nota [[38 - Paso previo a S11-B1 - Validar la cabecera del CSV]] sigue **pendiente de
  validación**. Hoy dijo bien que la cabecera se comprueba antes de leer datos y que las
  columnas obligatorias viven en una constante, pero **no se le preguntó por la guardia de
  `fieldnames is None`**, que es lo que le faltaba. Queda como está: no se da por saldada.
- Lo siguiente ya no es el analizador. Material nuevo hacia su objetivo: análisis de datos
  con pandas. Ver `Capa 2 - Wiki/Próxima ruta - Análisis de datos (post-fundamentos)`.

## Conexiones

- [[41 - S11-B3 - Probar validaciones]]
- [[40 - S11-B2 - Probar calculos y limites]]
- [[39 - S11-B1 - Aprender pruebas unitarias basicas]]
- [[37 - S10-B4 - Probar rutas validas e invalidas]]
- [[Python desde 0 - Índice]]
