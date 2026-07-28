---
tags: [python, esquema, capa-3, reglas-ia]
capa: 3
---

# Constitución de la Wiki de programación

Este archivo define cómo una IA debe administrar la memoria de aprendizaje de Python.

## Arquitectura

### Capa 1 - Fuentes originales

- Contiene libros, artículos, documentos y otras fuentes en bruto.
- Es la fuente principal y fidedigna.
- Es inmutable: no editar, renombrar, reemplazar ni eliminar documentos.
- Registrar procedencia, fecha, tamaño, páginas y hash.
- Una nueva edición se guarda como una fuente adicional.

### Capa 2 - Wiki sintetizada

- Contiene conceptos, resúmenes temáticos, relaciones y notas de aprendizaje.
- La IA puede crear y actualizar estas notas.
- Toda afirmación tomada de un libro debe enlazar la fuente e indicar la página.
- Diferenciar `fuente consultada`, `código ejecutado`, `explicación demostrada` y `pendiente de comprobar`.
- Evitar duplicados: actualizar una nota relacionada antes de crear otra.

### Capa 3 - Esquema

- Contiene estas reglas, convenciones y flujos de trabajo.
- Solo se modifica cuando cambia deliberadamente la arquitectura.
- Ninguna nota de la Capa 2 puede contradecir estas reglas sin registrar primero el cambio aquí.

## Flujo para incorporar una fuente

1. Copiar el archivo sin modificarlo a la Capa 1.
2. Comprobar que se puede abrir.
3. Calcular su hash y registrarlo en el índice de fuentes.
4. No crear afirmaciones sobre su contenido sin leer las páginas correspondientes.
5. Cuando un bloque necesite el material, sintetizar únicamente el tema requerido en la Capa 2.
6. Añadir referencias cruzadas entre concepto, fuente, bloque y evidencia práctica.

## Convenciones

- Escribir Markdown en UTF-8 y conservar las tildes.
- Usar títulos claros en español; conservar nombres técnicos de Python en su forma original.
- Citar con un enlace al PDF y página exacta siempre que sea posible.
- No inventar autores, páginas, resultados, dominio ni progreso.
- No mezclar este sistema con `English Learning Notes`.
- Conservar los archivos existentes y sus enlaces salvo que exista una migración explícita y verificada.

## Autoridad del progreso

- Los libros aportan conocimiento de referencia, pero su presencia no demuestra aprendizaje.
- La Capa 2 registra lo sintetizado y la evidencia real.
- `$cerrar-bloque-aprendizaje` determina si un bloque está validado.
- ProjectLibre refleja avance administrativo y puede estar retrasado.
- Leer un capítulo no equivale automáticamente a dominar el tema.

## Recuperación e indexación inspiradas en QMD

- Buscar primero en el conocimiento ya sintetizado antes de recorrer fuentes extensas.
- Recuperar solo los documentos necesarios para la pregunta o bloque actual.
- Usar contexto jerárquico para distinguir fuentes, conocimiento sintetizado y reglas.
- Preferir búsqueda literal para identificadores exactos y búsqueda semántica o híbrida para preguntas conceptuales.
- Tratar cualquier índice, embedding, puntuación o reordenamiento como ayuda de recuperación, no como evidencia ni fuente de verdad.
- Verificar contra la Capa 1 las afirmaciones que dependan de libros o fuentes externas.
- Considerar los índices de búsqueda como datos derivados y reconstruibles; no guardarlos en la Capa 1.
- Si QMD está habilitado, comprobar su estado y actualizar el índice después de cambios relevantes.
- Si QMD no está disponible, aplicar el mismo proceso mediante búsqueda local de texto y lectura selectiva.
