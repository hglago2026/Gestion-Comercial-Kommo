---
name: regla-ciclo-lectivo
tipo: rule
titulo: Ciclo lectivo y convivencia de ciclos
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: todas las métricas
afecta_a:
  - ciclo-lectivo
  - postulacion
bloqueantes:
  - G4
  - G3
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Ciclo lectivo y convivencia de ciclos

## Enunciado

**Confirmado (requerimiento del equipo):** de **abril en adelante conviven dos ciclos** —el
corriente y el siguiente— y el reporte debe mostrar ambos.

## Consecuencia práctica

**Ninguna métrica del embudo tiene sentido sin decir de qué ciclo habla.** Un número sin
ciclo, entre abril y diciembre, es ambiguo por construcción. Por eso `ciclo` es dimensión
obligatoria en toda la Capa 2 y por eso [gq-cuantos-inscriptos](../golden_questions/gq-cuantos-inscriptos.md) es una golden question.

## Decisiones abiertas

- **A DEFINIR (G4)** — el segundo campo de ciclo (`ciclo_nivel`), hoy placeholder sin carga.
- **A DEFINIR (G3)** — qué ciclo se asume cuando el usuario no lo aclara. Esto pertenece al
  [el contrato](../../CONTRATO.md) (Capa 4), no a la Capa 2.
