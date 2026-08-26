---
name: avanzan
tipo: status
titulo: Avanzan
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
  - reunion-presentacion
  - esperando-familia
  - lista-de-espera
sale_hacia:
  - intercambio-ok
  - taller-intercambio
bloqueantes:
  - E1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Avanzan

Rama de continuidad del embudo, no un estado de reposo: el caso sigue hacia la
instancia de intercambio.

**Confirmado:** acá interviene el DOE leyendo las encuestas ([app-doe](../sources/app-doe.md)) y bifurca según el
nivel — **K1–K2** van a [intercambio-ok](intercambio-ok.md); **K3 en adelante** van a
[taller-intercambio](taller-intercambio.md). Ver [postulantes-actividad-intercambio](../metrics/postulantes-actividad-intercambio.md).

**A DEFINIR (E1):** si `AVANZAN` es un estado real del pipeline o una forma de agrupar en el
Sheet. Es una de las diferencias entre el mapa del negocio y el vocabulario del CRM.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
