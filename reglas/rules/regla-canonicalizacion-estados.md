---
name: regla-canonicalizacion-estados
tipo: rule
titulo: Canonicalización de estados (negocio vs CRM)
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: todos los estados
afecta_a:
  - kommo-export-eventos
  - evento-de-lead
bloqueantes:
  - E1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Canonicalización de estados (negocio vs CRM)

## Enunciado

**Un estado, un nombre.** Las variantes del CRM se resuelven a un estado canónico antes de
llegar a la Capa 2.

**Confirmado:** `ESPERANDO FLIA` y `ESPERANDO FAMILIA` son el mismo estado. También hay que
resolver mayúsculas, acentos y espacios.

## El problema mayor: dos vocabularios

No es solo ortografía. Conviven **el vocabulario del negocio** (el mapa de status que
escribió el equipo en [sheet-requerimientos-ingresos](../sources/sheet-requerimientos-ingresos.md)) y **el vocabulario del CRM** (lo que
aparece en [kommo-export-eventos](../sources/kommo-export-eventos.md)). Ejemplos sin resolver:

| Negocio | CRM | Estado |
|---|---|---|
| Intercambio OK | `ICBIO OK` | ¿es lo mismo? **A DEFINIR (E1)** |
| Lista de espera | `RESERVA PRE ICBIO` / `ESPERANDO VACANTE(HNO)` | **A DEFINIR (E1)** |
| Avanzan | *no existe en el CRM* | ¿estado o agrupación? **A DEFINIR (E1)** |
| Inscripto | `GRABADO EN ABM` / `PAGO RESERVA` | **A DEFINIR (E1, D7)** |

**Sugerencia (no es decisión tomada):** que el nombre canónico sea el del **negocio** y el
del CRM quede como alias, porque el negocio sobrevive a los cambios de herramienta. La
decisión es del equipo.

## Qué se rompe si cambia

Todas las páginas de `/statuses` y el numerador o denominador de casi todas las métricas.
