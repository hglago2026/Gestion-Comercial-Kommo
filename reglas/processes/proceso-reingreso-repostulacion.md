---
name: proceso-reingreso-repostulacion
tipo: process
titulo: Reingreso y repostulación
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema_soporte: A DEFINIR
entidades:
  - persona
  - postulacion
estados:
  - duplicados
metricas: []
bloqueantes:
  - B6
  - B4
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Reingreso y repostulación

Una familia que postuló en un ciclo anterior y vuelve a intentarlo.

**Confirmado:** el equipo lo pidió como **recupero de solicitudes anteriores**.

## Por qué hoy no se puede medir

Porque hoy eso se ve como un [duplicados](../statuses/duplicados.md) y la lógica del prototipo lo colapsa. Ver
[regla-duplicados](../rules/regla-duplicados.md): **la regla de deduplicación actual borra exactamente lo que este
proceso quiere medir.**

## Pregunta con dato disponible

**A DEFINIR (B4):** cuántas personas repostulan entre ciclos. Esta es una de las pocas
preguntas del cuestionario que **se puede responder auditando el export actual** en vez de
esperar al equipo — cruzando nombres y familias entre ciclos en
[kommo-export-eventos](../sources/kommo-export-eventos.md).
