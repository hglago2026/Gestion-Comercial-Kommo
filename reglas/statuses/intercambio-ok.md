---
name: intercambio-ok
tipo: status
titulo: Intercambio OK
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
proceso: proceso-admision
responsable: A DEFINIR (E2) — transcribir del Sheet
origen_del_nombre: ambos
entra_desde:
  - avanzan
  - taller-intercambio
sale_hacia:
  - grabado-abm
  - reserva-pre-icbio
bloqueantes:
  - E1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Intercambio OK

La instancia de intercambio dio resultado favorable. Es el último tramo antes de que el
caso salga de Kommo hacia el [abm-sedna-hosking-handing](../sources/abm-sedna-hosking-handing.md).

**Cómo se ve en el dato:** en Kommo conviven `ICBIO OK` y `RESERVA PRE ICBIO`. La relación
exacta entre el vocabulario del Sheet (*intercambio*) y el del CRM (*ICBIO*) está
**A DEFINIR (E1)**.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
