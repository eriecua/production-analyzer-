---
tags: [python, fuentes, capa-1, github, qmd]
capa: 1
tipo: fuente-web
estado: consultado
---

# tobi/qmd - repositorio consultado

## Identificación

- Proyecto: QMD - Query Markup Documents.
- Repositorio oficial: https://github.com/tobi/qmd
- Autor del repositorio: `tobi`.
- Fecha de consulta: 2026-07-17.
- Estado local: QMD no está instalado ni configurado en este sistema de aprendizaje.
- Naturaleza: el repositorio es una fuente web mutable. Esta nota registra lo consultado en la fecha indicada; si cambia de forma importante, crear un nuevo registro en lugar de alterar silenciosamente este.

## Información documentada por el proyecto

- QMD es un buscador local para notas Markdown, documentación y bases de conocimiento.
- Combina búsqueda de texto completo BM25, búsqueda semántica mediante vectores y reordenamiento con un modelo local.
- Organiza documentos en colecciones.
- Permite añadir contexto descriptivo global y por rutas; el contexto más específico ayuda a seleccionar documentos relevantes.
- Ofrece `search` para coincidencias literales, `vsearch` para similitud semántica y `query` para búsqueda híbrida con reordenamiento.
- Puede recuperar un documento con `get` o varios con `multi-get`.
- La máscara predeterminada de una colección es `**/*.md`.
- Después de cambiar rutas, patrones o exclusiones se debe actualizar el índice; los embeddings se generan por separado.
- Puede integrarse con agentes mediante salida JSON, listas de archivos o un servidor MCP.

## Uso adoptado en esta Wiki

QMD se usa como referencia de diseño para recuperar conocimiento, no como autoridad sobre el contenido. El índice de búsqueda sería derivado y reconstruible. Las fuentes originales, las notas verificadas y la Constitución de la Wiki conservan la autoridad.

## Referencias principales

- README: https://github.com/tobi/qmd#readme
- Configuración de ejemplo: https://github.com/tobi/qmd/blob/main/example-index.yml
