---
name: grabado-abm
tipo: status
titulo: Grabado en ABM
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
proceso: proceso-admision
responsable: A DEFINIR (E2) — transcribir del Sheet
origen_del_nombre: ambos
entra_desde:
  - intercambio-ok
  - pago-reserva
sale_hacia:
  - inscripto
bloqueantes:
  - E1
  - D7
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Grabado en ABM

**El punto de quiebre del proyecto.** Acá se da el alta en el sistema académico
([abm-sedna-hosking-handing](../sources/abm-sedna-hosking-handing.md)) y la persona empieza a ser [alumno](../entities/alumno.md) y deja de ser
[postulacion](../entities/postulacion.md).

**Confirmado (medido):** en el dato de Kommo este estado tiene una mediana de permanencia de
**115 a 188 días** — funciona como sala de espera hasta la matrícula. Cualquier métrica de
"tiempo hasta el cierre" que lo incluya sin aclararlo va a dar números enormes y correctos
pero inútiles.

**A DEFINIR (D7):** si el `GRABADO ABM` de Kommo y el alta real en el ABM siempre coinciden.
Si no coinciden, hay dos verdades y hay que elegir una.

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
