---
name: inscripto
tipo: status
titulo: Inscripto
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
  - grabado-abm
sale_hacia:
  - documentacion
bloqueantes:
  - E1
  - D7
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Inscripto

**Confirmado:** inscripto = **contrato firmado + DI**. Ocurre en el ABM, no en Kommo.

Esta página existe sobre todo para responder la pregunta que abre el
[gq-cuantos-inscriptos](../golden_questions/gq-cuantos-inscriptos.md): cuando alguien pregunta *"¿cuántos inscriptos tenemos?"*, ¿se
refiere a este estado, a [grabado-abm](grabado-abm.md), a [pago-reserva](pago-reserva.md)? Son números distintos.

**A DEFINIR (D7, E1)** — cuál de estos estados es "inscripto" a los fines del reporte.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
