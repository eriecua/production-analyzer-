---
tags: [python, aprendizaje, semana-10, bloque-1]
tipo: bloque
semana: 10
bloque: S10-B1
estado: validado
fecha: 2026-07-29
---

# S10-B1 - Recibir la ruta CSV como argumento

## Objetivo

El programa recibe la ruta del CSV desde la línea de comandos y avisa con un mensaje legible cuando el argumento falta o el archivo no existe.

## Conocimiento esencial

- `sys.argv` es una lista de textos que Python arma con lo escrito en la terminal. La posición `0` es el nombre del script; los argumentos del usuario empiezan en la `1`. Comprobar `len(sys.argv)` antes de indexar evita el `IndexError`.
- `sys.exit(1)` detiene el programa; `print` solo muestra texto y la ejecución continúa con la línea siguiente. Un mensaje de error sin `sys.exit()` deja el programa corriendo con datos vacíos.
- `except` debe nombrar la excepción concreta (`except FileNotFoundError`). Un `except` pelado atrapa también los fallos de programación y los disfraza.
- `"ruta_csv"` con comillas es un texto de ocho letras; `ruta_csv` sin comillas es la variable. Confundirlos produjo un error **bien formado pero falso**: el mensaje afirmaba que no existía `datos/produccion.csv` cuando ese archivo sí estaba. Cuando un mensaje de error contradice algo comprobado, sospechar del código que lo emite.
- `__name__` es una variable que **Python** asigna a cada archivo automáticamente; no se importa de ningún sitio. Vale `__main__` en el archivo que se ejecuta y el nombre del módulo en el que es importado. Por eso `if __name__ == "__main__":` es falso al importarlo y el bloque no se ejecuta: sin esa línea, `pytest` intentaría abrir la carpeta `tests/` como si fuera el CSV.

## Lo que construyó el estudiante

En `analizador_produccion.py`, dentro del bloque `if __name__ == "__main__":`: la comprobación de `len(sys.argv) < 2` con mensaje de uso y `sys.exit(1)`, la ruta guardada en la variable `ruta_csv`, y el `try` / `except FileNotFoundError` alrededor de la apertura del archivo con un mensaje que incluye la ruta recibida.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py`
- Revisión: se inspeccionó el archivo guardado.
- Ejecución: observada en los tres caminos. Sin argumento devuelve el mensaje de uso y código de salida 1; con `no_existe.csv` devuelve `No existe un archivo llamado: no_existe.csv` y código 1; con `datos/produccion.csv` devuelve 5 registros válidos, 1 rechazado y los totales `440 28 412 34`, con código 0.
- Explicación: demostrada. Formuló el mecanismo del guardián con sus palabras: «si el nombre coincide con la ejecución en el terminal entonces entra al bloque, si no se lo salta». También acertó sin ayuda que el valor de `__name__` lo pone Python, y que la comparación es falsa cuando el test importa el módulo.
- Método de validación: revisión estática, ejecución desde la terminal y explicación del estudiante.

## Errores y correcciones

- El `except FileNotFoundError` se escribió sin `sys.exit(1)`. El mensaje aparecía, pero el programa seguía con `registros` vacío y sobrescribía los CSV de `salidas/` con ceros. Se añadió `sys.exit(1)`.
- `open("ruta_csv", ...)` con comillas abría un archivo literalmente llamado `ruta_csv`. El `except` capturaba el fallo y emitía un mensaje correcto en forma pero falso en contenido. Se quitaron las comillas.
- El mensaje de uso decía `<salidas/analizador>`, que no era lo que el programa espera. Se corrigió a `<ruta_csv>`.
- Primer intento de explicar `__name__`: lo identificó con el argumento de la terminal (`produccion.csv`). Se resolvió observando la salida de `__name__`, `sys.argv[0]` y `sys.argv[1]` imprimidos a la vez, y desactivando el guardián en una copia para ver que `pytest` fallaba con `PermissionError` al intentar abrir `tests/`.

## Pendiente

Docstrings y anotaciones de tipo, repartidos entre S10-B1 y S10-B3 según se escriban las funciones. No bloquean este bloque.

## Conexiones

- [[32 - Refactorizar a funcion y para que sirve un test]]
- [[33 - Bloque puente - Proyecto real, reportes y primera prueba]]
- [[14 - S06-B1 - Excepciones concretas y ValueError]]
- [[01 - Funciones - def y return]]
- [[Python desde 0 - Índice]]
