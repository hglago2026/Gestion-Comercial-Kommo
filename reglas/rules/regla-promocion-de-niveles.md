---
name: regla-promocion-de-niveles
tipo: rule
titulo: Promoción de niveles para proyectar ocupación
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: ocupación y vacancia proyectada
afecta_a:
  - nivel
  - ocupacion-por-curso-y-nivel
  - cupo
bloqueantes:
  - F1
  - F4
  - D7
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Promoción de niveles para proyectar ocupación

## Enunciado

Para proyectar la ocupación de un ciclo futuro **no alcanza con contar quién está hoy en
cada nivel**: los alumnos promocionan. Sala 3 de este año es Sala 4 del que viene.

El prototipo v11 ya implementa una **foto recursiva** que promociona los 17 niveles de la
escalera y suma las postulaciones nuevas encima.

## Qué le falta a ese modelo

- **A DEFINIR (F4):** la tasa de permanencia. Hoy la promoción asume que todos siguen. Los
  que se van (`Egresado` aparte) no están modelados, y ese supuesto infla la ocupación
  proyectada.
- **A DEFINIR (F1):** qué se cuenta como ocupado.
- **A DEFINIR (D7):** de qué fuente sale la matrícula que se promociona. Hoy sale de Kommo,
  que **no es** el sistema donde vive el alumno. Ver [abm-sedna-hosking-handing](../sources/abm-sedna-hosking-handing.md).

**Esta es la métrica donde la falta de la entidad [alumno](../entities/alumno.md) duele más**: se está
proyectando la ocupación de alumnos con datos de leads.
