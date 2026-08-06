---
tags: [python, wiki, capa-2, planificacion, analisis-de-datos]
capa: 2
estado: planificado-pendiente-de-activacion
---

# Próxima ruta - Análisis de datos con Python, SQL y Power BI

Esta nota **no es una síntesis de conocimiento**. Es un recordatorio de planificación de proyecto: registra una decisión tomada con el usuario y el contexto profesional detrás de ella, para no perderla antes de que llegue el momento de activarla. No cuenta como bloque validado ni como aprendizaje demostrado.

## Objetivo declarado

Convertirse en experto en análisis de datos con Python, SQL y Power BI — identificadas por el usuario como las habilidades más solicitadas en el mercado actual. El fin es doble: conseguir empleo como analista de datos y, a largo plazo, contemplar la posibilidad de ofrecer consultoría propia o crear una empresa en esta área.

## Trasfondo profesional del usuario

El usuario se desempeñó como coordinador de producción, donde reportaba KPIs, gestionaba información compleja y creaba dashboards y presentaciones ejecutivas semanales en Excel. Ese trasfondo es el origen directo del proyecto "Analizador de producción" que ya existe dentro del plan vigente de Python. Su ambición de largo plazo (consultoría/empresa propia) implica que la ruta, cuando se diseñe, debe incluir también comunicación y presentación de resultados, no solo la parte técnica.

## Situación y urgencia

- Actualmente no tiene empleo y está en búsqueda activa en el área de datos; aprovecha ese tiempo para estudiar.
- No hay una fecha límite externa fija, pero la urgencia es real.
- Disponibilidad real de estudio: aproximadamente 10 horas al día de lunes a viernes (fines de semana variables) — muy por encima del ritmo pausado del plan actual de fundamentos por bloques semanales. Esto implica que, una vez activada, esta ruta puede avanzar mucho más rápido que "Python desde 0".

## Resultado tangible esperado

1. Un portafolio de 2-3 proyectos que combinen Python + SQL + Power BI, mostrable en LinkedIn/GitHub/entrevistas.
2. Aplicación directa de estas habilidades al proyecto real ya existente (analizador de producción) u otro similar.
3. Certificación formal (ej. Microsoft Power BI): opción secundaria, no prioritaria — el usuario no tiene evidencia de que correlacione con contrataciones.

## Condición de activación

Esta ruta **no se activa todavía**. Se activa solo después de cerrar el plan vigente de fundamentos de Python, es decir, al completar la Semana 12 y su validación semanal. Última nota validada al 26 de julio de 2026: [[31 - S09-B4 - Mostrar un resumen legible en consola]]. Antes de esa fecha, no crear bloques ni semanas nuevas sobre estos temas.

Existe además deuda técnica pendiente antes de la Semana 10, detallada en [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]].

## Orden acordado, con rol evaluado de cada fuente

Se revisó la tabla de contenidos completa de las fuentes candidatas en la Capa 1 antes de fijar este orden — no es una suposición sobre los títulos.

### 1. Python / pandas

- Guía principal: [[Capa 1 - Fuentes originales/Libros de programación/Python for Data Analysis (Wes McKinney) (z-library.sk, 1lib.sk, z-lib.sk).pdf|Python for Data Analysis (Wes McKinney)]] — cubre pandas/NumPy de forma progresiva (Series/DataFrame → carga de datos → limpieza → `groupby`/split-apply-combine → pivot tables), y mapea casi 1:1 con lo ya practicado manualmente en el plan de Python (CSV, limpieza, agrupación por turno/producto).
- Puente breve opcional antes del anterior, si se necesita una rampa más suave: [[Capa 1 - Fuentes originales/Libros de programación/Python for Data Analysis A Basic Programming Crash Course to Learn Python Data Science Essential Tools, Pandas, and Numpy with… (Oscar Scratch) (z-library.sk, 1lib.sk, z-lib.sk).pdf|Python for Data Analysis (Oscar Scratch)]] (130 p., introducción corta de Python básico a pandas/NumPy).
- Referencia adicional ya disponible: [[Capa 1 - Fuentes originales/Libros de programación/Python Basics A Practical Introduction to Python 3 (Real Python) (z-library.sk, 1lib.sk, z-lib.sk).pdf|Python Basics (Real Python)]] tiene capítulos de "Working With Databases" (SQLite) y "Read and Write CSV Data" que sirven de puente hacia la sección de SQL.

### 2. SQL

- Punto de entrada, incorporado el 2026-08-05: [[Capa 1 - Fuentes originales/Libros de programación/SQL Queries for Mere Mortals - John L. Viescas.pdf|SQL Queries for Mere Mortals (Viescas)]] — cubre el escalón que faltaba. Las dos fuentes de abajo dan por sabido lo básico: Tanimura enseña a pensar analíticamente y el Cookbook resuelve problemas concretos, pero ninguna enseña SQL desde cero. Viescas empieza por el modelo relacional (Parte I) y construye la sentencia `SELECT` pieza a pieza —consulta simple, columnas calculadas, filtrado (Parte II)— antes de llegar a joins y subconsultas (Parte III), agrupación y `HAVING` (Parte IV), modificación de datos (Parte V) y funciones de ventana (Parte VI, cap. 22). Es la primera fuente que abrir cuando se active esta ruta, no la última.
- Guía principal: [[Capa 1 - Fuentes originales/Libros de programación/SQL for Data Analysis Advanced Techniques for Transforming Data into Insights (Cathy Tanimura) (z-library.sk, 1lib.sk, z-lib.sk).pdf|SQL for Data Analysis (Tanimura)]] — libro de pensamiento analítico con SQL (perfilado de datos, series de tiempo, cohortes, anomalías, experimentos), no solo sintaxis.
- Referencia puntual por técnica: [[Capa 1 - Fuentes originales/Libros de programación/SQL Cookbook Query Solutions and Techniques for All SQL Users (Anthony Molinaro, Robert de Graaf) (z-library.sk, 1lib.sk, z-lib.sk).pdf|SQL Cookbook]] — consultar cuando un bloque necesite una receta concreta (joins, ventanas, pivots, running totals), no leer de forma secuencial.
- Consulta puntual adicional para conexión Python↔MySQL: [[Capa 1 - Fuentes originales/Libros de programación/Python_Beginner_To_Pro.pdf|Python Beginner To Pro]] (sin estructura clara de navegación; usar solo para buscar temas puntuales).

### 3. Power BI

- Guía principal: [[Capa 1 - Fuentes originales/Libros de programación/Power Pivot and Power BI. The Excel User’s Guide to DAX, Power Query, Power BI  Power Pivot in Excel 2010-2016 (Rob Collie, Avichal Singh) (z-library.sk, 1lib.sk, z-lib.sk).pdf|Power Pivot and Power BI (Collie/Singh)]] — progresión real de DAX (columnas calculadas → medidas → `CALCULATE()` → contexto de fila/filtro → time intelligence → variables).
- Referencia complementaria de funcionalidades sueltas: [[Capa 1 - Fuentes originales/Libros de programación/Power BI 4 in 1- Beginners Guide+ Tips and Tricks+ Simple and Effective Strategies to learn Power Bi and Power Query+ An… (Jones, Daniel) (z-library.sk, 1lib.sk, z-lib.sk).pdf|Power BI 4 in 1 (Jones)]] — compilación dispersa; usar para temas puntuales (compartir dashboards, fuentes de datos, publicación), no como guía principal de DAX.

### Fuente de baja relevancia para este objetivo

[[Capa 1 - Fuentes originales/Libros de programación/Coding Projects in Python (DK) (z-library.sk, 1lib.sk, z-lib.sk).pdf|Coding Projects in Python (DK)]] — proyectos lúdicos (turtle graphics, juegos). Útil solo para practicar fundamentos de forma entretenida; no aporta a la ruta de análisis de datos.

## Regla de diseño cuando se active

- Leer las fuentes de la Capa 1 relevantes antes de definir los bloques concretos de esta ruta; no sintetizar contenido de estos libros por adelantado.
- Sintetizar en la Capa 2 solo lo que un bloque práctico concreto necesite, igual que en el plan vigente de fundamentos (ver [[Capa 3 - Esquema/Constitución de la Wiki]]).
- Diseñar los bloques pensando también en comunicación y presentación de resultados (dashboards, reportes ejecutivos), no solo en la parte técnica, dado el trasfondo y la ambición de largo plazo del usuario.
- Priorizar reutilizar y extender el proyecto real ya existente (analizador de producción) sobre crear proyectos desconectados, para maximizar el valor de portafolio.
