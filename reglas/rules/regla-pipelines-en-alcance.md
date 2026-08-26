---
name: regla-pipelines-en-alcance
tipo: rule
titulo: Qué pipelines entran en el análisis
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: toda la ingesta desde Kommo
afecta_a:
  - kommo-export-eventos
  - colegio-sede
  - conversion-a-cierre-positivo
bloqueantes:
  - D9
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Qué pipelines entran en el análisis

## Enunciado

**Confirmado (observado en el dato del 2026-08-04):** en Kommo conviven pipelines de
admisión, un pipeline de marketing y ruido.

| Pipeline | Qué es | Trato |
|---|---|---|
| NFS Puertos y Nordelta | admisión | **en alcance** |
| CDF Benavidez y Escobar | admisión | **en alcance** |
| CDF Puertos | admisión | **en alcance** |
| LTH Hudson | admisión | **en alcance** |
| Red Itínere | marketing, vocabulario propio, 0,2% de cierre | **A DEFINIR (D9)** — reportar aparte, no mezclar |
| Historico · NoEsLead · Prueba · Embudo de ventas | ruido | **A DEFINIR (D9)** — excluir |

## Por qué importa

Mezclar Red Itínere con los pipelines de admisión **hunde artificialmente cualquier tasa de
conversión de la red**. El 0,2% es correcto para lo que ese embudo hace y desastroso si se
lee como admisión. Es el caso testigo de un número bien calculado y mal entendido.

## Decisiones abiertas

- **A DEFINIR (D9)** — confirmar exclusiones y decidir si Red Itínere se reporta por
  separado o queda fuera del piloto.
