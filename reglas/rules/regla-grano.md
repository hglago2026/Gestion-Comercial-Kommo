---
name: regla-grano
tipo: rule
titulo: El grano del modelo
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: todo el modelo
afecta_a:
  - alumno
  - postulacion
  - lead
bloqueantes:
  - A1
  - A3
  - B6
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# El grano del modelo

## Estado: **A DEFINIR — es la decisión de fondo del proyecto**

## Lo que hay (v2, prototipo v11)

**Dos capas:**

- **cruda / auditoría** — `lead_evento` (~935k filas) + `lead` (~44k, con duplicados
  marcados por `es_duplicado`).
- **derivada limpia** — `postulante`, agrupando por `CodigoDuplicado`.

**Confirmado:** funcionó para auditar el dato. **No alcanza** para el objetivo v3.

## Lo que el replanteo v3 propone revisar

Si la unidad de análisis es el [alumno](../entities/alumno.md), la cadena natural es:

`[persona](../entities/persona.md)` → *N* `[postulacion](../entities/postulacion.md)` → *N* `[lead](../entities/lead.md)` → *N* `[evento-de-lead](../entities/evento-de-lead.md)`

...y "colapsar duplicados" deja de ser la operación central. La pregunta **B6** puede tumbar
toda la lógica actual de deduplicación.

## Decisiones abiertas

- **A DEFINIR (A1)** — qué es un alumno.
- **A DEFINIR (A3)** — grano de la postulación.
- **A DEFINIR (B6)** — deduplicación.

**Nada de la Capa 2 se puede certificar antes de cerrar esto.**
