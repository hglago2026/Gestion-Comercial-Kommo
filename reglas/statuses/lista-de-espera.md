---
name: lista-de-espera
tipo: status
titulo: Lista de espera
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
sale_hacia:
  - avanzan
  - desiste
bloqueantes:
  - E1
  - C2
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Lista de espera

La familia quiere avanzar pero no hay cupo. **Confirmado:** cuenta en el numerador de
[efectividad-comercial](../metrics/efectividad-comercial.md) junto con las reservas — el equipo decidió que quedar en lista de
espera es un resultado comercial positivo, no una pérdida.

**A DEFINIR (C2):** el equipo pidió una lista de espera **calificada por hermano sin cupo**.
Eso requiere la entidad [familia](../entities/familia.md) y saber quién es [alumno](../entities/alumno.md) de la red; hoy no se puede
calcular. Ver también [esperando-vacante-hno](esperando-vacante-hno.md).

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
