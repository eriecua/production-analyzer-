---
tags: [python, aprendizaje, semana-11, bloque-1]
tipo: bloque
semana: 11
bloque: S11-B1
estado: validado
fecha: 2026-08-06
---

# S11-B1 - Aprender pruebas unitarias básicas

## Objetivo

Hacer que una prueba falle a propósito, saber leer lo que pytest informa, y escribir una prueba nueva que cubra una guardia hasta ahora sin vigilar.

## Conocimiento esencial

- **pytest hace solo el trabajo de portero.** Entra en la carpeta, busca archivos que empiezan por `test_`, dentro busca funciones que empiezan por `test_` y las llama una a una. El prefijo no es decoración: es el mecanismo de reconocimiento. Se demostró borrando las llamadas manuales y los `print("OK - ...")` que él había escrito al final de los dos archivos, y comprobando que las cuatro pruebas seguían ejecutándose igual.
- **pytest sigue después de un fallo; un script no.** Con las llamadas manuales, la primera aserción rota mataba el archivo y las siguientes no se ejecutaban. `..F.` muestra las cuatro marcas y `1 failed, 3 passed` el recuento. Además reimprime la función entera con la línea culpable marcada con `>`.
- **En `assert 460 == 999`, el izquierdo lo calculó el programa y el derecho lo escribió él.** Formulación suya: «el programa buscó en el diccionario el valor de unidades producidas y comparó con la cantidad que yo escribí». De ahí se sigue que cuando una prueba falla hay que averiguar cuál de los dos lados miente; ese día mentía la prueba.
- **Una prueba que pasa no dice nada hasta que se la ha visto fallar cuando debía fallar.** Es el principio del bloque. Se comprueba con una **prueba de mutación**: se rompe a propósito lo que la prueba vigila, se confirma que salta, y se repara.
- **Una prueba puede pasar sin estar mirando nada.** Es el hallazgo del día y salió de aplicar lo anterior. Ver la sección siguiente.

## La prueba dormida

Al escribir su quinta prueba, para la guardia de `unidades_producidas == 0`, comprobó `resultado[0]["unidades_producidas"] == 0` en lugar de `resultado[0]["tasa_defectos_pct"] is None`. La prueba pasaba, pero comprobaba un valor que la guardia no toca: pasaba igual con la guardia sana y con la guardia rota.

No se detectó leyendo el código. Se detectó porque la mutación —cambiar `tasa_defectos = None` por `tasa_defectos = 0` en la línea 65— **no hizo saltar la prueba**. `5 passed` con el programa roto es la señal.

Corregida la clave, la misma mutación produjo `assert 0 is None` y la prueba pasó a vigilar de verdad.

Pregunta de cierre y respuesta suya, que es el argumento entero del bloque: si no se hubiera roto la guardia, ¿se habrían enterado alguna vez de que la prueba miraba la clave equivocada? — **«Negativo, solo verificando manualmente.»** Es decir: una prueba en la que hay que confiar a mano no ahorra nada.

## Lo que construyó el estudiante

En `tests/`:

- Borró las diez líneas de llamadas manuales y `print("OK - ...")` del final de `test_resumen_por_turno.py` y `test_resumen_por_producto.py`. Eran el andamiaje de cuando ejecutaba los archivos con `python` a secas.
- Escribió `test_producto_sin_unidades` en `test_resumen_por_producto.py`, la quinta prueba del proyecto y la primera que cubre la guardia de división entre cero por unidades producidas, verificada hasta hoy solo con un CSV temporal.

Sobre `analizador_produccion.py` solo hizo la mutación temporal de la línea 65, revertida al terminar.

## Evidencia

- Archivos: `analizador-produccion/tests/test_resumen_por_producto.py` líneas 31-37, y `test_resumen_por_turno.py` sin las llamadas finales.
- Ejecución: observada en las cinco corridas de `python -m pytest tests/ -q`.
  - Tras borrar las llamadas manuales: `4 passed`.
  - Con `999` en lugar de `460`: `..F.`, `assert 460 == 999`, `1 failed, 3 passed`.
  - Restaurado el `460`: `4 passed`.
  - Quinta prueba con la clave equivocada y la guardia rota: `5 passed`. **La prueba estaba dormida.**
  - Corregida la clave, guardia todavía rota: `assert 0 is None`, `1 failed, 4 passed`.
  - Guardia reparada: `5 passed`.
- Comprobación final del tutor sobre los archivos guardados: la línea 65 vuelve a decir `tasa_defectos = None`, y `python analizador_produccion.py datos/produccion.csv` sigue en `440 28 412 34` con código `0`.
- Explicación: **demostrada.** Explicó la aserción con sus palabras, identificó que la prueba comprobaba «otra clave», y cerró con «negativo, solo verificando manualmente».
- Método de validación: ejecución observada, mutación del código y explicación propia.

## Errores y correcciones

- **Cuarto incidente de lanzador de la racha.** Primero ejecutó `pytest test/` —sin la `s`— desde dentro de la carpeta `tests`, y después usó el botón ▶ de VS Code, que lanzó `python.exe ...test_resumen_por_turno.py` en lugar de pytest. La salida vacía del segundo caso resultó útil: probaba que, borradas las llamadas manuales, el archivo ya no ejecuta nada por sí solo.
- `SyntaxError` en el diccionario de la prueba nueva: comas de más, una detrás de `"producto"` y otra detrás de cada `:`. Se corrigió comparándolo con su propia línea 23, que estaba bien escrita.
- `TypeError: unsupported operand type(s) for -: 'str' and 'str'`: escribió los números entre comillas, `"0"` y `"100"`. Se le había advertido de la diferencia en el mismo mensaje y eligió las comillas; el error lo hizo evidente mejor que la advertencia.
- Al rellenar el esqueleto de la prueba sustituyó la línea entera `assert resultado[0][___] is None` por una aserción propia sobre otra clave. De ahí salió la prueba dormida, que acabó siendo lo más valioso del bloque.

## Pendiente

Las validaciones de `PROYECTO.md` no son testeables todavía: viven dentro de `if __name__ == "__main__":`, donde pytest no entra. Solo `calcular_resumen_por_turno` y `calcular_resumen_por_producto` son importables. Extraerlas a funciones es el paso que habilita el resto de la Semana 11.

Detalle menor: en la línea 37 quedó `resultado [0]` con un espacio de más, y en la 32 `registro_1=` sin espacio antes del igual. No afecta a la ejecución.

## Conexiones

- [[38 - Paso previo a S11-B1 - Validar la cabecera del CSV]]
- [[32 - Refactorizar a funcion y para que sirve un test]]
- [[33 - Bloque puente - Proyecto real, reportes y primera prueba]]
- [[Python desde 0 - Índice]]
