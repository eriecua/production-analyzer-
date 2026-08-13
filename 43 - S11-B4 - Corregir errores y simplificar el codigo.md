---
tags: [python, aprendizaje, semana-11, bloque-4]
tipo: bloque
semana: 11
bloque: S11-B4
estado: validado
fecha: 2026-08-13
---

# S11-B4 - Corregir errores y simplificar el codigo

Cierra la Semana 11. Se hizo el mismo día que
[[42 - Cierre del proyecto - Explicar el flujo principal]], después de ver el plan de
ProjectLibre y comprobar que S11-B4 seguía sin hacer.

## Objetivo

Reescribir por dentro las dos funciones de resumen con una estructura de datos mejor, sin
que se rompa ninguna de las once pruebas.

## Conocimiento esencial

- **Un diccionario cuyo valor es otro diccionario.** En vez de tres o cuatro diccionarios
  paralelos con un dato cada uno, uno solo donde cada clave guarda una ficha con todos sus
  campos juntos: `datos[turno]["unidades"]`. Cada corchete entra un nivel más adentro; no
  hay sintaxis nueva, es el mismo `[ ]` dos veces.
- **Es la estructura de una fila de pandas.** Una clave y, colgando de ella, un registro con
  varios campos. No es una analogía: es la misma forma.
- **Los diccionarios paralelos son una trampa de mantenimiento.** Añadir un campo obligaba a
  tocar cuatro sitios distintos, y olvidar el de la inicialización revienta con `KeyError`.
  Con la ficha única, el `if` crea todos los campos de golpe.
- **Un error puede esconderse detrás de otro.** El `NameError` de la segunda mitad tapaba un
  error de datos real en la primera. Solo se ve el primero de la fila.
- **Para eso servían las once pruebas.** Cambiar por dentro una función que ya funciona es
  el momento más peligroso que hay, porque no se nota. Aquí se supo en 0,03 segundos que el
  comportamiento no había cambiado.

## Lo que construyó el estudiante

Refactorizó **las dos** funciones de resumen:

- `calcular_resumen_por_turno`: tres diccionarios paralelos (`unidades_por_turno`,
  `horas_por_turno`, `buenas_por_turno`) reducidos a `datos_turno`, con ficha
  `{"unidades": 0, "horas": 0, "buenas": 0}`.
- `calcular_resumen_por_producto`: cuatro diccionarios reducidos a `datos_producto`, con
  ficha de cuatro campos y las **dos** guardias de división leyendo del nuevo diccionario.
- Corregidos los dos `print` del final de la lectura: «Registro válidos» → «Registros
  válidos», y lo mismo con los rechazados.

## Lo que demostró el estudiante

- **Enumeró solo los cuatro puntos de toque** del problema antes de que se le dijera cuál
  era: declarar el diccionario vacío, inicializarlo dentro del `if`, acumular en el bucle y
  añadirlo al diccionario `fila`. Acertó además que `COLUMNAS_OBLIGATORIAS` no se toca,
  porque esa columna ya se lee.
- **Hizo la segunda mitad de la primera función sin que se le pidiera.** El encargo era solo
  la parte que acumula; entregó la función entera, con las líneas de lectura ya adaptadas a
  los dos corchetes y correctas.
- **Propuso él la transferencia:** *«y también lo podemos hacer con productos»*, antes de
  que se le planteara. La hizo **sin esqueleto y sin errores**, en la función más grande
  —cuatro campos y dos guardias en vez de tres y una—.
- **Explicó la ganancia con sus palabras**, y la frase da en el clavo: *«en `datos_turno` se
  acumula el turno, y siempre va a tener unidades, horas y buenas»*. Los datos de un turno
  viajan juntos; ya no depende de que él se acuerde de mantener tres diccionarios
  sincronizados.

## Errores y correcciones

- **Las tres líneas de acumulación escribían en la misma carpeta.** Copió la primera y no
  cambió la clave, así que unidades, horas y buenas se sumaban todas en `["unidades"]`.
  Causa dicha por él: *«copié para evitar escribir a mano»*. Se le señalaron las tres líneas
  juntas y lo vio de inmediato. Habría producido un reporte por turno con números
  inventados.
- **Ese error estuvo tapado por el `NameError`.** Las pruebas fallaban por la segunda mitad
  aún sin migrar, no por las carpetas. Se comprobó con una prueba de mutación deliberada
  —devolver `"unidades"` a la línea de las horas con la función ya sana—: salió
  `1 failed, 10 passed` con `assert 480 == 460`. Los 20 de más eran las horas de las dos
  filas de mañana metidas en el cajón equivocado.
- Preguntado qué ocurre al hacer `d['Mañana'] += 5` sobre un diccionario vacío, contestó que
  quedaría «código muerto». Lo comprobó con `python -c` y obtuvo `KeyError: 'Mañana'`.

## Lo que necesitó ayuda

- **La sintaxis anidada `datos[turno]["unidades"]` se la dio el tutor.** Ante la pregunta de
  cómo escribirla dijo «no lo sé», que era la respuesta honesta: no la había visto nunca.
  Sí escribió después, por su cuenta, la versión con la variable `turno`.
- **El primer refactor se hizo con esqueleto de huecos.** El segundo no, y ahí está la
  evidencia.
- **La lectura del fallo de la mutación.** Dijo *«no entiendo mucho esos test»* y se le trazó
  de dónde salían los 480. Después lo reformuló bien: *«mete las horas que son enteras,
  entonces la suma da 480 y no los 460 que se esperan»*. Comprensión conseguida, pero
  después de la traza, no antes.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py`, funciones
  `calcular_resumen_por_turno` (líneas 14-38) y `calcular_resumen_por_producto`
  (líneas 40-71).
- Revisión: el tutor leyó las dos funciones completas tras cada refactor.
- Ejecución: **observada**. `python analizador_produccion.py datos/produccion.csv` da
  5 válidos, 1 rechazado y código 0; `salidas/resumen_por_producto.csv` conserva las mismas
  cifras que antes del cambio (Producto A: 91,67 % de cumplimiento, 7,73 % de defectos).
- Pruebas: `python -m pytest tests/` da **11 passed** después de los dos refactores.
- Prueba de mutación: ejecutada, `1 failed, 10 passed`, revertida y vuelta a verde.
- Explicación: **demostrada**.
- Método de validación: pruebas automatizadas como red de seguridad del refactor, más
  ejecución del programa completo comparando la salida con la anterior.

## Pendiente

Nada para este bloque. La Semana 11 queda completa.

## Conexiones

- [[42 - Cierre del proyecto - Explicar el flujo principal]]
- [[41 - S11-B3 - Probar validaciones]]
- [[39 - S11-B1 - Aprender pruebas unitarias basicas]]
- [[Capa 2 - Wiki/Próxima ruta - Análisis de datos (post-fundamentos)]]
- [[Python desde 0 - Índice]]
