---
name: lead
tipo: entity
titulo: Lead (Kommo)
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - lead
grano: un caso en el CRM
clave_natural: Object ID de Kommo
fuentes:
  - kommo-export-eventos
reglas:
  - regla-grano
  - regla-pipelines-en-alcance
bloqueantes:
  - A1
  - B6
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Lead (Kommo)

**Confirmado:** un caso del CRM, identificado por `Object ID`. Es lo que el proyecto tiene
hoy y sobre lo que se construyó el prototipo v11. ~43.893 leads en el export del 2026-08-04,
de los cuales 14.828 tuvieron al menos un cambio de etapa.

**Es un artefacto de la herramienta, no un concepto del negocio.** Esta página existe para
que quede escrito: el lead se documenta porque es la fuente, no porque sea el centro del
modelo. El centro es [alumno](alumno.md).

## Atributos observables

| Atributo | Fuente | Notas |
|---|---|---|
| id | `Object ID` | |
| nombre de la familia | `Entity Name` | dato personal |
| pipeline (colegio/sede) | `Value After.pipeline` del evento tid=14 | ver [colegio-sede](colegio-sede.md) |
| estado | `Value After.name` del evento tid=14 | ver [regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) |
| fecha de creación | evento `Type ID = 1` | |

## Límite

El lead **no llega a la matrícula**: el embudo sigue en
[abm-sedna-hosking-handing](../sources/abm-sedna-hosking-handing.md). Un modelo que termina en el lead no puede responder cuántos
alumnos tiene la red.
