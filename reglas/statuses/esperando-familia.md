---
name: esperando-familia
tipo: status
titulo: Esperando familia
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
  - reunion-presentacion
sale_hacia:
  - avanzan
  - desiste
bloqueantes: []
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Esperando familia

La pelota está del lado de la familia: falta que confirme, que entregue algo o que
responda. **Cómo se ve en el dato:** aparece en Kommo como `ESPERANDO FAMILIA` y como
`ESPERANDO FLIA`. Son el mismo estado; ver [regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md).

Es un estado de espera, y los estados de espera son los que hacen el tiempo del embudo. Ver
[time-to-lead](../metrics/time-to-lead.md).

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
