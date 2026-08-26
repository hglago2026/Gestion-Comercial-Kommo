---
name: proceso-archivo-mensual
tipo: process
titulo: Archivo mensual del status
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema_soporte: A DEFINIR (I1)
entidades:
  - evento-de-lead
  - cupo
estados: []
metricas: []
bloqueantes:
  - H1
  - I1
  - D4
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Archivo mensual del status

**Confirmado (requerimiento del equipo):** archivar el status al cierre de cada mes para
armar curvas históricas y comparar contra el hito del 31 de marzo.

## Dos formas de cumplirlo, y una es mejor

| Forma | Cómo | Problema |
|---|---|---|
| **Snapshot archivado** | guardar una foto del estado a fin de mes | si la definición cambia, la foto vieja queda con la definición vieja y no se puede recalcular |
| **Reconstrucción desde eventos** | guardar todos los [evento-de-lead](../entities/evento-de-lead.md) y reconstruir cualquier fecha | ninguno, si la historia está completa |

**Sugerencia (no es decisión tomada):** reconstruir desde eventos y usar los snapshots solo
como control cruzado. Ver [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md).

**La excepción es el [cupo](../entities/cupo.md):** no genera eventos. Si no se versiona a mano, la ocupación
pasada no se puede reconstruir aunque los eventos estén completos. **A DEFINIR (D4).**
