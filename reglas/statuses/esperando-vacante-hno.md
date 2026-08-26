---
name: esperando-vacante-hno
tipo: status
titulo: Esperando vacante (hermano)
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
  - postulante
sale_hacia:
  - reserva-pre-icbio
  - desiste
bloqueantes:
  - E1
  - C1
  - C2
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Esperando vacante (hermano)

Estado literal de Kommo (`ESPERANDO VACANTE(HNO)`). **Confirmado:** el CRM ya distingue
el caso de hermano sin cupo — es decir, **el negocio ya venía tratando a la familia como
unidad aunque el modelo de datos no la tenga.**

Es la evidencia más clara de por qué hace falta la entidad [familia](../entities/familia.md) y por qué el modelo
centrado en el lead se queda corto. Ver [lista-de-espera](lista-de-espera.md) y **A DEFINIR (C1, C2)**.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
