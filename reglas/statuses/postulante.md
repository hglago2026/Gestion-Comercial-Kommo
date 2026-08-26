---
name: postulante
tipo: status
titulo: Postulante (Kommo)
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
  - nuevo
sale_hacia:
  - esperando-familia
  - esperando-vacante-hno
bloqueantes:
  - E1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Postulante (Kommo)

Estado literal de Kommo. **Confirmado (medido en el export del 2026-08-04):** es el
estado donde más tiempo se acumula — mediana de **46 días en NFS**, 24,8 en CDF Benavidez,
15,2 en CDF Puertos y 17,5 en LTH Hudson. Esa dispersión entre sedes es, hoy, el hallazgo
operativo más accionable del prototipo.

**A DEFINIR (E1):** a qué tramo del mapa del negocio corresponde.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
