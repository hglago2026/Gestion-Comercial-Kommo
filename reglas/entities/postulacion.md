---
name: postulacion
tipo: entity
titulo: Postulación
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - postulacion
grano: A DEFINIR (A3)
clave_natural: A DEFINIR
fuentes:
  - kommo-export-eventos
reglas:
  - regla-grano
  - regla-ciclo-lectivo
bloqueantes:
  - A3
  - B6
  - G4
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Postulación

El intento de una [persona](persona.md) de entrar a una [colegio-sede](colegio-sede.md) en un [ciclo-lectivo](ciclo-lectivo.md) y un
[nivel](nivel.md) determinados.

**Es la entidad puente**: una persona puede tener varias postulaciones (otro año, otra
sede), y eso es información valiosa, no un error de carga. Distinguirla del [lead](lead.md) es lo
que permite responder *"¿cuántos de los que postularon este año ya lo habían intentado
antes?"*, que el equipo pidió como **recupero de solicitudes anteriores**.

## Grano

**A DEFINIR (A3):** una postulación por persona × sede × ciclo, o por persona × ciclo
(permitiendo postular a varias sedes dentro de la misma postulación).

## Relación con el lead

**A DEFINIR (B6).** Hoy el prototipo v11 agrupa por `CodigoDuplicado` para armar un
*postulante* a partir de varios leads. Esa lógica puede quedar obsoleta si se define
[persona](persona.md) + N postulaciones. Ver [regla-duplicados](../rules/regla-duplicados.md).

## Ciclo

**A DEFINIR (G4):** el segundo campo de ciclo. Hoy existe un placeholder `ciclo_nivel` sin
carga. Ver [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md).
