---
name: proceso-admision
tipo: process
titulo: Proceso de admisión (embudo completo)
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema_soporte: Kommo + App DOE + ABM
entidades:
  - postulacion
  - alumno
  - familia
estados:
  - contactos-leads
  - prospectos
  - invitados-a-reunion
  - reunion-presentacion
  - avanzan
  - intercambio-ok
  - grabado-abm
  - inscripto
  - documentacion
  - legajo
metricas:
  - calidad-de-leads
  - efectividad-convocatoria
  - efectividad-comercial
bloqueantes:
  - D1
  - D7
  - E1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Proceso de admisión (embudo completo)

## El hallazgo que ordena todo

**El embudo NO termina en Kommo.** Esto es lo más importante de esta página:

```
        ── Kommo ──────────────────────────────────┐   ── ABM ──────────────────┐
CONTACTOS → PROSPECTOS → INVITADOS → REUNIÓN →     │                            │
            AVANZAN → INTERCAMBIO OK →             │ GRABADO ABM → INSCRIPTO →  │
                                                   │ DOCUMENTACIÓN → LEGAJO     │
        ───────────────────────────────────────────┘ ───────────────────────────┘
                                                     ↑
                                            acá nace el ALUMNO
```

Un modelo que solo lee Kommo puede medir la gestión comercial pero **no puede decir cuántos
alumnos tiene la red**. Ver [abm-sedna-hosking-handing](../sources/abm-sedna-hosking-handing.md).

## Secuencia

1. [contactos-leads](../statuses/contactos-leads.md) → 2. [prospectos](../statuses/prospectos.md) → salidas de descarte ([duplicados](../statuses/duplicados.md),
[incontactables](../statuses/incontactables.md), [desisten-en-contacto-inicial](../statuses/desisten-en-contacto-inicial.md), [filtro-semaforo](../statuses/filtro-semaforo.md))
3. [invitados-a-reunion](../statuses/invitados-a-reunion.md) → 4. [reunion-presentacion](../statuses/reunion-presentacion.md) → ramas ([desiste](../statuses/desiste.md),
[esperando-familia](../statuses/esperando-familia.md), [lista-de-espera](../statuses/lista-de-espera.md), [avanzan](../statuses/avanzan.md))
5. El **DOE** lee las encuestas ([app-doe](../sources/app-doe.md)) y bifurca por nivel: K1–K2 a
[intercambio-ok](../statuses/intercambio-ok.md), K3+ a [taller-intercambio](../statuses/taller-intercambio.md)
6. [intercambio-ok](../statuses/intercambio-ok.md) → 7. [grabado-abm](../statuses/grabado-abm.md) → 8. [inscripto](../statuses/inscripto.md) → 9. [documentacion](../statuses/documentacion.md) →
10. [legajo](../statuses/legajo.md)

## Quién lo ejecuta

**Confirmado:** intervienen **Secretaría de Ingresos**, **Equipos Directivos** y **DOE**,
y el equipo quiere medir performance por rol.
**A DEFINIR (E2):** el reparto exacto por estado está en el Sheet y falta transcribirlo.

## Decisiones abiertas

- **A DEFINIR (E1)** — mapear el vocabulario del negocio contra el del CRM.
- **A DEFINIR (D1, D7)** — el tramo del ABM.
