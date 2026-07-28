---
tags: [python, wiki, capa-2, planificacion, auditoria, alineacion]
capa: 2
estado: con-plan-de-accion
fecha: 2026-07-28
---

# Auditoría de alineación — plan oficial vs. trabajo real (antes de la Semana 10)

Esta nota **no es una síntesis de conocimiento**. Es una auditoría de planificación. No cuenta como bloque validado ni como aprendizaje demostrado.

Responde a una pregunta del estudiante: *«¿hemos estado haciendo lo que demanda la planificación, o nos hemos desviado?»*. Es la segunda auditoría del proyecto; la primera fue [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]], que comparó el trabajo contra la **especificación**. Esta compara el trabajo contra el **plan de bloques** y contra el propio código.

## Origen y método

Erick pidió primero el `analizador_produccion.py` completo con las doce semanas, para ver «cómo debería verse» y juzgar si el aprendizaje va alineado.

**No se escribió.** Dos razones, ambas del propio proyecto:

- `PROYECTO.md`, criterio de aceptación: «El estudiante puede explicar el flujo principal **sin copiarlo**».
- **S12-B1 es «Integrar la versión final».** El programa completo *es* el entregable de la Semana 12. Escribirlo hoy eliminaría las Semanas 10, 11 y 12.

Al aclararlo, el objetivo real resultó ser la auditoría, no el código. Es la misma distinción de [[Tecnica Feynman aplicada a la programacion]]: la IA como herramienta de prueba, no de instrucción.

**Fuentes, todas verificadas en disco:**

- El XML exportado del `.pod`: nombres, fechas y porcentaje de los 78 elementos del plan.
- `analizador-produccion/PROYECTO.md`.
- `analizador-produccion/analizador_produccion.py`, medido con recuentos, no leído por encima.
- Los 24 archivos de `practicas/` y las 33 notas de bloque del vault.

---

## Hallazgo 1 — Las Semanas 3, 6 y 7 nunca llegaron al programa

**Es el hallazgo principal.** El bloque puente del 27 de julio migró al programa real los cálculos de las Semanas 8 y 9. No migró nada de las Semanas 3, 6 y 7.

| Medición sobre `analizador_produccion.py` | Valor | Bloque que lo exige |
| --- | ---: | --- |
| Líneas | 138 | — |
| Funciones definidas | **1** | S03-B2, S07-B1 |
| Docstrings | **0** | S07-B4 |
| Anotaciones de tipo | **1** | S07-B3 |
| Bloques `try/except` | **0** | S06-B1 |
| Constantes con nombre | **0** | S07-B3 |
| Reglas de validación | **1 de 9** | `PROYECTO.md` |

El contraste importa: `practicas/practica_s06.py` **sí** tiene `try/except`, y `practicas/practica_s07.py` **sí** tiene funciones y anotaciones.

> El conocimiento está demostrado. El programa no lo contiene.

Es una consecuencia estructural de cómo se trabajó: nueve semanas en archivos de práctica sueltos, y un programa real creado al final que solo heredó lo más reciente.

## Hallazgo 2 — Dos campos obligatorios se cargan pero no se usan

`datos/produccion.csv` tiene los ocho campos que exige la especificación. El programa convierte y lee **cuatro**. `id_registro` y `fecha` entran en cada diccionario y **no se referencian nunca**.

No es casual que sean esos dos: son justamente los que necesitan dos validaciones exigidas —duplicados (S06-B3) y fechas inválidas—, que tampoco están implementadas.

## Hallazgo 3 — Un hueco real en el plan, no un descuido del estudiante

`PROYECTO.md` exige reportar nueve situaciones: campos vacíos, fechas inválidas, valores no numéricos, cantidades negativas, meta no positiva, horas no positivas, defectuosas mayores que producidas, identificadores duplicados y divisiones entre cero.

Implementada: **solo la séptima**.

Y aquí está el problema del plan: **ningún bloque de las Semanas 10 a 12 dice «implementar las validaciones»**. S11-B3 dice «**probar** validaciones y registros inválidos», dando por supuesto que existen.

El plan enseña las validaciones en la Semana 6 y las prueba en la Semana 11, pero nunca dice cuándo se escriben en el programa real. Esto no lo causó Erick.

## Hallazgo 4 — El ritmo va muy por delante del calendario, y está explicado

| | Planificado | Real |
| --- | --- | --- |
| Semana 0 | 2026-07-20 | ~2026-07-14 |
| Semana 9 | 2026-09-21 | 2026-07-26 |
| Semana 12 | 2026-10-12 | — |

La Semana 9 se cerró **57 días antes** de lo planificado. El caso extremo fue el 17 de julio: **once bloques validados en un solo día** (de S03-B3 a S05-B4, las Semanas 4 y 5 completas más dos bloques).

**No es una desviación.** Erick estudia a diario y cierra cada semana conforme entiende los temas, no según el calendario. El `.pod` asume una cadencia de estudiante a tiempo parcial; su disponibilidad real ronda las 10 h diarias, según [[Próxima ruta - Análisis de datos (post-fundamentos)]].

> El criterio de avance ha sido la comprensión, no la fecha. Las fechas del `.pod` son una estimación inicial superada por los hechos, no un objetivo incumplido.

La única cautela, tomada de Marzano en [[Tecnica Feynman aplicada a la programacion]]: el conocimiento **procedimental** —la sintaxis— necesita repetición aunque el concepto se entienda a la primera. El proyecto ya lo comprobó: al cerrar la Semana 9 Erick señaló por sí mismo que no recordaba la sintaxis de `with open`, y el paso 6 del bloque puente lo resolvió reconstruyéndola de memoria. Es una cautela sobre **el tipo de práctica**, no sobre la velocidad.

## Hallazgo 5 — Las Semanas 0, 1 y 2 no tienen notas, y es normal

Quince elementos al 100 % en ProjectLibre sin ningún registro en la wiki.

Causa verificada y benigna: `Prueba 1.py` (14 jul), `practica_s01_b1.py` (15 jul) y `practica_s02.py` (16 jul) demuestran que ese trabajo se hizo **antes de que existiera el vault**, cuya primera nota es del 16 de julio.

No hay nada que rehacer. Queda dicho para que el vault no aparente un vacío que no existe.

## Hallazgo 6 — Cuatro trabajos fuera del plan, correctamente etiquetados

Las notas 20 (calculadora), 26 (práctica adicional), 32 (explicación del tutor) y 33 (bloque puente) no figuran en ProjectLibre. Todas están marcadas como práctica complementaria o explicación del tutor, **no** como bloques oficiales. El avance no queda inflado.

## Hallazgo 7 — Un incidente de registro, ya corregido

La nota 26 se registró en su día como S08-B4, cuando el objetivo oficial de ese bloque era otro. Se detectó al leer el plan de ProjectLibre y se corrigió renombrando la nota y abriendo el S08-B4 real, sin reescribir el log.

Queda como precedente de método: los errores de registro se corrigen con una entrada nueva, no borrando la historia.

---

## Veredicto

**Alineación de temario: correcta.** Todos los bloques oficiales de las Semanas 3 a 9 tienen su nota validada, en orden, y los objetivos coinciden con los del plan.

**Alineación de producto: incompleta.** Lo aprendido no se acumuló en el programa real. El programa contiene las Semanas 5, 8 y 9; le faltan la 3, la 6 y la 7.

La distinción importa porque el criterio de cierre no evalúa las notas, sino el programa: *«otra persona ejecuta el programa usando solo el README»*.

---

## Plan de acción

Objetivo: que en la Semana 12 quede por hacer **integrar**, no reconstruir.

**No se crea un segundo bloque puente.** Los huecos encajan en bloques que ya existen, y añadir semanas extra retrasaría S10 sin necesidad.

| Hueco | Dónde se cierra | Por qué encaja ahí |
| --- | --- | --- |
| Organización en funciones (S07-B1) y `if __name__ == "__main__":` | **S10-B1** | Recibir un argumento obliga a crear un `main()`; la separación de responsabilidades deja de ser teórica |
| Anotaciones de tipo y docstrings (S07-B3, S07-B4) | **S10-B1 a S10-B3**, sobre cada función nueva | Se documenta al escribir, no después |
| Archivo inexistente o ilegible, con `try/except` (S06-B1) | **S10-B2** | Es su objetivo literal y reutiliza las excepciones ya validadas |
| Códigos de salida y constantes (S07-B3) | **S10-B3** | Los códigos de salida *son* constantes con nombre |
| Las ocho validaciones que faltan, leyendo `id_registro` y `fecha` | **Paso previo a S11-B1** | S11-B3 presupone que existen; hay que escribirlas antes de poder probarlas |
| Pruebas de esas validaciones | **S11-B3**, sin cambios | Ya estaba previsto |

El único añadido real es ese **paso previo al inicio de la Semana 11**. Corrige una omisión del plan, no introduce temario nuevo: todo su contenido conceptual está validado en las Semanas 2, 3 y 6.

## Comprobación de que el plan funcionó

Al llegar a S12-B1, el programa debe cumplir:

- [ ] Se ejecuta como `python .\analizador_produccion.py .\datos\produccion.csv`
- [ ] Separa lectura, validación, cálculo y presentación en funciones
- [ ] Las nueve reglas de validación reportan, cada una, su motivo
- [ ] Usa `id_registro` y `fecha`
- [ ] Las funciones importantes tienen docstring y anotaciones de tipo
- [ ] Los códigos de salida son constantes con nombre
- [ ] Genera los tres reportes en `salidas/` sin tocar el original
- [ ] Las pruebas pasan
- [ ] Erick explica el flujo sin mirar el código

Si al abrir S12-B1 quedan casillas sin marcar, la Semana 12 volverá a ser reconstrucción. Esa es la señal a vigilar.

## Conexiones

- [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]] — auditoría anterior, contra la especificación
- [[33 - Bloque puente - Proyecto real, reportes y primera prueba]] — la deuda que sí se saldó
- [[Tecnica Feynman aplicada a la programacion]] — la IA como herramienta de prueba, y lo declarativo frente a lo procedimental
- [[Índice de conocimientos]]
