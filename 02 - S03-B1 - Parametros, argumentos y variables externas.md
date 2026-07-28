---
tags: [python, funciones, parametros, argumentos, semana-3, bloque-1]
aliases: [S03-B1 Parámetros y argumentos]
---

# S03-B1 - Parámetros, argumentos y variables externas

## Idea principal

En `def calcular_unidades_buenas(unidades_producidas, unidades_defectuosas)`, los nombres dentro de los paréntesis son **parámetros**.

Cuando llamo la función con algo como `calcular_unidades_buenas(700, 70)` o `calcular_unidades_buenas(producidas, defectuosas)`, lo que envío son **argumentos**.

## Diferencia importante

- **Parámetro**: nombre temporal que existe dentro de la función.
- **Argumento**: valor o variable real que mando al llamar la función.
- **Variable externa**: variable creada fuera de la función.

```python
def calcular_unidades_buenas(unidades_producidas, unidades_defectuosas):
    unidades_buenas = unidades_producidas - unidades_defectuosas
    return unidades_buenas

producidas = 700
defectuosas = 70
resultado = calcular_unidades_buenas(producidas, defectuosas)
print(resultado)
```

## Qué se comprobó en este bloque

- La función se ejecutó correctamente.
- El resultado validado fue `630`.
- Se comprobó que los nombres de las variables externas **no tienen que ser iguales** a los parámetros internos.
- Se comprobó que `return` entrega el valor para usarlo fuera de la función.

## Regla práctica

La función **no guarda permanentemente** los parámetros. Solo recibe valores durante la llamada, trabaja con ellos y devuelve un resultado.

## Error común

Confundir esto:

```python
calcular_unidades_buenas(700, 70)
```

con esto:

```python
def calcular_unidades_buenas(unidades_producidas, unidades_defectuosas):
```

Lo primero es la **llamada**. Lo segundo es la **definición**.

## Frase para recordar

> Los parámetros son nombres internos de la función. Los argumentos son los valores o variables reales que envío desde afuera.

Volver a [[Python desde 0 - Índice]].
