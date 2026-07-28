---
tags: [python, aprendizaje, bloque-puente, csv, funciones, pruebas, refactorizar]
tipo: bloque
semana: puente
bloque: Bloque puente pre-Semana 10
estado: validado
fecha: 2026-07-27
---

# Bloque puente - Proyecto real, reportes y primera prueba

## Objetivo

Cerrar la deuda técnica detectada en la auditoría previa a la Semana 10: que el analizador lea un CSV real con los ocho campos de la especificación, genere los tres reportes en `salidas/`, y quede cubierto por una prueba automatizada.

## Conocimiento esencial

- **Refactorizar es cambiar la forma sin cambiar el resultado.** El criterio de éxito no es que el código quede más bonito, sino que la salida siga siendo idéntica. La comprobación usada fue que Mañana siguiera dando `12.69`.
- **Una prueba automatizada necesita una función a la que llamar.** Con el código suelto ejecutándose de arriba a abajo solo existe una puerta —ejecutar todo—, y no se puede probar una parte por separado.
- **Los acumuladores deben declararse dentro de la función.** Si viven fuera, la segunda llamada suma sobre los restos de la primera y el resultado depende de cuántas veces se haya llamado.
- **Una prueba debe poder fallar para servir de algo.** Con un solo registro por turno, la prueba no detectaría que se sustituyera `+=` por `=`. Se comprobó empíricamente: al sabotear el acumulador, la prueba señaló la línea exacta.
- **Todo lo que escriba en el archivo va dentro del `with`; lo que solo prepare datos puede ir fuera.** Escribir fuera del bloque produce `ValueError: I/O operation on closed file`, porque el `with` cierra el archivo al salir.

## Lo que construyó el estudiante

En `analizador-produccion/analizador_produccion.py`: lectura del CSV con `csv.DictReader`, conversión de tipos, rechazo de registros inválidos con `continue`, acumuladores por turno y por producto, y los tres bloques de exportación a `salidas/`.

En `analizador-produccion/datos/produccion.csv`: seis registros con los ocho campos obligatorios, metas variadas y una fila deliberadamente inválida (70 producidas contra 90 defectuosas).

En `analizador-produccion/tests/test_resumen_por_turno.py`: la primera prueba del proyecto, con datos inventados y cinco comprobaciones con `assert`.

En `practica_memoria.py`: reconstrucción del bloque de escritura CSV sin consultar código anterior.

## Evidencia

- Archivos: `analizador-produccion/analizador_produccion.py`, `analizador-produccion/datos/produccion.csv`, `analizador-produccion/salidas/`, `analizador-produccion/tests/test_resumen_por_turno.py`, `practica_memoria.py`
- Revisión: se inspeccionó cada archivo guardado después de cada modificación.
- Ejecución: **observada**. Salida real del analizador: `5` válidos, `1` rechazado, totales `440 28 412 34`. Salida de la prueba: `OK - test_resumen_por_turno`.
- Explicación: **demostrada parcialmente**. Ver el desglose más abajo.
- Método de validación: ejecución observada, comprobación manual de valores, y una prueba de sabotaje.

### Valores comprobados a mano antes de ejecutar

```text
Mañana:  203 buenas / 16 h  = 12.69
Noche:    72 buenas /  7 h  = 10.29
Tarde:   137 buenas / 11 h  = 12.45
Totales: 440 − 28 = 412 buenas en 34 h
Filas:   5 válidos + 1 rechazado = 6 del origen
```

`datos/produccion.csv` no se modificó, cumpliendo el criterio de la especificación.

### Qué demostró el estudiante

- Escribió los tres bloques de exportación por su cuenta.
- Aplicó sin ayuda la regla de cuándo hace falta una lista: `resumen_general` sin lista por ser una sola fila, turno y producto con lista por ser varias.
- Diagnosticó solo, con una única pista, que sobrescribía en lugar de acumular: «no estoy acumulando, creo la fórmula pero no el acumulador».
- Escribió `for fila in calcular_resumen_por_turno(registros):`, llamando a la función directamente en el `for`. **Más limpio que la versión sugerida por el tutor**, y solo posible entendiendo qué devuelve `return`.
- Reconstruyó de memoria el bloque completo de escritura CSV: `import csv`, la lista de diccionarios, `with open` con sus cuatro argumentos en orden, `DictWriter`, `fieldnames`, `writeheader` y el `for` con `writerow`. Único fallo: los paréntesis de llamada.
- Explicó con sus palabras qué hace `with open` y por qué el `DictWriter` va dentro del bloque.
- Detectó que la forma de construir listas de diccionarios que se le pedía contradecía la de la Semana 4. **Tenía razón: ambas son válidas.**

### Qué explicó el tutor y sigue sin demostrarse

- La sintaxis de `assert` se entregó completa, no se dedujo.
- `sys.path.append` y `from X import Y` se entregaron completos.
- El razonamiento de la extracción de función quedó registrado como explicación del tutor en [[32 - Refactorizar a funcion y para que sirve un test]].

## Errores y correcciones

| Error | Corrección |
| --- | --- |
| `buenas_por_producto[producto] = ...` en lugar de `+=` | Sobrescribía en cada vuelta; Producto A conservaba solo el último registro. Diagnosticado por el estudiante con una pista |
| Faltaba el acumulador `buenas_por_turno` | Detectado antes de escribir el reporte, al necesitarlo la fórmula de la especificación |
| Función extraída como copia, no como mudanza | La lógica quedó duplicada y el CSV seguía alimentándose del código suelto. Se eliminó el original |
| `return registros` dentro de la prueba | La prueba devolvía su propia entrada en lugar de comprobar el resultado |
| Los tres turnos distintos en la prueba | Una prueba así no puede detectar un fallo de acumulación. Se duplicó el turno Mañana |
| `escritor.writeheader` y `escritor.writerow` sin paréntesis | Mencionaban la función sin ejecutarla. Es el error de la sección 11 de [[01 - Funciones - def y return]] |
| `print("Test pasó ✅")` | El emoji falla en consolas con codificación `cp1252`. Sustituido por texto plano |

## Deuda técnica resuelta

- **Fórmula de productividad**: se adoptó la de la especificación, `unidades buenas / horas trabajadas`, en lugar de la practicada en la Semana 9 con unidades producidas.
- **Datos reales**: las Semanas 8 y 9 usaban datos escritos a mano en el código.
- **`resumen_general.csv`**: nunca se había exportado.
- **`tests/README.md`**: afirmaba que las pruebas correspondían a la Semana 11; se actualizó explicando por qué se adelantó una.

## Pendiente

- **Importar `analizador_produccion.py` ejecuta el módulo completo.** Al correr la prueba aparecen los mensajes del programa y se reescriben los archivos de `salidas/`. Se resuelve con `if __name__ == "__main__":`, previsto al abrir S10-B1. Es también la causa del subrayado de Pylance en el `import` de la prueba, que es un falso positivo.
- **Extraer una función desde cero, sin molde**, y explicar por qué cada pieza va donde va. Requisito para reclasificar [[32 - Refactorizar a funcion y para que sirve un test]].
- **Escribir un `assert` sin que se entregue la sintaxis.**

## Conexiones

- [[Auditoria de congruencia - plan vigente vs especificacion (pre-Semana 10)]] — el plan de seis pasos que este bloque ejecuta
- [[32 - Refactorizar a funcion y para que sirve un test]] — explicación del tutor sobre funciones y pruebas
- [[01 - Funciones - def y return]] — definir frente a llamar, y variables internas
- [[13 - S05-B4 - Convertir filas a tipos correctos]] — conversión con `int()` al leer CSV
- [[29 - S09-B2 - Exportar resultados por turno]] — patrón de exportación reutilizado aquí
- [[Python desde 0 - Índice]]
