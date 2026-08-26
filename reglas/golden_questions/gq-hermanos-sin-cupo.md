---
name: gq-hermanos-sin-cupo
tipo: golden_question
titulo: ¿Cuántas familias de la comunidad quedaron sin cupo este ciclo?
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
pregunta: "¿Cuántas familias de la comunidad quedaron sin cupo este ciclo?"
metricas:
  - efectividad-comercial
entidades:
  - familia
  - alumno
reglas:
  - regla-duplicados
respuesta_esperada: A DEFINIR
tolerancia: A DEFINIR
bloqueantes:
  - K1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# ¿Cuántas familias de la comunidad quedaron sin cupo este ciclo?

> "¿Cuántas familias de la comunidad quedaron sin cupo este ciclo?"

**Esta golden question hoy no tiene respuesta posible, y por eso está acá.**

Es el requerimiento que el equipo escribió —lista de espera calificada por hermano sin
cupo— y que demuestra por qué el modelo centrado en el [lead](../entities/lead.md) no alcanza.

## Qué haría falta

1. La entidad [familia](../entities/familia.md) — **A DEFINIR (C1)**.
2. Saber quién ya es [alumno](../entities/alumno.md) de la red — **A DEFINIR (A1, D1)**.
3. Poder unir a la persona del CRM con la del ABM — **A DEFINIR (B2)**.

**Confirmado, y es lo llamativo:** el CRM **ya tiene** el estado
[esperando-vacante-hno](../statuses/esperando-vacante-hno.md). El negocio venía tratando a la familia como unidad mucho antes de
que el modelo de datos la tuviera. La pregunta no es nueva: lo nuevo sería poder
contestarla.

## Qué debería hacer la IA

Según el [el contrato](../../CONTRATO.md): resolver lo que tenga default declarado, **repreguntar** lo
que no, y etiquetar la respuesta como **dato certificado**, **interpretación** o
**hipótesis**. Nunca mezclarlos sin distinguir.

## Respuesta esperada

**A DEFINIR (G1)** — se completa cuando las métricas estén certificadas. El valor va con la
versión de la definición usada.
