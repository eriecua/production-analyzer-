---
tags: [python, validacion, semana-3, bloque-3]
tipo: bloque
semana: 3
bloque: S03-B3
estado: validado
fecha: 2026-07-17
---

# S03-B3 - Crear función para validar registros

## Objetivo

Crear una función que coordine las validaciones de meta, defectos y horas antes de aceptar un registro.

## Conocimiento esencial

- Una función de validación puede devolver `OK` o un mensaje de error.
- `resultado = funcion(argumentos)` guarda el valor devuelto por otra función.
- `if resultado != "OK"` permite detener la validación cuando ya existe un error.
- La función principal puede llamar a especialistas en un orden definido: meta, defectos y horas.
- Si todos los controles pasan, la última validación devuelve `OK`.

## Lo que construyó el estudiante

Integró `validar_meta(...)`, `validar_defectos(...)` y `validar_horas(...)` dentro de `validar_registro(...)`. Ejecutó cinco casos: uno válido y cuatro inválidos.

## Evidencia

- Archivo: `practica_s03.py`
- Revisión: se leyó el archivo guardado y se comprobó que existe una sola definición de `validar_registro(...)`.
- Ejecución: observada en esta sesión; los cinco casos produjeron los resultados esperados.
- Explicación: demostrada; el estudiante explicó las cinco reglas de aceptación y rechazo.
- Método de validación: revisión estática, ejecución observada y explicación del estudiante.

## Errores y correcciones

- Se corrigió el retorno faltante que producía `None` cuando todas las validaciones eran correctas.
- Se eliminó la definición duplicada de `validar_registro(...)`.

## Pendiente

Nada para este bloque.

## Conexiones

- [[03 - S03-B2 - Funciones para cada KPI]]
- [[Python desde 0 - Índice]]
