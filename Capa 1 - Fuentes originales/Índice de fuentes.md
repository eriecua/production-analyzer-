---
tags: [python, fuentes, capa-1, libros]
capa: 1
estado: verificado
---

# Capa 1 - Fuentes originales

Esta carpeta conserva los documentos originales que sirven como fuente principal para el aprendizaje de programación. Los archivos son inmutables: la IA puede leerlos y citarlos, pero no editarlos, renombrarlos ni reemplazarlos.

## Libros registrados

| Fuente | Autor o entidad | Páginas | Tamaño | SHA-256 |
|---|---|---:|---:|---|
| [[Libros de programación/Coding Projects in Python (DK) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Coding Projects in Python]] | DK | 226 | 21.87 MiB | `FB8542C74396FAC51EF18FE255573C7696B9C06570A8DA505FA3004590CA3383` |
| [[Libros de programación/Python Basics A Practical Introduction to Python 3 (Real Python) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Python Basics: A Practical Introduction to Python 3]] | Real Python | 627 | 5.81 MiB | `7A1CF0E05C3F8583C567889AC7FC8444A06D483C96E5599AF88EB78EE3F6A99F` |
| [[Libros de programación/Python for Data Analysis A Basic Programming Crash Course to Learn Python Data Science Essential Tools, Pandas, and Numpy with… (Oscar Scratch) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Python for Data Analysis]] | Oscar Scratch | 130 | 0.56 MiB | `C3850ABDE15FB40061C80447204C29F79794E199150DA654F9F5DF3193271551` |
| [[Libros de programación/Python_Beginner_To_Pro.pdf\|Python Beginner To Pro]] | Autor no indicado en los metadatos | 506 | 9.18 MiB | `D80BD9D533F35903FAE87317050C34BEBF81678055BC053D91D8F2C10B49B102` |
| [[Libros de programación/Python for Data Analysis (Wes McKinney) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Python for Data Analysis (Wes McKinney)]] | Wes McKinney | 582 | 8.95 MiB | `F4E88A0D412831491C0CD456A91DD385800DD8ECD87914E2B4D48F3CCBBB4D08` |
| [[Libros de programación/SQL Cookbook Query Solutions and Techniques for All SQL Users (Anthony Molinaro, Robert de Graaf) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|SQL Cookbook]] | Anthony Molinaro, Robert de Graaf | 572 | 12.43 MiB | `D00F37196EBBAF1D5773B4B9D4FED2D5198E77427D554C5E46C2740335963E8` |
| [[Libros de programación/SQL for Data Analysis Advanced Techniques for Transforming Data into Insights (Cathy Tanimura) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|SQL for Data Analysis]] | Cathy Tanimura | 359 | 10.74 MiB | `1D54D6523964876D44C2D3C4CC9ED9D36DD4A57F78A9F8A4F2661FC143ADAA96` |
| [[Libros de programación/Power BI 4 in 1- Beginners Guide+ Tips and Tricks+ Simple and Effective Strategies to learn Power Bi and Power Query+ An… (Jones, Daniel) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Power BI 4 in 1]] | Daniel Jones | 489 | 10.86 MiB | `3237856456EDC62A326DAA0FB428E01847CA47B648B13A64B60F5D7EB97F4F17` |
| [[Libros de programación/Power Pivot and Power BI. The Excel User’s Guide to DAX, Power Query, Power BI  Power Pivot in Excel 2010-2016 (Rob Collie, Avichal Singh) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Power Pivot and Power BI]] | Rob Collie, Avichal Singh | 330 | 14.79 MiB | `501A447F62823A08C9DD8412C391EAD205D9C1162EE8D2EEAD5F9D7A48E9286` |
| [[Libros de programación/The Art and Science of Teaching A Comprehensive Framework for Effective Instruction (Robert J. Marzano) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|The Art and Science of Teaching]] | Robert J. Marzano (ASCD, 2007) | 234 | 1.60 MiB | `3D809B47179B879BF9E7467AF73712119252925F1332E09EE45196D1A0DFA3C3` |

## Procedencia y verificación

- Carpeta de origen (primeros cuatro libros): `C:\Users\MSI ERICK\Downloads\LIBROS PROGRAMACION`.
- Fecha de incorporación (primeros cuatro libros): 2026-07-17.
- Se verificó que los cuatro archivos pueden abrirse como PDF y se obtuvo su cantidad de páginas.
- Fecha de incorporación (cinco libros de análisis de datos, SQL y Power BI): 2026-07-26.
- Los cinco libros nuevos se verificaron con `pypdf`: se confirmó apertura, cantidad de páginas, autor de metadatos y hash SHA-256.
- El hash permite comprobar en el futuro que una fuente no cambió.
- Registrar una edición nueva como otro archivo; nunca sobrescribir la edición ya incorporada.
- Fecha de incorporación (Marzano, pedagogía): 2026-07-27. Verificado con `pypdf`: 234 páginas y hash SHA-256. Sus metadatos internos están corruptos —autor `debra`, título `10408-00_FM.indd`, artefactos de la maquetación—, por lo que autor y título de la tabla proceden de la portada y la página de créditos, no de los metadatos.

## El libro de pedagogía es de otra naturaleza

Los nueve primeros libros son **fuentes de contenido**: enseñan Python, SQL o Power BI. El de Marzano es una **fuente de método**: no contiene programación, sino el marco con el que se decide cómo enseñar.

Se usa, por tanto, de forma distinta. No se sintetiza para un bloque del plan, sino para fundamentar la skill `tutor-adaptativo-python` y para que Erick reconozca por qué el curso está estructurado como está. Su síntesis vive en [[Capa 2 - Wiki/Tecnica Feynman aplicada a la programacion]].

Estructura del libro: diez preguntas de diseño instruccional, una por capítulo. Las directamente aplicables a este proyecto son el capítulo 2 (interactuar con conocimiento nuevo, p. 29), el capítulo 3 (practicar y profundizar, p. 58) y el capítulo 4 (generar y poner a prueba hipótesis, p. 86).

## Cómo se conectan los libros nuevos con el sistema

El plan de aprendizaje ya trabaja con registros de producción en CSV, agrupación por turno/producto y cálculo de KPIs (Semanas 5 y 8). Los cinco libros incorporados el 2026-07-26 extienden esa misma línea hacia el resto del flujo de análisis de datos, sin sustituir el plan de Python vigente:

- [[Libros de programación/Python for Data Analysis (Wes McKinney) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Python for Data Analysis (Wes McKinney)]] — referencia estándar de `pandas`/`NumPy`; complementa el uso actual de `dict`, listas y `csv.DictReader` cuando el plan llegue a análisis con `pandas`.
- [[Libros de programación/SQL Cookbook Query Solutions and Techniques for All SQL Users (Anthony Molinaro, Robert de Graaf) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|SQL Cookbook]] y [[Libros de programación/SQL for Data Analysis Advanced Techniques for Transforming Data into Insights (Cathy Tanimura) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|SQL for Data Analysis]] — cubren consultas y análisis en SQL; siguiente fuente natural cuando los registros dejen de venir solo de CSV.
- [[Libros de programación/Power BI 4 in 1- Beginners Guide+ Tips and Tricks+ Simple and Effective Strategies to learn Power Bi and Power Query+ An… (Jones, Daniel) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Power BI 4 in 1]] y [[Libros de programación/Power Pivot and Power BI. The Excel User’s Guide to DAX, Power Query, Power BI  Power Pivot in Excel 2010-2016 (Rob Collie, Avichal Singh) (z-library.sk, 1lib.sk, z-lib.sk).pdf\|Power Pivot and Power BI]] — DAX, Power Query y Power BI; útiles cuando el objetivo pase de calcular KPIs en Python a presentarlos en un dashboard.

Estos libros quedan registrados como fuente disponible. Siguiendo la regla de la Capa 3, no se debe sintetizar su contenido en la Capa 2 hasta que un bloque del plan lo requiera.

## Fuentes web registradas

- [[Fuentes web/tobi-qmd - repositorio]] — Diseño de recuperación local para documentos Markdown y flujos con agentes. Consultado el 2026-07-17.
- [[Fuentes web/Programador X - La Mejor Ruta Para Aprender PYTHON]] — Video con un mapa general de fundamentos, temas avanzados, frameworks y pruebas. Consultado el 2026-07-21.
- [[Fuentes web/Tecnica Feynman - cuatro articulos]] — Cuatro artículos sobre la técnica Feynman (Virginia Law, Todoist, Wispr Flow, Thomas Oppong), con sus pasos, citas literales y límites declarados. Consultados el 2026-07-27.

## Cómo citar una fuente

En una nota de la Capa 2, enlazar el PDF e indicar la página utilizada. Ejemplo:

```text
Fuente: [[Libros de programación/Python_Beginner_To_Pro.pdf#page=25|Python Beginner To Pro, p. 25]]
```
