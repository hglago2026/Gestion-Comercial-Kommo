---
name: taller-intercambio
tipo: status
titulo: Taller de intercambio
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
  - avanzan
sale_hacia:
  - intercambio-ok
bloqueantes:
  - E1
  - E7
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Taller de intercambio

Instancia para postulantes de **K3 en adelante**.

**Confirmado — y es el indicador de tiempo más específico que pidió el equipo:**
`Devolución Act. Ibio − Fecha Taller` debe ser **≤ 7 días**. Ver [tiempos-entre-status](../metrics/tiempos-entre-status.md).

**A DEFINIR (E7):** dónde se registran la fecha del taller y la fecha de devolución. Si no
están en un campo con fecha, el indicador no se puede calcular.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
