---
tags: [python, wiki, capa-2, qmd, recuperacion]
capa: 2
estado: diseño-adoptado
---

# QMD - recuperación local de la Wiki

QMD inspira cómo recuperar conocimiento de este vault sin cargar todos los documentos en cada conversación. No reemplaza las tres capas: funciona como un índice local derivado sobre los archivos Markdown.

Fuente: [[Capa 1 - Fuentes originales/Fuentes web/tobi-qmd - repositorio]]

## Papel dentro de la arquitectura

```text
Pregunta del estudiante
        ↓
Búsqueda en la Wiki Markdown
        ↓
Recuperación de pocas notas relevantes
        ↓
Verificación contra la Capa 1 cuando corresponda
        ↓
Respuesta, ejercicio o actualización de la Capa 2
```

- Capa 1: conserva las fuentes y sirve para comprobar afirmaciones.
- Capa 2: es la colección principal de búsqueda porque contiene conocimiento sintetizado.
- Capa 3: aporta las reglas y el contexto que orientan la selección.
- Índice QMD: es una ayuda reconstruible; nunca es la fuente principal.

## Contexto jerárquico recomendado

Si QMD se instala posteriormente, la colección debe describir las rutas de esta forma:

- `/`: aprendizaje de Python por bloques y proyecto Analizador de producción.
- `/Capa 1 - Fuentes originales`: inventario y referencias; su presencia no demuestra dominio.
- `/Capa 2 - Wiki`: conocimiento sintetizado, conceptos y relaciones comprobadas.
- `/Capa 3 - Esquema`: reglas obligatorias para agentes y mantenimiento de la Wiki.

## Estrategia de búsqueda adoptada

1. Para nombres exactos como `validar_meta`, `S03-B3` o `return`, comenzar con búsqueda literal.
2. Para preguntas conceptuales como “por qué una función devuelve None”, usar búsqueda híbrida si está disponible.
3. Limitar la consulta a la colección o ruta pertinente.
4. Recuperar únicamente las notas mejor relacionadas.
5. Si la respuesta depende de un libro, abrir la fuente y comprobar la página.
6. No interpretar una puntuación de relevancia como certeza, veracidad o aprendizaje demostrado.

## Mantenimiento futuro

- Actualizar el índice después de cambiar rutas, patrones o documentos.
- Regenerar embeddings cuando existan notas nuevas o cuando cambie el modelo de embeddings.
- Revisar el estado del índice antes de depender de sus resultados.
- Mantener fuera del índice los archivos temporales y cualquier índice generado.

## Estado actual

La estrategia está adoptada como guía, pero QMD no está instalado ni configurado. Mientras tanto, Codex debe aplicar el mismo criterio usando búsqueda local de texto y lectura selectiva de archivos.
