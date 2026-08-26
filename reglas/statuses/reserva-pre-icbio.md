---
name: reserva-pre-icbio
tipo: status
titulo: Reserva pre-ICBIO
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
  - intercambio-ok
  - postulante
sale_hacia:
  - icbio-ok
  - pago-reserva
bloqueantes:
  - E1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Reserva pre-ICBIO

Estado literal de Kommo. **A DEFINIR (E1):** relación con [lista-de-espera](lista-de-espera.md) y con el
concepto de *reserva* que usa el numerador de [efectividad-comercial](../metrics/efectividad-comercial.md). **Esta ambigüedad
es material:** de ella depende qué se cuenta como reserva.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
