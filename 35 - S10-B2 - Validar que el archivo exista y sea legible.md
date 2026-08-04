---
tags: [python, aprendizaje, semana-10, bloque-2]
tipo: bloque
semana: 10
bloque: S10-B2
estado: validado
fecha: 2026-08-04
---

# S10-B2 - Validar que el archivo exista y sea legible

## Objetivo

El programa nunca muere con un traceback por culpa de la ruta recibida: avisa con una frase legible y sale con código 1, tanto si el archivo no existe como si existe y no se puede leer.

## Conocimiento esencial

- Un `try` admite **varios `except` seguidos**, uno por tipo de error. Cada `except` nombra un solo error y solo detiene lo que se llama exactamente así. `except FileNotFoundError` no atrapa un `PermissionError` aunque el fallo ocurra en la misma línea que vigila.
- «Que el archivo exista» y «que se pueda leer» son **dos comprobaciones distintas**. Una ruta puede existir de sobra y aun así no ser legible: en Windows, pasar la carpeta `datos` en lugar de un archivo produce `PermissionError: [Errno 13] Permission denied: 'datos'`, no `FileNotFoundError`.
- El nombre que va detrás de `except` **lo da Python**, en la última línea del traceback y antes de los dos puntos. De `PermissionError: [Errno 13] Permission denied: 'datos'` se copia `PermissionError`. El número (`Errno 13`) es lo que más se parece a un «código de error» y es justo lo que no se usa.
- El botón ▶ de VS Code ejecuta siempre `python archivo.py`, **sin argumentos**. Desde que el programa recibe la ruta por `sys.argv`, lanzarlo con ese botón entra siempre por el mensaje de uso y no llega nunca al `try`. Hay que escribir el comando en la terminal, y desde `analizador-produccion/`, porque las rutas relativas se resuelven desde el directorio del terminal.
- Al añadir un `except` a un `try` que ya funcionaba, el riesgo real no es el caso nuevo sino haber roto los viejos sin enterarse. El cierre exige volver a ejecutar los tres caminos, no solo el que se acaba de escribir.

## Lo que construyó el estudiante

En `analizador_produccion.py`, una segunda rama `except PermissionError:` debajo del `except FileNotFoundError` existente, con un mensaje que incluye la ruta recibida y `sys.exit(1)`. Alineada correctamente con el `except` de arriba a la primera.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py`, líneas 101-103.
- Revisión: se inspeccionó el archivo guardado.
- Ejecución: observada en los tres caminos. Los mensajes los produjo y reportó el estudiante desde su terminal; los códigos de salida los confirmó el tutor sobre el mismo archivo guardado. Con `datos` (carpeta) devuelve `No se puede leer: datos` y código 1; con `datos/no_existe.csv` devuelve `No existe un archivo llamado: datos/no_existe.csv` y código 1; con `datos/produccion.csv` devuelve 5 registros válidos, 1 rechazado y los totales `440 28 412 34`, con código 0.
- Explicación: demostrada por transferencia. Ante un error que nunca había visto, `UnicodeDecodeError: 'utf-8' codec can't decode byte 0xf1 in position 12`, escribió sin ayuda `except UnicodeDecodeError:`.
- Método de validación: revisión estática, ejecución desde la terminal y transferencia a un error nuevo.

## Errores y correcciones

- Reportó dos veces el mensaje de uso como salida de `python analizador_produccion.py datos`. El código estaba correcto y guardado; el diagnóstico apuntaba en falso al `except`. La causa real era el lanzador: usaba el botón ▶ de VS Code, que no pasa argumentos. Se resolvió comparando la salida del botón con la del comando escrito a mano en la terminal integrada.
- Su primera formulación de dónde sale el nombre del error fue imprecisa: «en el código de error». Acertaba en lo esencial —la información la da Python, no se inventa— pero «código de error» apunta igual de bien al `Errno 13`, que no sirve. Se afinó señalando el trozo exacto de la línea; después transfirió sin ayuda.

## Pendiente

Docstrings y anotaciones de tipo para las dos funciones del programa, y constantes con nombre para los códigos de salida. Ambos corresponden a S10-B3.

## Conexiones

- [[34 - S10-B1 - Recibir la ruta CSV como argumento]]
- [[14 - S06-B1 - Excepciones concretas y ValueError]]
- [[10 - S05-B1 - Archivos rutas y codificacion]]
- [[Python desde 0 - Índice]]
