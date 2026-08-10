---
tags: [python, aprendizaje, semana-11, bloque-2]
tipo: bloque
semana: 11
bloque: S11-B2
estado: validado
fecha: 2026-08-10
---

# S11-B2 - Probar cálculos y límites

## Objetivo

Cubrir con pruebas las ramas de límite de las funciones de cálculo y de `validar_cabecera`, y comprobar por mutación que esas pruebas de verdad vigilan algo.

## Conocimiento esencial

- **Una función que valida devuelve el motivo; no hace `sys.exit`.** `sys.exit` no es «devolver algo»: interrumpe el programa entero, y quien hizo la llamada nunca recibe el resultado. Una prueba de pytest es precisamente «quien hizo la llamada»: espera un valor para compararlo. Si la función se mata por dentro, no hay valor, no hay `assert` y la prueba no llega a existir. Formulación suya: **«estamos parando todo el tren, en lugar de hacer una parada donde se debe. Y nadie sabe por qué se paró el tren.»**
- **El reparto que se sigue de lo anterior.** La función decide y responde; el `if __name__ == "__main__":` decide qué hacer con esa respuesta —imprimir el mensaje y cortar con el código de salida—. Es lo que ya estaba escrito en el programa: `validar_cabecera` devuelve texto o `None` en las líneas 80-89, y el `sys.exit(SALIDA_FALTA_DATO)` vive fuera, en la línea 105.
- **Matiz que corrige la analogía del tren.** `sys.exit` sí deja una señal **fuera** del programa: el código que lee `$LASTEXITCODE`. Lo que no deja es nada **dentro**, para el código que hizo la llamada. La analogía explica el corte, no la ausencia total de información.
- **Auditar una función por sus salidas.** `validar_cabecera` tiene tres `return`: cabecera `None`, columna que falta, y todo correcto. Contar los `return` y emparejarlos con las pruebas es un método reutilizable para saber qué falta por cubrir. Se aplicó también a las dos funciones de cálculo: sus cuatro ramas de límite ya estaban cubiertas.
- **Un caso de prueba solo detecta los fallos que producen una respuesta distinta de la esperada en ESE caso.** Es la generalización del bloque, y explica los dos hallazgos de abajo.

## Los dos experimentos de mutación

### El caso sano no lo vigilaba nadie

Antes de hoy, la única prueba de `validar_cabecera` era `test_cabecera_sin_columna_producto`: le pasaba una cabecera sin `producto` y esperaba `"Falta la columna obligatoria: producto"`. Un `validar_cabecera` que ignorase la cabecera y **siempre** devolviera esa frase habría pasado sin despeinarse.

Se comprobó cambiando el `return None` de la línea 89 por `return "Falta la columna obligatoria: producto"`. Resultado observado: `1 failed, 8 passed`. Falló solo `test_cabecera_completa`, la escrita ese día, con `AssertionError: assert 'Falta la columna obligatoria: producto' is None`. **La prueba vieja pasó con la función saboteada.**

Coincidieron por casualidad: el mentiroso soltó su única frase justo cuando esa frase era la verdad. Es comprobar si un reloj parado funciona mirándolo a las 3:00.

### Hallazgo del bloque: las pruebas de lista vacía son débiles por naturaleza

Las dos pruebas de lista vacía venían de la sesión anterior y se habían dado por buenas sin verlas fallar nunca. Se les aplicó la mutación: cambiar `return filas_turno` (línea 40) por `return []`, es decir, una función que no calcula nada jamás.

Resultado observado: `2 failed, 8 passed`. Cayeron `test_resumen_por_turno` y `test_turno_sin_horas`, las dos con `IndexError: list index out of range` —la lista vacía no tiene posición `[0]`—. Y **`test_turno_sin_registros` pasó**, con la función destruida.

No es una prueba dormida como la de S11-B1: esa nunca podía fallar, y ésta sí fallaría si el código inventara una fila fantasma. Es un defecto distinto y también útil: **el resultado correcto de una lista vacía (`[]`) coincide con el resultado de no hacer nada.** Formulación suya: la prueba no puede distinguir «no había nada que calcular» de «no calculé nada». Solo vale acompañada de las pruebas que exigen contenido.

Su predicción antes de ejecutar fue parcial: acertó `test_resumen_por_turno` y no anticipó `test_turno_sin_horas`.

## Lo que construyó el estudiante

En `tests/test_validaciones.py`:

- `test_cabecera_completa`, escrita por él paso a paso: la lista con las ocho columnas y `assert validar_cabecera(cabecera) is None`. Es la prueba que cierra el agujero del caso sano.
- `test_cabecera_inexistente`, para la rama `cabecera is None`. **La dictó el tutor entera**; no cuenta como conocimiento demostrado por él.

Sobre `analizador_produccion.py` solo hizo las dos mutaciones temporales, ambas revertidas y verificadas.

Comprobaciones conceptuales resueltas durante el bloque: que el orden de los nombres en la lista de la prueba no importa, porque la línea 86 usa `in` —pertenencia, no posición—; y que se compara con `is` contra `None` y con `==` contra un texto.

## Evidencia

- Archivo: `analizador-produccion/tests/test_validaciones.py`, tres pruebas.
- Ejecución: observada en cinco corridas de `python -m pytest tests/`.
  - Nueve pruebas tras `test_cabecera_completa`: `9 passed`.
  - Mutación de la línea 89: `1 failed, 8 passed`, con `assert 'Falta la columna obligatoria: producto' is None`.
  - Revertida: `9 passed`.
  - Añadida `test_cabecera_inexistente`: `10 passed`.
  - Mutación de la línea 40 a `return []`: `2 failed, 8 passed`, las dos con `IndexError`.
- Comprobación final del tutor sobre los archivos guardados: la línea 40 vuelve a decir `return filas_turno`, la 89 `return None`, y `python -m pytest tests/ -q` da `10 passed`.
- Auditoría de ramas hecha por el tutor sobre las líneas 12-79: las cuatro ramas de límite de los dos cálculos —`horas_trabajadas == 0`, `meta_unidades == 0`, `unidades_producidas == 0` y lista vacía— tienen prueba. No queda ninguna huérfana.
- Explicación: **demostrada** para el principio de `sys.exit` y para el límite de las pruebas de lista vacía. Las dos con sus palabras.
- Método de validación: ejecución observada, dos pruebas de mutación y explicación propia.

## Errores y correcciones

- Al preguntársele por qué pytest recoge las funciones que empiezan por `test_`, respondió «porque nosotros en pytest ponemos test». Era una respuesta circular y se completó de inmediato: pytest **busca por nombre**, y una función llamada `comprobar_cabecera_completa` estaría ahí sin ejecutarse ni avisar. Es convención, no concepto a deducir.
- Confundió el nombre del parámetro con el valor que se le pasa: ante «¿qué le tienes que pasar a `validar_cabecera` para llegar a la primera salida?» respondió «¿o sea cabecera?». Se le dio la respuesta (`None`) por ser ambigüedad de vocabulario, no falta de comprensión.
- Ante la pregunta de qué `return` quedaba sin probar dijo «son muchas líneas de código, sería difícil identificar qué le falta». Lo que lo desbloqueó fue poner las ocho líneas de la función delante, en el mensaje, con las tres salidas marcadas. Reducir el terreno funcionó mejor que insistir en la pregunta.

## Interrupción de método que merece registro

A mitad del bloque preguntó: **«¿Qué objetivo de estudio tiene hacer todo esto? ¿Qué estoy aprendiendo realmente?»** Se paró el bloque y se respondió con el vínculo a su objetivo declarado: en análisis de datos no se puede comprobar a mano un CSV de 200.000 filas, así que las pruebas son la única forma de confiar en un número; y una prueba mal escrita da la misma luz verde que una buena, que es peor que no tener ninguna.

Su respuesta: «sigamos entonces, si esto de verdad tiene una utilidad práctica vale entenderlo». **Necesita ver la conexión con el trabajo real para sostener el esfuerzo en bloques que parecen mecánicos.** Conviene anticiparla al abrir bloques de este tipo en vez de esperar a que la pida.

## Pendiente

- Las **seis** validaciones que faltan de `PROYECTO.md` —campos vacíos, fechas inválidas, cantidades negativas, meta no positiva, horas no positivas e identificadores duplicados—, cada una emparejada con su prueba. Las dos últimas obligan a leer `id_registro` y `fecha`, hoy exigidos en la cabecera y nunca usados. Van en S11-B3.
- `test_cabecera_inexistente` no está demostrada por él: se le dictó.
- Siguen abiertos los dos hallazgos de la nota 38: el CSV en UTF-8 **con BOM** rechazado por el BOM pegado al primer nombre de columna, y el CSV con cabecera correcta y ninguna fila, que produce totales en cero y devuelve `0`.

## Conexiones

- [[39 - S11-B1 - Aprender pruebas unitarias basicas]]
- [[38 - Paso previo a S11-B1 - Validar la cabecera del CSV]]
- [[37 - S10-B4 - Probar rutas validas e invalidas]]
- [[Python desde 0 - Índice]]
