---
name: familia
tipo: entity
titulo: Familia
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - familia
grano: un grupo familiar
clave_natural: A DEFINIR (C1)
reglas:
  - regla-duplicados
bloqueantes:
  - C1
  - C2
  - C3
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Familia

El equipo trabaja con familias, no con individuos: habla de *familia de la comunidad*, de
*hermanos*, de *referidos*. El CRM lo sabe —guarda el nombre de la familia en `Entity Name`
y tiene el estado [esperando-vacante-hno](../statuses/esperando-vacante-hno.md)— pero el modelo de datos no tiene la entidad.

## Qué habría que definir

- **A DEFINIR (C1):** qué constituye una familia. ¿Comparten un adulto responsable?
  ¿Comparten domicilio? ¿Se declaran hermanos?
- **A DEFINIR (C2):** qué prioridad da ser hermano de un alumno, y cómo se refleja en la
  [lista-de-espera](../statuses/lista-de-espera.md).
- **A DEFINIR (C3):** si "familia de la comunidad" incluye ex alumnos y personal.

Cada una de estas es una regla de negocio con consecuencias en quién entra al colegio. **El
wiki no las propone: las pregunta.**

## Decisiones abiertas

- **A DEFINIR (C1, C2, C3)**
