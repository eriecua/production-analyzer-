---
tags: [python, aprendizaje, semana-8, practica-adicional]
tipo: practica-adicional
semana: 8
estado: validado-como-practica-complementaria
fecha: 2026-07-25
---

# Práctica adicional - Funciones y cumplimiento por producto

## Nota importante sobre este bloque

Esta práctica **no corresponde al bloque oficial S08-B4** del plan de ProjectLibre. Según el plan cargado (`Plan_completo_ProjectLibre_para_Claude.pdf` y el XML exportado), el objetivo real de **S08-B4 es "Identificar mejores y peores resultados"**, que a la fecha de esta nota seguía en 0 % según ProjectLibre. Este ejercicio fue una exploración adicional de funciones (`def`/`return`) y del cálculo de cumplimiento, útil para reforzar Semana 3 y Semana 8, pero no cierra el bloque oficial.

## Objetivo

Empaquetar un cálculo de agrupación en una función reutilizable y calcular el cumplimiento por producto con `meta_unidades`.

## Conocimiento esencial

- Una función puede recibir la lista completa de registros como parámetro y devolver un diccionario acumulador, evitando repetir el mismo bucle en varias partes del código.
- `return` debe quedar alineado con el nivel de la función (fuera del `for`), no dentro del bucle, para que se ejecute una sola vez, cuando ya se recorrieron todos los registros.
- El cumplimiento por producto usa el mismo patrón de dos acumuladores independientes (unidades producidas y meta) que comparten la misma clave de producto.
- Al escribir `diccionario[variable]`, Python evalúa primero el valor que contiene la variable en ese momento y usa ese valor como clave real; no busca una clave llamada igual que el nombre de la variable.

## Analogías usadas para comprender diccionarios

El estudiante construyó y confirmó con sus propias palabras estas analogías durante el bloque:

- Un diccionario es un archivador con cajones etiquetados; `diccionario[clave]` abre el cajón que tiene esa etiqueta.
- `[]` accede a un elemento existente por su clave o índice (lista, diccionario, string); `()` ejecuta una función. Un diccionario nunca se "llama" con paréntesis, se indexa con corchetes.
- Una clave literal entre comillas (`registro["producto"]`) es un texto fijo que el programador escribió a mano al crear el diccionario. Una clave sin comillas (`diccionario[producto]`) es una variable: Python evalúa primero qué valor contiene esa variable en ese instante y usa ese valor, no el nombre de la variable, como clave real.
- En `if clave not in diccionario`, la pregunta es si esa etiqueta ya existe como cajón en el archivador (no si algo está "dentro de la variable clave").
- La variable que recorre un `for` (ej. `producto`) actúa como una llave (`key`) que cambia de valor en cada vuelta; por eso una expresión como `diccionario[producto]` solo tiene sentido dentro del bucle, donde esa llave apunta al cajón correcto en cada iteración.
- `return` debe compararse con la indentación de la primera línea del bucle: si queda al mismo nivel que el `for`, se ejecuta una sola vez al terminar todas las vueltas; si queda una sangría más adentro, se ejecuta en la primera vuelta y corta el resto del recorrido.

## Lo que construyó el estudiante

Creó la función `obtener_defectos_por_turno(lista_registro)`, que empaqueta el acumulador de defectos por turno y lo devuelve con `return`. Además agregó la clave `meta_unidades` a los cinco registros y construyó el acumulador `meta_unidades_por_producto` para calcular el cumplimiento por producto.

## Evidencia

- Archivo: `practica_s08.py`
- Revisión: definición de la función, indentación del `return`, y patrón acumulador del diccionario `meta_unidades_por_producto`.
- Ejecución: observada; `print(meta_unidades_por_producto)` produjo `{'Producto A': 200, 'Producto B': 100, 'Producto D': 100, 'Producto C': 100}`.
- Explicación: demostrada; el estudiante explicó con sus propias palabras la diferencia entre una clave literal (`registro["producto"]`) y una clave por variable (`diccionario[producto]`), y por qué `return` debe quedar fuera del `for`.
- Método de validación: revisión estática y ejecución real.

## Pendiente

- Solo se empaquetó una función (`obtener_defectos_por_turno`); falta crear funciones equivalentes para productividad, rendimiento y cumplimiento si se quiere completar el patrón "una función por indicador".
- Las metas de prueba usadas son todas `100`, por lo que el cumplimiento siempre da 100 %; conviene variar los valores para probar un caso más realista.
- Falta encapsular el cálculo de cumplimiento por producto dentro de su propia función.

## Conexiones

- [[25 - S08-B3 - Comparar productividad y calidad]]
- [[Python desde 0 - Índice]]
- S08-B4 oficial (pendiente): "Identificar mejores y peores resultados", según `Plan_completo_ProjectLibre_para_Claude.pdf`.
