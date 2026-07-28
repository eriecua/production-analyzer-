---
tags: [python, wiki, capa-2, planificacion, auditoria]
capa: 2
estado: pendiente-de-comprobar
fecha: 2026-07-26
---

# Auditoría de congruencia — plan vigente vs. especificación (antes de la Semana 10)

Esta nota **no es una síntesis de conocimiento**. Es una auditoría de planificación realizada al cerrar la Semana 9, comparando lo realmente construido contra la especificación del proyecto y las reglas declaradas en el propio vault. No cuenta como bloque validado ni como aprendizaje demostrado.

Fuentes consultadas para esta auditoría (todas internas, verificadas en disco):

- `analizador-produccion/PROYECTO.md` — especificación y criterio final de aceptación.
- `Plan_completo_ProjectLibre_para_Claude.pdf` y el XML exportado del `.pod` — objetivos oficiales de las Semanas 10 a 12.
- [[Ruta de Python del video de Programador X - análisis y adaptación]] — reglas pedagógicas derivadas.
- [[Próxima ruta - Análisis de datos (post-fundamentos)]] — condición de activación de la siguiente ruta.
- Archivos de práctica reales: `practica_s08.py`, `practica_s09.py` y los CSV generados.

## Veredicto general

Los temas de las Semanas 10, 11 y 12 **sí son congruentes** con los objetivos declarados. El problema no está en el temario, sino en la **deuda acumulada entre lo practicado y lo que exige el criterio de cierre**.

| Semana | Objetivo oficial | Respaldo declarado |
|---|---|---|
| S10 | Uso desde consola | `PROYECTO.md`: ejecución final `python .\analizador_produccion.py .\datos\produccion.csv` |
| S11 | Pruebas y calidad | Regla pedagógica: las pruebas evitan que una función que ya servía deje de funcionar |
| S12 | Integración y presentación | Criterio de cierre: otra persona ejecuta el programa usando solo el README |

## Desajustes detectados

### 1. El programa real no existe

`analizador_produccion.py` no está creado. La carpeta `analizador-produccion/` contiene únicamente la especificación, los generadores de PDF y archivos `README.md` de marcador de posición en `datos/`, `salidas/` y `tests/`. Tampoco existe `datos/produccion.csv`.

Todo el trabajo validado hasta ahora vive en archivos de práctica sueltos (`practica_s01` … `practica_s09`) fuera de la carpeta del proyecto.

### 2. Regresión de CSV a datos escritos a mano

La Semana 5 validó la lectura de CSV con `DictReader`. Sin embargo, las Semanas 8 y 9 se construyeron sobre cinco diccionarios escritos directamente en el código. La especificación exige que los registros provengan del CSV.

### 3. Faltan dos de los ocho campos obligatorios

`PROYECTO.md` exige `id_registro`, `fecha`, `turno`, `producto`, `meta_unidades`, `unidades_producidas`, `unidades_defectuosas` y `horas_trabajadas`.

Los registros de práctica actuales tienen seis: faltan `id_registro` y `fecha`, que son precisamente los que requieren las validaciones de duplicados y fechas inválidas ya trabajadas en la Semana 6.

### 4. Divergencia en la fórmula de productividad

- `PROYECTO.md`: `Productividad = unidades buenas / horas trabajadas`.
- Practicado y registrado en [[25 - S08-B3 - Comparar productividad y calidad]]: `unidades_producidas / horas_trabajadas`, descrita como "productividad bruta".

Debe reconciliarse antes de la integración final, o documentarse explícitamente como dos indicadores distintos.

### 5. Falta el tercer reporte y la ubicación es incorrecta

El criterio exige tres CSV en `salidas/`: `resumen_general.csv`, `resumen_por_turno.csv` y `resumen_por_producto.csv`.

Estado real: se generaron dos de los tres (turno y producto), y quedaron en el directorio de trabajo de las prácticas, no en `salidas/`. El resumen general se mostró en consola en [[28 - S09-B1 - Disenar el resumen general]] pero nunca se exportó a archivo.

## Tensión metodológica declarada

[[Ruta de Python del video de Programador X - análisis y adaptación]] establece: *"Mantener las pruebas como hábito gradual; no reservarlas únicamente para el final."*

El plan de ProjectLibre concentra la totalidad de las pruebas unitarias en la Semana 11. Es una contradicción entre una regla del vault y el calendario vigente. No se resuelve modificando el plan, sino escribiendo pruebas puntuales durante la Semana 10 en lugar de esperar a la 11.

## Corrección menor pendiente

[[Próxima ruta - Análisis de datos (post-fundamentos)]] indica como condición de activación la última nota `S08-B4`. Está desactualizada: la última validada es [[31 - S09-B4 - Mostrar un resumen legible en consola]]. La condición real sigue siendo cerrar la Semana 12 completa.

## Plan de acción para la próxima sesión

Objetivo: eliminar la deuda acumulada antes de iniciar la Semana 10, para que S12 sea una integración y no una reconstrucción.

Se propone tratarlo como un **bloque puente** (práctica de transferencia, no bloque oficial), en este orden:

**Paso 1 — Crear el CSV real**
Escribir `analizador-produccion/datos/produccion.csv` con los ocho campos obligatorios y al menos los cinco registros ya conocidos, más una fila inválida deliberada para probar validaciones. Los valores de turno, producto, unidades, defectos y horas deben coincidir con los ya comprobados manualmente para poder verificar contra resultados conocidos.

**Paso 2 — Sembrar el programa real**
Crear `analizador-produccion/analizador_produccion.py` que lea ese CSV con `DictReader`, convierta los campos numéricos a `int` y muestre los registros cargados. Este paso reutiliza lo validado en la Semana 5; no introduce conceptos nuevos.

**Paso 3 — Migrar los cálculos ya validados**
Trasladar desde `practica_s08.py` y `practica_s09.py` los acumuladores por turno y por producto, los indicadores y la identificación de mejores/peores resultados. Reconciliar aquí la fórmula de productividad con la especificación.

**Paso 4 — Completar los tres reportes**
Añadir la exportación de `resumen_general.csv` y dirigir los tres archivos a `salidas/`. Comprobar que `datos/produccion.csv` no se modifica.

**Paso 5 — Primera prueba automática**
Escribir una única prueba en `tests/` que compruebe un cálculo ya verificado a mano (por ejemplo, que el total producido sea 440). Esto cumple la regla de no dejar todas las pruebas para el final, sin adelantar el temario de la Semana 11.

**Paso 6 — Repaso pendiente**
Reconstruir de memoria, sin consultar código previo, un bloque `with open(...) as f:` con `csv.DictWriter`. Punto señalado por el propio estudiante y registrado en [[31 - S09-B4 - Mostrar un resumen legible en consola]].

Solo después de estos seis pasos conviene abrir S10-B1 (recibir la ruta CSV como argumento), porque ese bloque asume que ya existe un programa que recibe una ruta.

## Estado de esta nota

`pendiente-de-comprobar`: ninguno de los seis pasos se ha ejecutado. Actualizar esta nota conforme se completen, o archivarla cuando la deuda quede saldada.

## Conexiones

- [[Python desde 0 - Índice]]
- [[31 - S09-B4 - Mostrar un resumen legible en consola]]
- [[Próxima ruta - Análisis de datos (post-fundamentos)]]
- [[Ruta de Python del video de Programador X - análisis y adaptación]]
