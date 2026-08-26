---
name: proceso-pase-de-sede
tipo: process
titulo: Pase de sede
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema_soporte: A DEFINIR
entidades:
  - persona
  - colegio-sede
estados:
  - paso-de-sede
metricas:
  - pases-de-sede
bloqueantes:
  - B6
  - A1
  - E8
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Pase de sede

Una familia que ya está en la red pide cambiar de sede.

**Confirmado:** el equipo pidió medir **solicitudes**, **concretados** y **tiempo** entre
ambos. Kommo tiene un estado [paso-de-sede](../statuses/paso-de-sede.md).

## Por qué hoy no se puede medir

Un pase es **la misma persona** apareciendo en otra sede. Sin [persona](../entities/persona.md) estable:

- se ve como dos casos distintos, o
- se marca como [duplicados](../statuses/duplicados.md) y se colapsa, perdiendo el hecho de que hubo un pase.

Ver [regla-duplicados](../rules/regla-duplicados.md). **Es uno de los cinco requerimientos del equipo que hoy no cierran
por falta de la entidad [alumno](../entities/alumno.md).**

## Decisiones abiertas

- **A DEFINIR (E8)** — dónde se registra la solicitud de pase y dónde el concretado.
