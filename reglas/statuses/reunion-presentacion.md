---
name: reunion-presentacion
tipo: status
titulo: Reunión de presentación
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
  - invitados-a-reunion
sale_hacia:
  - desiste
  - esperando-familia
  - lista-de-espera
  - avanzan
bloqueantes:
  - E1
  - E5
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Reunión de presentación

La familia asistió. Es el numerador de [efectividad-convocatoria](../metrics/efectividad-convocatoria.md) y el **denominador
de [efectividad-comercial](../metrics/efectividad-comercial.md)**, la métrica más mirada del embudo.

**Confirmado:** el equipo distingue reuniones por tipo —presencial / virtual × individual /
grupal— y quiere medirlas por separado. Ver [reuniones-por-tipo](../metrics/reuniones-por-tipo.md).

**A DEFINIR (E5):** si "asistió" se registra como estado, como campo o como evento de
calendario. De eso depende que la métrica se pueda calcular.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
