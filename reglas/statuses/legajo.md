---
name: legajo
tipo: status
titulo: Legajo del estudiante
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
proceso: proceso-admision
responsable: A DEFINIR (E2) — transcribir del Sheet
origen_del_nombre: sheet
entra_desde:
  - documentacion
sale_hacia: []
bloqueantes:
  - E1
  - A1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Legajo del estudiante

Estado final del embudo de ingresos. La persona es, sin discusión, [alumno](../entities/alumno.md) de la red.

**A DEFINIR (A1):** si el legajo completo es la definición operativa de alumno, o si alumno
se es desde [grabado-abm](grabado-abm.md). Es exactamente la pregunta A1 del cuestionario, y de ella
depende todo el modelo.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
