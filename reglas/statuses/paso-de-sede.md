---
name: paso-de-sede
tipo: status
titulo: Paso de sede
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
proceso: proceso-admision
responsable: A DEFINIR (E2) — transcribir del Sheet
origen_del_nombre: kommo
entra_desde: []
sale_hacia: []
bloqueantes: []
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Paso de sede

Estado literal de Kommo. **Confirmado:** el equipo pidió medir pases de sede
—solicitudes, concretados y tiempo— en [sheet-requerimientos-ingresos](../sources/sheet-requerimientos-ingresos.md). Ver
[pases-de-sede](../metrics/pases-de-sede.md) y [proceso-pase-de-sede](../processes/proceso-pase-de-sede.md).

**El problema de fondo:** un pase de sede es la **misma persona** cambiando de sede. Sin
entidad [persona](../entities/persona.md) estable, en el dato se ve como dos casos distintos, o como un
[duplicados](duplicados.md). Es otro requerimiento que hoy no cierra por falta de la entidad
[alumno](../entities/alumno.md).

## Reglas aplicables

[regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md) · [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md) · [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md)
