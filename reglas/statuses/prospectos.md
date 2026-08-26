---
name: prospectos
tipo: status
titulo: Prospectos
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
  - contactos-leads
sale_hacia:
  - duplicados
  - incontactables
  - desisten-en-contacto-inicial
  - filtro-semaforo
  - invitados-a-reunion
bloqueantes: []
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Prospectos

El contacto fue trabajado y calificado. Del total de contactos, los que llegan acá son
la base de [calidad-de-leads](../metrics/calidad-de-leads.md).

Desde este estado se abren las cuatro salidas de descarte ([duplicados](duplicados.md),
[incontactables](incontactables.md), [desisten-en-contacto-inicial](desisten-en-contacto-inicial.md), [filtro-semaforo](filtro-semaforo.md)) y la salida de
avance ([invitados-a-reunion](invitados-a-reunion.md)).

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
