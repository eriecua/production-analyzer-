---
tags: [python, funciones, refactorizar, tests, alcance, bloque-puente, dudas-del-estudiante]
aliases: [Refactorizar a función, Para qué sirve un test]
estado: explicacion-del-tutor-pendiente-de-demostracion
bloque: Bloque puente pre-Semana 10, paso 5
---

# Refactorizar a función y para qué sirve un test

> [!warning] Estado de esta nota
> Esta nota registra **la explicación del tutor**, no comprensión demostrada por el estudiante. Nació de dudas concretas planteadas durante el paso 5 del bloque puente. No cuenta como bloque validado. Se reclasificará cuando el estudiante pueda explicar estos puntos con sus propias palabras y aplicarlos sin ayuda.

> [!summary] Idea principal
> Extraer una función **no cambia lo que el programa hace**; le pone una puerta propia a un pedazo para poder llamarlo sin ejecutar todo lo demás. Eso es lo que hace posible un test. Y un test no es un tema nuevo: es automatizar la comprobación manual que ya se venía haciendo con los ojos desde la Semana 8.

Documento visual de apoyo: https://claude.ai/code/artifact/5c1951ee-a5d8-4660-9da1-12d3b9414eff

## 1. Duda de origen: «el test salió de la nada»

La objeción del estudiante fue legítima y el tutor la reconoció como un fallo de explicación propio: el paso 5 venía escrito en [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]], pero nunca se explicó su propósito antes de pedir el trabajo.

**El test no es un tema nuevo.** Es lo que ya se hacía a mano:

```text
HOY - se comprueba con los ojos     CON TEST - se comprueba solo

  cambio algo                         cambio algo
      |                                   |
  corro el programa                   corro el test
      |                                   |
  abro salidas/....csv                ✅  o  ❌
      |
  busco "Mañana" con la vista
      |
  ¿12.69? ...creo que sí
```

Importa **ahora** porque en la Semana 10 cambia la forma en que entra el archivo y en la Semana 11 se agregan validaciones. Cada cambio puede romper el cálculo del turno sin que nadie lo note, porque ya nadie estará mirando ese número.

## 2. El vínculo: por qué el test obligó a extraer la función

El código estaba suelto, corriendo de arriba a abajo:

```text
+--------------------------------------+
|  analizador_produccion.py            |
|                                      |
|  leer el CSV ---------------+        |
|  calcular totales          |  TODO   |
|  calcular por turno        |  PEGADO |
|  calcular por producto     |         |
|  escribir los 3 CSV -------+         |
+--------------------------------------+
                ^
     Solo hay UNA puerta: ejecutar todo.
     No se puede entrar a probar un pedazo.
```

Un test necesita **llamar solo al pedazo que quiere probar**. Con el código suelto es imposible: para calcular el turno hay que leer el CSV real y escribir los tres archivos. Todo o nada.

Extraer la función es ponerle una puerta propia a ese pedazo:

```text
   entra                                          sale
     |                                              ^
[registros]  -->  calcular_resumen_por_turno()  --> [filas_turno]
                  (agrupa y calcula productividad)
```

## 3. Las tres piezas de una función

| Pieza | En el código del proyecto | Qué hace |
| --- | --- | --- |
| `def nombre` | `def calcular_resumen_por_turno` | Nombra la máquina |
| `( )` | `(registros)` | La **ranura de entrada** |
| `return` | `return filas_turno` | La **bandeja de salida** |

Amplía [[01 - Funciones - def y return]] y [[02 - S03-B1 - Parametros, argumentos y variables externas]].

## 4. Duda: por qué `(registros)` va entre paréntesis

Se conecta con la distinción de símbolos ya trabajada en [[26 - Practica adicional - Funciones y cumplimiento por producto]]:

| Símbolo | Qué hace |
| --- | --- |
| `{ }` | crea un diccionario |
| `[ ]` | crea una lista, **o busca** dentro de algo |
| `( )` | **llama** a una función |

Los paréntesis son el gesto de «ejecútate». Lo que va adentro es lo que se le entrega, igual que en funciones ya usadas a diario:

```python
len(registros)        # le entrego registros,  devuelve 5
int("120")            # le entrego "120",      devuelve 120
round(12.6875, 2)     # le entrego dos cosas,  devuelve 12.69
```

Escribir `def calcular_resumen_por_turno(registros):` es **declarar qué cabe en esa ranura**. Es una promesa: «cuando me llames, tienes que darme una lista de registros».

## 5. Duda: el parámetro se llama igual que la variable de afuera

```text
AFUERA                             ADENTRO de la función
------                             ---------------------
registros = [las 5 filas del CSV]

   calcular_resumen_por_turno(registros)
                  |
                  +-- pasa el contenido -->  registros
                                             (nombre local, nuevo)
```

El `registros` de adentro es una etiqueta **nueva y local**. Se llama igual por comodidad, pero podría llamarse `lista` o `datos`. La función no sabe ni le importa de dónde vino lo que recibió.

**Esa indiferencia es exactamente lo que la vuelve testeable**: se la puede llamar con datos inventados y funciona igual.

## 6. Duda: por qué los diccionarios van dentro de la función

Es lo que hace confiable a la máquina.

### Diccionarios afuera (mal)

```python
unidades_por_turno = {}

def calcular(registros):
    ...acumula sobre el de afuera...
```

```text
1a llamada -> {Mañana: 220}
2a llamada -> {Mañana: 440}   <-- se sumó otra vez encima
```

La función **se acuerda** de la llamada anterior y contamina el resultado.

### Diccionarios adentro (bien)

```python
def calcular(registros):
    unidades_por_turno = {}
    ...
```

```text
1a llamada -> {Mañana: 220}
2a llamada -> {Mañana: 220}   <-- empieza limpio
```

Cada llamada arranca con los cajones vacíos: la misma entrada siempre da la misma salida. Un test lo necesita así, o un día pasa y otro día falla sin motivo.

Relacionado con las variables internas de [[01 - Funciones - def y return]] (sección 10).

## 7. Duda: por qué `filas_turno = []` lleva corchetes

Los corchetes crean **una bolsa vacía**. Hace falta bolsa porque el `for` da varias vueltas y cada vuelta **pisa** la variable `fila`:

```text
vuelta 1 -> fila = {Mañana...}  -> append ->  [Mañana]
vuelta 2 -> fila = {Noche...}   -> append ->  [Mañana, Noche]
vuelta 3 -> fila = {Tarde...}   -> append ->  [Mañana, Noche, Tarde]
                                              +--------+--------+
                                              esto es lo que se devuelve
```

> [!tip] La pregunta que decide, para cualquier código
> **¿Voy a producir una cosa, o varias?**
> - **Varias** -> necesito lista `[]` + `append`.
> - **Una sola** -> basta la variable.

El estudiante ya aplicó esta regla correctamente por su cuenta: `resumen_general.csv` **no** usa lista (una sola fila), mientras que turno y producto **sí** (varias filas). Ver [[30 - S09-B3 - Exportar resultados por producto]].

## 8. Duda: por qué la función va al principio del archivo

Python lee de arriba hacia abajo, como una receta. No puede usar algo que todavía no leyó.

```python
# No funciona
filas = calcular(registros)   # ¿calcular? no la conozco todavía

def calcular(registros):
    ...
```

```python
# Funciona
def calcular(registros):
    ...

filas = calcular(registros)   # ya sé qué es
```

Es como decir «bate lo de la olla» antes de haber dicho qué va en la olla.

## 9. Duda: «¿lo podría haber unido desde el inicio?»

Sí, y ahí está la lección real del paso.

Alguien con experiencia habría escrito la función desde el primer momento. El estudiante no podía: hace tres semanas **todavía no sabía qué cálculo necesitaba**. Había que descubrirlo escribiéndolo suelto.

Este orden es el normal, también entre profesionales:

```text
1. Lo escribo suelto        -> para entender el problema
2. Funciona                 -> ya sé qué hace exactamente
3. Lo empaqueto en función   -> ahora sí puedo darle forma
       |
       +-- esto se llama REFACTORIZAR:
           cambiar la forma sin cambiar lo que hace
```

> [!important] Criterio de refactorización correcta
> Si se refactorizó bien, **el resultado no cambia**. Por eso `salidas/resumen_por_turno.csv` debe seguir dando **12.69** para Mañana. Si ese número cambió, la mudanza salió mal.

Amplía la separación de responsabilidades de [[18 - S07-B1 - Separar responsabilidades]] y [[19 - S07-B2 - Nombres y responsabilidades]].

## 10. Error de proceso a evitar

Al extraer la función, el estudiante hizo una **copia** en lugar de una **mudanza**: la lógica quedó viviendo en dos sitios a la vez (suelta arriba, y dentro de la función abajo), con el CSV alimentándose todavía del código suelto.

El riesgo es concreto: si mañana se corrige un error dentro de la función, el CSV sigue saliendo mal, porque el CSV no pasa por la función. **Dos copias de la misma verdad siempre se desincronizan.**

Refactorizar exige eliminar el original. Mientras el duplicado exista, un test que pruebe la función no está probando el programa.

## 11. Comprobación personal

> [!question] Preguntas para autoevaluar
> 1. ¿Por qué un test no puede probar código suelto, pero sí una función?
> 2. ¿Qué pasa si los diccionarios acumuladores se declaran fuera de la función y se la llama dos veces?
> 3. ¿Cómo decido, en un código nuevo, si necesito una lista con `append` o me basta una variable?
> 4. ¿Por qué el resultado **no** debe cambiar después de refactorizar?
> 5. ¿Por qué el nombre del parámetro puede ser igual al de la variable de afuera sin que choquen?

No marcar este tema como dominado hasta poder extraer una función desde cero, sin copiar el molde, y explicar por qué cada pieza va donde va.

---

Volver a [[Python desde 0 - Índice]].
