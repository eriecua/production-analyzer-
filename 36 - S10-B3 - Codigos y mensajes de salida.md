---
tags: [python, aprendizaje, semana-10, bloque-3]
tipo: bloque
semana: 10
bloque: S10-B3
estado: validado
fecha: 2026-08-05
---

# S10-B3 - Códigos y mensajes de salida

## Objetivo

Cada forma de terminar el programa deja un código de salida distinto, con nombre propio, comprobable desde PowerShell con `$LASTEXITCODE`.

## Conocimiento esencial

- Un programa termina dejando un **número** a quien lo lanzó. El `print` es para una persona; el código de salida es para **otro programa**. Formulación del estudiante: «el mensaje es para el usuario, y el programa puede detectar qué falló». Sin el número, un lanzador automático que corre el analizador de madrugada no puede saber qué pasó, porque no lee español.
- El criterio para decidir si dos fallos comparten código **no es de dónde vienen, sino qué tiene que hacer distinto quien recibe el número**. Comando mal escrito → corregir lo que se teclea. Archivo no encontrado → buscar dónde está. Archivo bloqueado → cerrar el programa que lo ocupa. Tres acciones distintas, tres códigos distintos.
- La convención: `0` es éxito, cualquier otro número es fallo, y el `2` está **reservado** para el mal uso del comando. «Reservado» significa que ese número es suyo, no que haya que dejarlo vacío.
- Python devuelve `0` **por su cuenta** cuando el script llega al final sin reventar, y `1` por su cuenta si muere con una excepción no atrapada. Un `sys.exit(SALIDA_OK)` explícito no cambia el comportamiento: cambia lo que el archivo declara. El estudiante lo dedujo solo al ver que la prueba con el CSV bueno devolvía `0` sin que `SALIDA_OK` apareciera en ninguna parte del código.
- Una constante también anota tipos que no son valores sueltos. `int` describe *un* valor; `list` describe **el recipiente**. En `for registro in registros`, el plural es la caja (`list`) y el singular es lo que se saca de ella (`dict`). `list[dict]` dice las dos cosas a la vez.
- Un código de salida **no se imprime**. La evidencia de este bloque no está en la pantalla: está en `$LASTEXITCODE`, que hay que leer inmediatamente después de ejecutar, con el comando escrito en la terminal.

## Lo que construyó el estudiante

En `analizador_produccion.py`, cuatro constantes con nombre debajo de los `import` (líneas 4-7):

```python
SALIDA_OK = 0
SALIDA_NO_EXISTE_ARCHIVO = 1
SALIDA_COMANDO_ERRADO = 2
SALIDA_NO_LEE = 3
```

Los tres `sys.exit(1)` existentes sustituidos por la constante que corresponde a cada causa (líneas 81, 106 y 110), y un `sys.exit(SALIDA_OK)` explícito al final del bloque `if __name__ == "__main__":` (línea 152), con la sangría correcta para que no se dispare al importar el módulo.

Además, docstring de una línea y anotaciones de tipo en las dos funciones: `def calcular_resumen_por_turno(registros: list) -> list[dict]:` y `def calcular_resumen_por_producto(registros: list) -> list[dict]:`. Con esto queda saldada la deuda de docstrings y anotaciones heredada de S07-B3 y S07-B4.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py`, líneas 4-7, 9-10, 39-40, 81, 106, 110 y 152.
- Revisión: se inspeccionó el archivo guardado en cada paso.
- Ejecución: observada. El estudiante ejecutó en su terminal, desde `analizador-produccion/`, las cuatro rutas con `; $LASTEXITCODE` pegado detrás. Sin argumento: mensaje de uso y código `2`. Con `inventado.csv`: `No existe un archivo llamado: inventado.csv` y código `1`. Con `datos` (carpeta): `No se puede leer: datos` y código `3`. Con `datos/produccion.csv`: 5 válidos, 1 rechazado, totales `440 28 412 34` y código `0`. Las cuatro coinciden con el mapa de constantes. Tras añadir el `sys.exit(SALIDA_OK)` final, el tutor volvió a ejecutar el camino válido sobre el archivo guardado y confirmó que sigue devolviendo `0`.
- Explicación: demostrada. Dedujo sin ayuda de dónde salía el `0` de la cuarta prueba («eso viene por defecto cuando se ejecuta el código») y enunció con sus palabras el porqué de los códigos: «el mensaje es para el usuario, y el programa puede detectar qué falló».
- Método de validación: revisión estática, ejecución observada en las cuatro rutas con lectura de `$LASTEXITCODE`, y explicación del estudiante.

## Errores y correcciones

- **La confusión que costó tres turnos:** creía que `PermissionError` significaba que la ruta estaba mal escrita. Es lo contrario: la ruta mal escrita produce `FileNotFoundError`; `PermissionError` solo aparece cuando Python **sí** llegó adonde se le dijo. Lo que lo desbloqueó no fue repetir la explicación sino un caso donde el comando es impecable: el CSV correcto abierto en Excel, que Windows bloquea. Ahí se ve que reescribir el comando no arregla nada y que hace falta un código propio. Su conclusión, con sus palabras: «recibe un número nuevo porque es tipo diferente de error».
- Al aplicar la convención del `2`, entendió «reservado» como «prohibido»: dejó el `2` vacío y movió las otras causas al `3` y al `4`, en lugar de dárselo al mal uso del comando.
- Primeros nombres, en inglés y con dos falsos amigos: `FAIL_COMMENT` (comment es *comentario*; comando es *command*) y `NOT_FOUND_ARCHIVE` (archive es un *archivo comprimido o histórico*; el archivo de toda la vida es *file*). Se corrigieron pasándolos al español, que además es el idioma del resto del programa.
- Su primer nombre en español, `SALIDA_MAL_ESCRITA`, volvía a codificar la confusión inicial: en femenino apunta a «la ruta», y ese código salta cuando no se pasó **ningún** argumento, o sea cuando no hay ruta alguna. Prueba usada para detectarlo: escribir el nombre con un comentario al lado y luego borrar el comentario. Si la línea deja de entenderse, el nombre no está haciendo su trabajo.
- Anotó `registros: dict` en lugar de `list`. El error tenía fundamento: dentro sí hay diccionarios. La anotación del parámetro describe el recipiente que recibe la función, no su contenido. Al corregir, borró el `dict` sin poner nada en su lugar antes de escribir `list`.

## Aciertos propios

- Reordenó las cuatro constantes por número, de menos a más grave, sin que nadie se lo pidiera.
- Renombró `SALIDA_NO_EXISTE` a `SALIDA_NO_EXISTE_ARCHIVO` por su cuenta, para que la línea se entendiera leída sola.
- Eligió `list[dict]` para el retorno en lugar de `list` a secas, la opción más informativa de las dos.
- Decidió con argumento propio que `SALIDA_OK` fuera explícita: «prefiero que quede definido, luego limpiamos código». Es más fácil borrar una línea que recuperar una intención que nunca se escribió.

## Pendiente

Las ocho reglas de validación que faltan de `PROYECTO.md`, leyendo `id_registro` y `fecha`. Corresponden al paso previo a S11-B1, no a este bloque.

Detalle menor sin cerrar: un comentario suelto `#int` en la línea 32, resto de una anotación mental durante el bloque.

## Conexiones

- [[35 - S10-B2 - Validar que el archivo exista y sea legible]]
- [[34 - S10-B1 - Recibir la ruta CSV como argumento]]
- [[14 - S06-B1 - Excepciones concretas y ValueError]]
- [[Python desde 0 - Índice]]
