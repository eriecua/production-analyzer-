---
tags: [python, aprendizaje, semana-3, bloque-4]
tipo: bloque
semana: 3
bloque: S03-B4
estado: validado
fecha: 2026-07-17
---

# S03-B4 - Integrar funciones y validar registros

## Objetivo

Integrar funciones auxiliares de validación mediante una función coordinadora sin duplicar las reglas de cálculo.

## Conocimiento esencial

- `validar_registro(...)` coordina las validaciones y recibe los datos del registro como argumentos.
- La función guarda cada respuesta en una variable y usa `return` para detenerse ante el primer error.
- Si `validar_meta` devuelve `"OK"`, continúa con `validar_defectos`; después llama a `validar_horas`.
- Un registro válido devuelve `"OK"`; un registro inválido devuelve el mensaje de la primera regla incumplida.
- El orden de las instrucciones dentro de la función es vertical, de arriba hacia abajo; no se trata de una ejecución general de izquierda a derecha.

## Lo que construyó el estudiante

El archivo contiene `validar_meta`, `validar_defectos`, `validar_horas` y `validar_registro`. La función coordinadora reutiliza las tres funciones auxiliares en lugar de copiar sus reglas.

## Evidencia

- Archivo: `practica_s03.py`
- Revisión: se inspeccionó el archivo guardado y se comprobó la integración de las cuatro funciones.
- Ejecución: observada. Se ejecutaron casos válido, meta inválida, defectos excesivos, horas inválidas, defectos negativos y meta/defectos inválidos.
- Resultados aportados por el estudiante: `Caso válido: OK`, mensajes correctos para cada caso inválido.
- Explicación: demostrada. El estudiante explicó el orden `validar_meta → validar_defectos → validar_horas` y que `return` termina la función al encontrar un error.
- Método de validación: revisión estática, ejecución del archivo y explicación con palabras propias.

## Errores y correcciones

- La terminal mostró algunas tildes deformadas al ejecutar el archivo. La causa fue la codificación de salida de la consola; no cambió la lógica ni los resultados del programa. Las notas se conservaron en UTF-8.

## Pendiente

Nada para este bloque. La validación semanal de la Semana 3 permanece separada.

## Conexiones

- [[04 - S03-B3 - Validar registros]]
- [[Python desde 0 - Índice]]
- [[Capa 2 - Wiki/Índice de conocimientos]]
