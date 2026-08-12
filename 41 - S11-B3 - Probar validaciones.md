---
tags: [python, aprendizaje, semana-11, bloque-3]
tipo: bloque
semana: 11
bloque: S11-B3
estado: pendiente-de-validacion
fecha: 2026-08-11
---

# S11-B3 - Probar validaciones

**Bloque abierto.** Dos sesiones registradas. Falta la explicación del flujo, que se
aplazó a propósito a un chat en frío.

## Objetivo

Que cada una de las seis reglas de validación que faltan de `PROYECTO.md` exista como
función alcanzable por pytest, con su prueba escrita junto a ella.

**El objetivo cambió el 2026-08-11 por decisión suya.** Ver «Decisión de alcance» abajo.

## Avance de la sesión del 2026-08-10

Escribió `validar_fila`, la primera de las seis, para **campos vacíos**:

```python
def validar_fila(registro: dict) -> str | None:
    """Comprueba una fila. Devuelve el mensaje de error, o None si es correcta."""
    for columna in COLUMNAS_OBLIGATORIAS:
        if registro[columna] == "":
            return f"Falta el dato en la columna: {columna}"
    return None
```

Verificada a mano con un diccionario de prueba que tenía `producto` vacío. Salida
observada: `resultado: Falta el dato en la columna: producto`.

### Lo que sí quedó demostrado

- **Transfirió la forma de `validar_cabecera` a un problema nuevo.** Recibe algo, devuelve
  el motivo o `None`, y quien llama decide qué hacer. La primera vez esa forma se la dio el
  tutor; aquí la replicó él sobre un dato distinto.
- **Eligió el mensaje informativo por el motivo correcto.** Ante «¿solo "hay un campo
  vacío", o el nombre del campo?», pidió que nombrara el campo. Formulación suya: «"No
  existe el valor correspondiente a la fila tal", eso me gustaría».

### La fricción real, y no era de Python

Costó tres intentos llegar a la condición correcta:

1. Escribió `if columna not in registro`, copiando la condición de `validar_cabecera`.
   Nunca podía devolver nada: la cabecera ya pasó, así que las ocho claves existen siempre.
2. Objetó «estamos hablando de fila, no de columnas». La objeción descubrió el hueco: no
   tenía claro que una fila **es** un diccionario cuyas claves son los nombres de columna.
3. Escribió `if None == registro[columna]`. Ya entraba a mirar el valor —eso era el
   avance—, pero comparaba contra el objeto equivocado.

**Los dos conceptos que faltaban, ninguno específico de este proyecto:**

- **`in` sobre un diccionario mira las etiquetas; `registro[columna]` entra a mirar lo que
  hay dentro de la casilla.** Analogía usada: una fila es un formulario con ocho casillas,
  y los nombres de columna son las etiquetas de esas casillas.
- **`None` no es `''`.** `None` es «la casilla no existe»; `''` es «la casilla existe y
  está en blanco». `csv.DictReader` nunca devuelve `None` para una columna presente en la
  cabecera: devuelve `''`.

La condición final se le dio literal después del tercer intento. **No cuenta como
demostrada por él.**

## Avance de la sesión del 2026-08-11

### Lo que sí quedó demostrado, y esto es lo importante del bloque

**Predijo el resultado de la prueba de mutación con el razonamiento completo, antes de
ejecutar.** Se rompió la guardia cambiando `== ""` por `== "xxxxx"` y se le preguntó qué
pasaría. Su respuesta, íntegra:

> «Es que lo que sucede es que el valor ya no está vacío así que supongo que va a tirar
> error, pero arriba dice si el registro de columna es igual a "xxxx" entonces salta el
> error. Y no hay un dato que sea xxxx.»

Recorrió el camino entero: la condición no se cumple nunca → el bucle termina → la función
llega al `return None` del final → la prueba esperaba un mensaje y recibe `None` → falla.
La ejecución lo confirmó: `assert None == 'Falta el dato en la columna: turno'`.

**Es la aplicación por él del principio que ganó en S11-B1** —*una prueba que pasa no dice
nada hasta que se la ha visto fallar cuando debía fallar*—, esta vez sin que se lo
recordaran y anticipando el resultado en lugar de leerlo.

Otras cosas suyas de la sesión:

- Escribió `test_fila_con_campo_vacio` a partir de un esqueleto con huecos.
- **Añadió `unidades_producidas` al diccionario de prueba por su cuenta**, cerrando un
  agujero que se había dejado abierto a propósito: sin esa clave la prueba pasaba solo por
  el orden de `COLUMNAS_OBLIGATORIAS`, y habría reventado con `KeyError` si alguien
  reordenaba la lista.
- Identificó cuál era el único valor no libre del diccionario de prueba y por qué: «turno,
  porque ese es el que vamos a testear».
- Corrigió sus dos errores de la prueba leyendo la salida de pytest: el prefijo `tes_` en
  vez de `test_`, y el mensaje esperado copiado de `validar_cabecera`.

### Lo que NO cuenta como demostrado por él

Se registra aparte a propósito, porque en esta sesión el tutor escribió bastante código:

- **Dónde va `validar_fila` dentro del bucle.** Se le preguntó «antes o después del `try`».
  Primero respondió mal (dijo que saltaría el `sys.exit` de la cabecera, que ya había
  pasado). Se trazaron las dos opciones enteras y se le dio el criterio —lo que cambia es
  si sabes **por qué** se rechazó la fila—, y entonces eligió A. Es reconocimiento después
  de que se lo cuenten, no razonamiento propio.
- **`Path(__file__).parent`.** Se le preguntó si el valor cambiaría al ejecutar desde otra
  carpeta y predijo que sí. No cambia; esa es justamente la propiedad. Explicado por el
  tutor.
- **Las cuatro ediciones del cierre** (validaciones numéricas, `utf-8-sig`,
  `except UnicodeDecodeError`, guardia de cero registros): dictadas literalmente por el
  tutor a petición suya de ir rápido. Él las pegó y verificó.
- **El README**: redactado íntegramente por el tutor. Dijo «ya está listo» al preguntársele
  por su revisión, pero **la revisión no se confirmó**: solo se verificaron las dos
  correcciones de código que iban en el mismo mensaje.

## Decisión de alcance, tomada por él

A mitad de sesión dijo: *«siento que no estamos atascando en validación y más validaciones
[...] a la final he dejado de aprender, ahora solo valido y valido, es como un camino en
círculos. No me está gustando.»* Y después, más rotundo: *«es que siento que no aprendo
nada en realidad con todo esto».*

**El diagnóstico era correcto y se le dio la razón.** Llevaba desde la Semana 10 sin
construir nada nuevo: extraer funciones, añadir `except`, escribir pruebas, tapar agujeros.
Todo mantenimiento. El mantenimiento se siente como no aprender aunque no lo sea, porque al
final del día la pantalla se ve igual.

Se le ofreció elegir entre cerrar el proyecto rápido o aparcarlo y empezar material nuevo.
**Eligió cerrarlo rápido**, y se redujeron las validaciones al mínimo:

- **Implementadas** (dictadas por el tutor): cantidades negativas, meta no positiva y horas
  no positivas, como una sola condición con `or` junto a la comprobación de defectuosas
  mayores que producidas.
- **Descartadas y documentadas como deuda** en el README del proyecto: fechas inválidas e
  identificadores duplicados. Quedan 7 de las 9 reglas de `PROYECTO.md` implementadas.

## Lo que construyó el estudiante

Estado del programa al cierre de la sesión:

- `validar_fila` conectada al bucle de lectura, **antes** de la conversión a `int`, con
  `registros_rechazados += 1` y `continue`.
- `test_fila_con_campo_vacio` en `tests/test_validaciones.py`.
- Tres validaciones numéricas más en la condición de rechazo de fila.
- `CARPETA_SALIDAS = Path(__file__).parent / "salidas"` y las tres llamadas a `open()` de
  los reportes usándola.
- `encoding="utf-8-sig"` y una rama `except UnicodeDecodeError`.
- Guardia de cero registros válidos antes de escribir nada.
- Fixture `datos/prueba_campo_vacio.csv`.

## Evidencia

- Archivo: `analizador-produccion/analizador_produccion.py` y
  `analizador-produccion/tests/test_validaciones.py`.
- Revisión: se inspeccionaron las cuatro ediciones línea a línea antes de ejecutar.
- Ejecución: **observada**, cinco escenarios:
  - `datos/produccion.csv` → 5 válidos, 1 rechazado, código 0.
  - `datos/prueba_campo_vacio.csv` → 1 válido, 1 rechazado.
  - CSV con BOM de Excel → se lee bien; antes se rechazaba.
  - CSV con meta 0, horas 0 y unidades negativas → 3 rechazados, código 4.
  - CSV solo con cabecera → código 4 y **los tres reportes conservaron su hora anterior**,
    sin sobrescribirse.
  - Ejecutado además desde la carpeta superior: los reportes aparecen en
    `analizador-produccion/salidas/`, no donde estaba la terminal.
- Pruebas: `python -m pytest tests/` da **11 passed**.
- Explicación: **no comprobada.** Se aplazó deliberadamente a un chat en frío, porque en
  esta sesión el tutor explicó cada pieza y preguntar aquí mediría la memoria de la
  conversación, no la comprensión.
- Método de validación: ejecución observada y prueba automatizada. La prueba de mutación se
  ejecutó y falló como debía.

## Errores y correcciones

- `tes_fila_con_campo_vacio`: sin la `t`, pytest no la recoge. Prueba que nunca se ejecuta y
  no da ningún aviso. Corregido por él.
- `assert validar_fila(registro) == "Falta la columna obligatoria: turno"`: mensaje copiado
  de `validar_cabecera`. Son dos averías distintas —falta la columna entera vs. la columna
  está y el dato vacío— y los mensajes deben distinguirlas. Corregido por él.
- **Error del tutor, y produjo el peor atasco de la sesión.** Se le mostró el fragmento a
  insertar incluyendo líneas de contexto que ya existían (`for fila in lector:` y `try:`),
  solo para situarlo. Las copió también, y quedó un bucle dentro de otro bucle y dos `try`
  seguidos, con el archivo sin poder ejecutarse. **Al dar código para pegar, dar solo las
  líneas nuevas.**
- `UnicodeDecodeError: byte 0xf1`: el CSV de prueba se guardó en cp1252 al escribir «Mañana»
  desde el editor. No era el código. Se resolvió con *Save with Encoding → UTF-8*, y de paso
  descubrió que el programa no cazaba esa excepción.

## Pendiente

1. **Explicar el flujo principal sin copiarlo**, en un chat en frío. Es el único criterio de
   aceptación de `PROYECTO.md` que queda por cumplir, y el único que no puede hacer el
   tutor. Los otros cinco están cumplidos.
2. Confirmar que revisó el README, que redactó el tutor.
3. Deuda documentada y aceptada: fechas inválidas e identificadores duplicados.

## Conexiones

- [[40 - S11-B2 - Probar calculos y limites]]
- [[39 - S11-B1 - Aprender pruebas unitarias basicas]]
- [[38 - Paso previo a S11-B1 - Validar la cabecera del CSV]]
- [[Python desde 0 - Índice]]
