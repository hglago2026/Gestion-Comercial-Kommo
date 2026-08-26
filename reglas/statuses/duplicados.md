---
name: duplicados
tipo: status
titulo: Duplicados
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
  - prospectos
sale_hacia: []
bloqueantes:
  - E1
  - B6
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Duplicados

El caso ya existe en el sistema. **Confirmado:** los duplicados existen y hoy están
marcados en el prototipo v11 con `CodigoDuplicado`.

**A DEFINIR (B6):** qué es un duplicado. No es lo mismo *la misma persona cargada dos veces*
que *la misma persona que postuló en otro ciclo o en otra sede*. La primera es un error de
carga; la segunda es información valiosa (recupero de solicitudes anteriores) que el equipo
pidió explícitamente. Ver [regla-duplicados](../rules/regla-duplicados.md).

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
