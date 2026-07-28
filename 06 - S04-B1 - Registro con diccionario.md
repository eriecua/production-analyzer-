---
tags: [python, aprendizaje, semana-4, bloque-1, diccionarios]
tipo: bloque
semana: 4
bloque: S04-B1
estado: validado
fecha: 2026-07-17
---

# S04-B1 - Representar un registro con un diccionario

## Objetivo

Representar un registro de producción mediante una estructura de pares clave-valor.

## Conocimiento esencial

- Un diccionario se escribe con llaves `{}` y guarda parejas `clave: valor`.
- La clave identifica el dato, por ejemplo `"producto"`.
- El valor contiene la información, por ejemplo `"Producto A"`.
- Los corchetes `[]` permiten recuperar un valor usando su clave: `registro["producto"]`.
- Un registro del proyecto puede reunir las ocho columnas del CSV en una sola variable.

## Lo que construyó el estudiante

El archivo `practica_s04.py` contiene un diccionario `registro` con `id_registro`, `fecha`, `turno`, `producto`, `meta_unidades`, `unidades_producidas`, `unidades_defectuosas` y `horas_trabajadas`. Después imprime valores del registro mediante sus claves.

## Evidencia

- Archivo: `practica_s04.py`
- Revisión: se inspeccionó el diccionario guardado y se confirmó la presencia de las ocho columnas del registro de producción.
- Ejecución: observada. La salida mostró `2026-07-17`, `Producto A`, `850`, `34` y `1000`.
- Explicación: demostrada. El estudiante identificó correctamente que `"producto"` es la clave y `"Producto A"` es su valor.
- Método de validación: revisión estática, ejecución del archivo y explicación con palabras propias.

## Pendiente

Nada para este bloque.

## Conexiones

- [[05 - S03-B4 - Integrar funciones y validar registros]]
- [[Python desde 0 - Índice]]
- [[Capa 2 - Wiki/Índice de conocimientos]]
