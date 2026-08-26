---
name: contactos-leads
tipo: status
titulo: Contactos / Leads
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
proceso: proceso-admision
responsable: A DEFINIR (E2) — transcribir del Sheet
origen_del_nombre: sheet
entra_desde: []
sale_hacia:
  - prospectos
bloqueantes: []
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Contactos / Leads

Punto de entrada del embudo. Una familia dejó sus datos o fue cargada por la Secretaría
de Ingresos. Todavía no se sabe si es un caso viable.

**Cómo se ve en el dato:** en [kommo-export-eventos](../sources/kommo-export-eventos.md) el estado literal del CRM es `NUEVO`.
Ver [regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) para la correspondencia entre el nombre del negocio
y el nombre del CRM.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
