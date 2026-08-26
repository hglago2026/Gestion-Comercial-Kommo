---
name: evento-de-lead
tipo: entity
titulo: Evento de lead
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - evento de lead
grano: un cambio de estado o de campo, con fecha y hora
clave_natural: Event ID
fuentes:
  - kommo-export-eventos
reglas:
  - regla-canonicalizacion-estados
bloqueantes: []
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Evento de lead

**Confirmado:** la unidad más fina que tiene el proyecto. Cada fila del
[kommo-export-eventos](../sources/kommo-export-eventos.md) es un evento con fecha **y hora**, lo que permite medir permanencia
al minuto.

Es la tabla de hechos natural de la Capa 1: `lead_evento`.

## Por qué es la pieza que hace posible la historia

Un estado actual responde "¿cómo está hoy?". Una secuencia de eventos responde "¿cómo estaba
el 31 de marzo?" — que es exactamente lo que pide [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md).

## Cómo se arma la permanencia (dwell)

Por lead, ordenar los eventos `Type ID = 14` por fecha. El estado que *sostiene* un intervalo
es el `Value After` del evento anterior; el primer intervalo arranca en la creación
(`Type ID = 1`). El último estado queda **abierto** (censurado, sin dwell).

**Confirmado:** se filtran dwell negativos y mayores a 2000 días. Ver [time-to-lead](../metrics/time-to-lead.md).
