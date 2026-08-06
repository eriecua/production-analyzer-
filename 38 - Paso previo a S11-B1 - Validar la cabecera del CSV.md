---
tags: [python, aprendizaje, semana-11, paso-previo]
tipo: bloque
semana: 11
bloque: paso-previo-S11-B1
estado: pendiente-de-validacion
fecha: 2026-08-05
---

# Paso previo a S11-B1 - Validar la cabecera del CSV

## Objetivo

Que un CSV al que le falta una columna obligatoria falle con un mensaje que diga cuál falta y con un código de salida propio, en lugar de reventar con `KeyError` a mitad del trabajo.

## Estado

**Pendiente de validación.** Escrito, ejecutado y verificado por ambos; falta la explicación con sus palabras.

*Corregido el 2026-08-06:* esta validación **no es una de las nueve** de `PROYECTO.md` —la especificación no pide comprobar columnas ausentes—, sino un añadido suyo. Y de las nueve ya había tres hechas desde S10-B1, no una. Faltan seis. Ver la entrada `correccion-de-registro` del log.

## Conocimiento esencial

- **Validar es comprobar en la puerta, no durante el trabajo.** Antes de este bloque el programa descubría la columna ausente en la línea 48, cuando ya había impreso resultados y ya había vaciado `resumen_por_producto.csv`. Ahora lo detecta antes de tocar nada.
- **`DictReader` guarda la cabecera en `lector.fieldnames`.** No hay que calcularla: la leyó para hacer su trabajo y la deja disponible como lista de nombres. Comparar esa lista con la lista de exigencias es toda la validación.
- **`not in` sobre una lista** es la misma herramienta que ya usaba en `if turno not in unidades_por_turno`, con los dos lados cambiados. No era sintaxis nueva, era transferencia.
- **`fieldnames` puede valer `None`.** Si el archivo está completamente vacío no hay cabecera que leer, y `not in` contra `None` lanzaría `TypeError`. Pylance lo señala; ese aviso **sí era real**, a diferencia del falso positivo conocido en `tests/test_resumen_por_turno.py`.
- Un filtro previo y un filtro específico **no se sustituyen, se encadenan**. Objeción suya, y era correcta: si solo quedara la comprobación de `None`, se perdería el mensaje que dice qué columna falta. Por eso el `is None` va delante como portero y deja pasar todo lo demás al bucle.

## Lo que construyó el estudiante

En `analizador_produccion.py`:

- `SALIDA_FALTA_DATO = 4` (línea 8), siguiendo la numeración seguida que él mismo estableció en S10-B3.
- `COLUMNAS_OBLIGATORIAS` (línea 9), lista con los ocho nombres de columna de `PROYECTO.md`.
- Entre la creación del `DictReader` y el bucle de filas (líneas 92-99), dos comprobaciones encadenadas: `if lector.fieldnames is None` con su mensaje y su salida, y un bucle sobre `COLUMNAS_OBLIGATORIAS` que compara con `not in` y sale nombrando la columna que falta.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py`, líneas 8-9 y 92-99.
- Ejecución observada, primero por él y después repetida por el tutor sobre el archivo guardado:
  - `datos/prueba_falta_columna.csv` → `Falta la columna obligatoria: producto`, código `4`, **sin traceback** y sin tocar `salidas/`.
  - `datos/produccion.csv` → `440 28 412 34`, código `0`. Sin cambios de comportamiento.
- Casos límite probados por el tutor con archivos temporales fuera del repositorio:
  - CSV de 0 bytes → `El archivo no tiene cabecera`, código `4`. La guardia de `None` funciona.
  - CSV con la cabecera correcta y ninguna fila de datos → se ejecuta entero, `Registro válidos: 0`, totales `0 0 0 0`, código `0`.
  - CSV correcto guardado en UTF-8 **con BOM** → `Falta la columna obligatoria: id_registro`, código `4`.
- `python -m pytest tests/ -q`: 4 pruebas pasan. `salidas/` restaurado con el CSV bueno tras las pruebas.
- Explicación: **no comprobada todavía.**

## Hallazgos abiertos

Los dos salieron de probar casos límite y **ninguno está resuelto**:

1. **BOM.** Un CSV correcto exportado desde Excel se guarda normalmente en UTF-8 con BOM. Esos tres bytes iniciales se pegan al primer nombre de columna, que pasa a llamarse `﻿id_registro`, y la validación lo rechaza por una razón falsa. Se corrige leyendo con `encoding="utf-8-sig"` en lugar de `"utf-8"`. Es un caso realista, no rebuscado.
2. **CSV sin filas de datos.** Pasa la validación de cabecera, produce totales en cero y **sobrescribe los tres reportes** con contenido vacío, devolviendo `0` como si todo hubiera ido bien. Nada avisa de que el análisis se hizo sobre cero registros.

## Pendiente

Las **seis** validaciones restantes de `PROYECTO.md`: campos vacíos, fechas inválidas, cantidades negativas, meta no positiva, horas no positivas e identificadores duplicados. Las de valores no numéricos, defectuosas mayores que producidas y divisiones entre cero ya estaban hechas desde S10-B1.

Falta también leer `id_registro` y `fecha`, que hoy se exigen en la cabecera pero no se usan para nada.

*Desde el 2026-08-06 este paso previo deja de existir como bloque aparte:* las seis validaciones se escriben dentro de la Semana 11, cada una emparejada con su prueba. Decisión suya, registrada en [[39 - S11-B1 - Aprender pruebas unitarias basicas]].

## Conexiones

- [[37 - S10-B4 - Probar rutas validas e invalidas]]
- [[36 - S10-B3 - Codigos y mensajes de salida]]
- [[Python desde 0 - Índice]]
