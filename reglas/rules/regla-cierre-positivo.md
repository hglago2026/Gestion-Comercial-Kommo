---
name: regla-cierre-positivo
tipo: rule
titulo: Qué cuenta como cierre positivo
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: conversión y embudo
afecta_a:
  - conversion-a-cierre-positivo
bloqueantes:
  - E1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Qué cuenta como cierre positivo

## Estado: **definición de trabajo del proyecto, NO ratificada por el equipo**

Se usó para poder medir algo en el prototipo v11. **Está escrita acá justamente para que se
pueda discutir y reemplazar**, no para que se convierta en dogma por repetición.

**Definición provisoria usada:**

- **POSITIVO** — alcanzó alguna vez [reserva-pre-icbio](../statuses/reserva-pre-icbio.md), [icbio-ok](../statuses/icbio-ok.md), [grabado-abm](../statuses/grabado-abm.md),
  [pago-reserva](../statuses/pago-reserva.md) o [en-curso](../statuses/en-curso.md).
- **NEGATIVO** — [rechazado](../statuses/rechazado.md), [baja](../statuses/baja.md), [desiste](../statuses/desiste.md), [historico](../statuses/historico.md), perdido o "no familia".

## Los dos supuestos que esconde

1. **"Alcanzó alguna vez"** — un caso que llegó a reserva y después se cayó cuenta como
   positivo. Se puede defender (midió la gestión comercial) y se puede discutir (no terminó
   en matrícula).
2. **La lista de espera no está** en esta definición, aunque **sí está** en el numerador de
   [efectividad-comercial](../metrics/efectividad-comercial.md). Dos métricas con criterios distintos de "éxito". Puede ser
   correcto —miden cosas distintas— pero tiene que estar decidido, no ser un accidente.

## Decisiones abiertas

- **A DEFINIR (G1)** — ratificar o reemplazar esta definición.
