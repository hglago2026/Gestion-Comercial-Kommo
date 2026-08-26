---
name: regla-fecha-de-corte
tipo: rule
titulo: Fecha de corte, cierre al 31-3 y archivo mensual
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: todas las métricas y la ocupación
afecta_a:
  - cupo
  - evento-de-lead
  - proceso-archivo-mensual
bloqueantes:
  - G3
  - H1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Fecha de corte, cierre al 31-3 y archivo mensual

## Enunciado

**Confirmado (requerimientos del equipo):**

1. Hay un **hito de cierre al 31 de marzo** de cada año para evidenciar actividad comercial.
2. Hay que **archivar el status al cierre de cada mes** para poder armar curvas históricas.

## Por qué es la regla que más discusiones causa

**La mayoría de las discrepancias entre dos números nacen acá**, no en la fórmula. Dos
personas con la misma fórmula, distinta fecha de corte, obtienen resultados distintos y
ninguna está equivocada.

Tres cosas que hay que distinguir y suelen mezclarse:

- **Fecha del hecho** — cuándo pasó (el evento).
- **Fecha de corte** — hasta cuándo se cuenta.
- **Fecha de la foto** — cuándo se sacó el dato.

## Cómo se cumple técnicamente

No con un archivo mensual exportado a mano, sino con historia en la Capa 1: si están todos
los [evento-de-lead](../entities/evento-de-lead.md) con su fecha, el estado al 31 de marzo se **reconstruye**, no se
archiva. Ver [proceso-archivo-mensual](../processes/proceso-archivo-mensual.md).

El [cupo](../entities/cupo.md) es la excepción incómoda: si no se guarda su historia, la ocupación pasada no se
puede reconstruir aunque los eventos estén completos.

## Decisiones abiertas

- **A DEFINIR (H1)** — snapshots reconstruidos vs archivados, y con qué periodicidad.
- **A DEFINIR (G3)** — corte por defecto cuando nadie lo aclara.
