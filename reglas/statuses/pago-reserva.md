---
name: pago-reserva
tipo: status
titulo: Pago de reserva
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
proceso: proceso-admision
responsable: A DEFINIR (E2) — transcribir del Sheet
origen_del_nombre: kommo
entra_desde:
  - grabado-abm
  - reserva-pre-icbio
sale_hacia:
  - en-curso
bloqueantes:
  - E1
  - D7
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Pago de reserva

Estado literal de Kommo. **A DEFINIR (E1, D7):** si el pago de reserva es un hito
comercial dentro de Kommo o el reflejo de un hecho administrativo que ocurre en el ABM.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
