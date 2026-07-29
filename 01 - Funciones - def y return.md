---
tags: [python, funciones, def, return, fundamentos]
aliases: [Def y return]
---

# Funciones en Python: `def` y `return`

> [!summary] Idea principal
> `def` construye y nombra una función. Los parámetros reciben información. Las instrucciones hacen el trabajo. `return` entrega el resultado. Para ejecutar la función se escribe su nombre seguido de paréntesis.

## 1. La función como una máquina

Imagina una máquina que recibe materiales, realiza un trabajo y entrega un producto.

- `def` construye la máquina.
- El nombre identifica la máquina.
- Los parámetros son las entradas.
- El bloque indentado contiene el trabajo.
- `return` entrega el resultado.
- `nombre_funcion()` enciende la máquina.

```python
def sumar(numero_1, numero_2):
    resultado = numero_1 + numero_2
    return resultado
```

## 2. ¿Qué significa `def`?

`def` viene de *define*: definir. Indica que se creará una función.

```python
def saludar():
    print("Hola")
```

Las partes son:

- `def`: comienza la definición.
- `saludar`: nombre de la función.
- `()`: lugar de los parámetros.
- `:`: anuncia el bloque.
- Sangría: indica qué instrucciones pertenecen a la función.

Definir una función no significa ejecutarla. Para llamarla:

```python
saludar()
```

## 3. Parámetros y argumentos

El parámetro es una caja vacía declarada en la función:

```python
def preparar_jugo(fruta):
    print("Preparando jugo de", fruta)
```

El argumento es el valor real que enviamos:

```python
preparar_jugo("naranja")
```

- `fruta` es el parámetro.
- `"naranja"` es el argumento.

Con varios parámetros, el orden importa:

```python
def presentar_persona(nombre, edad):
    print("Nombre:", nombre)
    print("Edad:", edad)


presentar_persona("Erick", 25)
```

## 4. ¿Qué significa `return`?

`return` devuelve o entrega el resultado producido por la función.

```python
def sumar(numero_1, numero_2):
    resultado = numero_1 + numero_2
    return resultado


total = sumar(5, 3)
print(total)
```

Recorrido:

1. `numero_1` recibe `5`.
2. `numero_2` recibe `3`.
3. Se calcula `5 + 3`.
4. `resultado` guarda `8`.
5. `return` entrega `8`.
6. `total` recibe `8`.

Por eso `total = sumar(5, 3)` termina comportándose como `total = 8`.

## 5. Diferencia entre `print` y `return`

### `print` solamente muestra

```python
def sumar_con_print(a, b):
    print(a + b)


total = sumar_con_print(5, 3)
print(total)
```

Salida:

```text
8
None
```

La función mostró `8`, pero no entregó un valor. Por eso `total` recibe `None`.

### `return` entrega un valor reutilizable

```python
def sumar_con_return(a, b):
    return a + b


total = sumar_con_return(5, 3)
doble = total * 2
print(doble)
```

Salida:

```text
16
```

> [!tip] Regla práctica
> Si quieres mostrar algo, utiliza `print`. Si quieres obtener y reutilizar un resultado, utiliza `return`.

## 6. `return` termina la función

Cuando Python ejecuta `return`, sale inmediatamente de la función:

```python
def hacer_prueba():
    print("Paso 1")
    return 10
    print("Paso 2")
```

`Paso 2` nunca se ejecuta.

### `return` dentro de un bucle

Esta consecuencia es la que más confusión provoca. Si `return` queda dentro de un `for`, la función sale en la **primera vuelta** y el bucle nunca se completa.

```python
def sumar_todos(numeros):
    total = 0
    for n in numeros:
        total += n
        return total          # dentro del for: incorrecto


print(sumar_todos([5, 10, 20]))   # Muestra 5, no 35
```

Recorrido:

| Vuelta | `n` | `total` | ¿Llega al `return`? |
| ------ | --- | ------- | ------------------- |
| 1ª     | 5   | 5       | Sí, sale con `5`    |
| 2ª     | —   | —       | Nunca ocurre        |
| 3ª     | —   | —       | Nunca ocurre        |

La corrección consiste en sacar `return` del bucle, al mismo nivel que el `for`:

```python
def sumar_todos(numeros):
    total = 0
    for n in numeros:
        total += n
    return total              # fuera del for: correcto


print(sumar_todos([5, 10, 20]))   # Muestra 35
```

> [!warning] La indentación cambia el significado
> `return` **dentro** del bucle significa "sal en la primera vuelta".
> `return` **fuera** del bucle significa "sal cuando el bucle termine".
> Ninguno de los dos produce error de sintaxis: el programa funciona y entrega un resultado incorrecto.

El mismo riesgo aparece al construir listas dentro de una función. Si `filas = []` se coloca dentro del bucle que la llena, se reinicia en cada vuelta y solo sobrevive la última reconstrucción.

También puede haber diferentes salidas:

```python
def revisar_edad(edad):
    if edad >= 18:
        return "Es mayor de edad"

    return "Es menor de edad"
```

## 7. Ejemplo del analizador de producción

### Calcular unidades buenas

```python
def calcular_unidades_buenas(unidades_producidas, unidades_defectuosas):
    unidades_buenas = unidades_producidas - unidades_defectuosas
    return unidades_buenas


resultado = calcular_unidades_buenas(980, 35)
print("Unidades buenas:", resultado)
```

Salida:

```text
Unidades buenas: 945
```

### Conectar dos funciones

```python
def calcular_unidades_buenas(producidas, defectuosas):
    return producidas - defectuosas


def calcular_productividad(unidades_buenas, horas):
    return unidades_buenas / horas


buenas = calcular_unidades_buenas(980, 35)
productividad = calcular_productividad(buenas, 8.5)

print("Unidades buenas:", buenas)
print("Productividad:", round(productividad, 2))
```

La primera función devuelve `945`. Ese valor se convierte en la entrada de la segunda función.

## 8. Devolver `True` o `False`

Una función también puede responder preguntas:

```python
def meta_cumplida(producidas, meta):
    return producidas >= meta
```

```python
print(meta_cumplida(1000, 900))  # True
print(meta_cumplida(800, 900))   # False
```

## 9. Validar antes de calcular

No debemos dividir entre cero:

```python
def calcular_productividad(unidades_buenas, horas):
    if horas <= 0:
        return None

    return unidades_buenas / horas
```

Aquí `None` comunica que no existe un resultado válido para esas entradas.

## 10. Variables internas

Las variables creadas dentro de una función normalmente solo existen dentro de ella:

```python
def sumar(a, b):
    resultado = a + b
    return resultado


total = sumar(5, 3)
print(total)
```

`return` saca el valor de la función y `total` lo recibe fuera.

## 11. Errores frecuentes

### Definir, pero no llamar

```python
def saludar():
    print("Hola")


saludar()  # Esta línea ejecuta la función.
```

### Olvidar los paréntesis

```python
saludar    # Se refiere a la función.
saludar()  # Ejecuta la función.
```

### Olvidar `return`

```python
def sumar(a, b):
    resultado = a + b
```

La función calcula, pero devuelve `None`.

### Confundir `print` con `return`

```python
def sumar(a, b):
    print(a + b)   # Solo muestra.
```

Para reutilizar el resultado:

```python
def sumar(a, b):
    return a + b
```

### Enviar argumentos insuficientes

```python
def sumar(a, b):
    return a + b


sumar(5)     # Incorrecto: falta b.
sumar(5, 3)  # Correcto.
```

## 12. Recorrido completo

```python
def calcular_cumplimiento(producidas, meta):
    porcentaje = producidas / meta * 100
    return porcentaje


resultado = calcular_cumplimiento(980, 1000)
print("Cumplimiento:", resultado, "%")
```

Python hace lo siguiente:

1. Guarda la función.
2. Encuentra la llamada con `980` y `1000`.
3. Los parámetros reciben esos valores.
4. Calcula el porcentaje.
5. `return` devuelve `98.0`.
6. `resultado` recibe `98.0`.
7. `print` lo muestra.

## 13. Resumen para recordar

```text
def                  = construye y nombra una función
parámetros           = datos que la función puede recibir
instrucciones        = trabajo que realiza
return               = valor que entrega
nombre_funcion(...)  = llamada que ejecuta la función
print(...)           = muestra información en pantalla
```

> [!question] Comprobación personal
> ¿Puedes explicar por qué `print` muestra un valor, pero `return` permite guardarlo y utilizarlo en otro cálculo?

## 14. Ejercicio

Crea una función llamada `calcular_tasa_defectos` que:

1. Reciba unidades producidas y defectuosas.
2. Evite dividir entre cero.
3. Calcule el porcentaje de defectos.
4. Devuelva el resultado con `return`.
5. Muestre el resultado fuera de la función.

No marques este tema como dominado hasta poder explicar con tus propias palabras la diferencia entre **definir**, **llamar**, **mostrar** y **devolver**.

---

Volver a [[Python desde 0 - Índice]].
