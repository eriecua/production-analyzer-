---
tags: [wiki, capa-2, metodologia, feynman, marzano, aprendizaje, programacion]
capa: 2
estado: sintesis-metodologica
fecha: 2026-07-27
---

# Técnica Feynman aplicada a la programación

Síntesis de cinco fuentes: los cuatro artículos de [[Capa 1 - Fuentes originales/Fuentes web/Tecnica Feynman - cuatro articulos]] y el capítulo 3 de [[Capa 1 - Fuentes originales/Libros de programación/The Art and Science of Teaching A Comprehensive Framework for Effective Instruction (Robert J. Marzano) (z-library.sk, 1lib.sk, z-lib.sk).pdf|Marzano, *The Art and Science of Teaching*]].

Esta nota **no enseña Python**. Explica por qué el curso está construido como está, y qué hacer cuando algo no se entiende.

---

## Pepita 1 — Hay dos tipos de conocimiento, y se aprenden distinto

Es el hallazgo más útil de todo el material, porque resuelve una tensión real de este proyecto.

Marzano distingue, apoyándose en Anderson (1983, 1995):

| | **Declarativo** | **Procedimental** |
|---|---|---|
| Qué es | Saber **que** algo es así | Saber **hacer** algo |
| En Python | Por qué el acumulador necesita `if not in` | Teclear `with open(...)` sin consultar |
| Cómo se gana | Explicando, comparando, revisando | **Practicando. No hay atajo** |
| Cómo se comprueba | Técnica Feynman | Reconstruir de memoria |

Fuente: Marzano, cap. 3, pp. 60–61 (páginas físicas 69–70 del PDF).

### Por qué importa aquí

Erick declaró: «me gustaría entender la lógica para cualquier situación, en lugar de solo fijarme en formatos». Es una preferencia **por lo declarativo**, y es correcta para los conceptos.

Pero la sintaxis es conocimiento **procedimental**, y ahí la preferencia no basta. Marzano cita a Anderson, Reder y Simon (1995):

> «In denying the critical role of practice one is denying children the very thing they need to achieve real competence.» (p. 62)

Y la fuente de Virginia Law lo confirma desde el otro lado: la técnica Feynman es **menos eficaz para temas basados principalmente en memorización**.

**Dos fuentes independientes coinciden**: explicar con tus palabras comprueba los conceptos, pero no da fluidez con la sintaxis. Eso solo lo da repetir.

### Qué hacer con esto

- ¿No entiendes **por qué** algo funciona? → Feynman: explícalo con tus palabras.
- ¿No **recuerdas** cómo se escribe? → Repetición: reconstrúyelo de memoria.

Confundir los dos produce frustración. Ninguna cantidad de explicación conceptual hará que recuerdes `newline=""`.

---

## Pepita 2 — «What I cannot create, I do not understand»

Frase de Feynman, escrita en su pizarra al morir. Recogida por Thomas Oppong.

Es el criterio de comprensión más exigente y más honesto que hay, y **es directamente ejecutable en programación**, donde otras disciplinas solo pueden aspirar a la metáfora: puedes literalmente intentar crearlo y ver si funciona.

El **paso 6 del bloque puente** —reconstruir el bloque de escritura CSV sin consultar nada— fue exactamente esta prueba. Y funcionó como diagnóstico: reveló que la estructura estaba retenida y que solo faltaban los paréntesis de llamada.

**Regla operativa:** un tema no está aprendido cuando lo entiendes leyéndolo. Está aprendido cuando puedes escribirlo desde cero.

---

## Pepita 3 — Los errores no son fallos del proceso; son el proceso

Marzano recoge a Brown y Burton (1978), que **comparan el desarrollo del conocimiento con depurar una rutina de computadora**: la comprensión de un estudiante contiene «bugs», que se corrigen mediante examen continuo (cap. 3, p. 63).

La analogía es literal en este curso: los errores en la cabeza de Erick y los errores en su código **son la misma clase de cosa**, y se arreglan igual — aislando, probando y corrigiendo.

Marzano llama a esto **error analysis**, y lo clasifica como actividad para *profundizar* el conocimiento, no como accidente que estorba el aprendizaje.

### Evidencia de este proyecto

El error más productivo de la sesión del 2026-07-27 fue `buenas_por_producto[producto] = ...` en lugar de `+=`. Erick lo diagnosticó solo con una pista: «no estoy acumulando, creo la fórmula pero no el acumulador». Ese error enseñó más que cualquier explicación previa sobre acumuladores.

**Consecuencia práctica:** cuando algo falle, no pedir la solución de inmediato. El intento fallido es donde se forma el aprendizaje.

---

## Pepita 4 — «Presentar poco material cada vez» está respaldado por investigación

Marzano cita a Rosenshine (2002):

> «The most effective teachers presented only small amounts of material at a time. After this short presenting, these teachers then guided students…» (cap. 3, p. 61)

Esto **confirma de forma independiente** la regla que se añadió a `tutor-adaptativo-python` el mismo día en que se leyó esta fuente: una sola tarea accionable por mensaje. La regla se escribió a partir de la experiencia de una sesión concreta; resulta que coincide con la investigación instruccional.

Rosenshine llama a la fase siguiente **guided practice**: práctica guiada, no ejercicio mecánico. Durante ella el estudiante organiza, revisa, ensaya, resume, compara y contrasta.

**Distinción importante que hace Marzano** (p. 62): la práctica eficaz *no* es repetición mecánica de pasos memorizados. Es examinar y dar forma a los pasos iniciales. La mala fama de «la práctica» viene de confundirla con el *drill*.

---

## Pepita 5 — La comprensión inicial no basta, y se pierde

> «This initial understanding, albeit a good one, does not suffice for learning that is aimed at long-term retention… Without this type of extended processing, knowledge that students initially understand might fade and be lost over time.» (cap. 3, p. 58)

Entender algo hoy no significa saberlo dentro de tres semanas. Marzano describe tres formas de desarrollar un esquema mental (p. 60):

- **Acreción** — acumular conocimiento nuevo.
- **Ajuste (*tuning*)** — expresar lo mismo de forma más económica.
- **Reestructuración** — reorganizar lo que ya se sabe, produciendo comprensión nueva.

**Las tres están en este proyecto:** las notas de bloque son acreción; reescribir una explicación más corta es ajuste; descubrir que `[]` significa dos cosas distintas —crear lista o buscar— fue reestructuración.

Y justifica una práctica del vault: Marzano recomienda que los estudiantes **vuelvan a sus cuadernos a hacer cambios y añadidos**, tanto para agregar como para corregir concepciones erróneas iniciales (p. 59). Las notas de la Capa 2 deben poder revisarse; no son un archivo muerto.

---

## Pepita 6 — Cómo usar la IA, según la fuente más rigurosa

El artículo de Virginia Law es la única de las cuatro fuentes que aborda esto, y su recomendación es concreta:

> Usar la IA como **herramienta de prueba** (*test tool*), no como **herramienta de instrucción** (*instruction tool*) durante el aprendizaje inicial.

Traducido a este proyecto: el valor de la IA no está en que explique primero, sino en que **compruebe después**. La secuencia correcta es intentar → explicar con tus palabras → que el tutor detecte el hueco.

Esto coincide con la regla del método de este curso: nunca contar una explicación del tutor como comprensión demostrada por el estudiante. La nota [[32 - Refactorizar a funcion y para que sirve un test]] está marcada así precisamente por eso.

---

## El procedimiento, en cuatro pasos

Las tres fuentes serias coinciden en esto:

1. **Estudiar** el concepto. Elegir uno solo y escribirlo en una página en blanco.
2. **Explicarlo sin mirar apuntes**, como si fuera para alguien de primer año. En voz alta o por escrito.
3. **Volver a la fuente donde te atasques.** El punto exacto donde te trabas es el hueco. No es un fracaso: es el diagnóstico.
4. **Simplificar y crear analogías propias.** Si necesitas jerga, todavía no lo dominas.

> «No pude reducirlo al nivel de primer año. Eso significa que realmente no lo entendemos.» — Feynman, recogido por Todoist

### Aplicado a Python, en concreto

- **Paso 1:** un concepto por bloque. Nunca dos.
- **Paso 2:** explicar sin mirar el código. Ejemplo real que funcionó: «with open lo que hace es abrir y cerrar el archivo».
- **Paso 3:** el punto donde te atascas explicando **es** el concepto que falta. Nombrarlo en voz alta ya es medio diagnóstico.
- **Paso 4:** las analogías deben ser tuyas. Las del tutor ayudan a entender; las propias demuestran que entendiste.

---

## Advertencia sobre las analogías

Este proyecto ha producido analogías útiles —el archivador y los cajones, la máquina con entrada y salida, la bolsa que recoge lo del bucle— registradas en [[26 - Practica adicional - Funciones y cumplimiento por producto]].

Pero toda analogía se rompe en algún punto, y ese punto hay que conocerlo. El archivador explica bien qué es una clave y un valor; no explica que un diccionario conserva el orden de inserción, cosa que sí importó al escribir el primer `assert`.

**Regla:** cuando una analogía deje de funcionar, no forzarla. Sustituirla o abandonarla.

---

## Qué cambia en la práctica de este curso

| Antes | A partir de ahora |
|---|---|
| Todo se trata igual | Distinguir si el problema es de concepto o de fluidez |
| «¿Entendiste?» | «Explícamelo con tus palabras» |
| El error interrumpe | El error es material de aprendizaje; se analiza antes de corregir |
| La nota se escribe una vez | La nota se revisa cuando el conocimiento cambia |
| El tutor explica primero | El estudiante intenta primero; el tutor comprueba después |

## Conexiones

- [[Capa 1 - Fuentes originales/Fuentes web/Tecnica Feynman - cuatro articulos]] — las fuentes sin interpretar
- [[33 - Bloque puente - Proyecto real, reportes y primera prueba]] — donde se aplicó la prueba de reconstrucción de memoria
- [[32 - Refactorizar a funcion y para que sirve un test]] — nota marcada como explicación del tutor, por la regla de la pepita 6
- [[26 - Practica adicional - Funciones y cumplimiento por producto]] — las analogías de diccionarios
- [[Índice de conocimientos]]
