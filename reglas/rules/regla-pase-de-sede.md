---
name: regla-pase-de-sede
tipo: rule
titulo: Pase de sede: cómo entra y cuándo se detecta
estado: en_revision
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - G6
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Pase de sede

## Cómo entra — **Confirmado (G6)**

> *"Un pase de sede se inicia operativamente igual que cualquier proceso de ingreso: la familia, por iniciativa propia o por sugerencia del equipo directivo, completa una postulación en la web de la sede de destino o a través de una campaña."*

No hay canal, formulario ni circuito diferenciado. Entra como un lead más.

## El punto ciego — **Confirmado (G6)**

> *"Si ingresa mediante form corto, inicialmente no es posible identificar que se trata de un alumno actual de otra sede de la red."*

Con form corto el lead es **indistinguible** de un ingreso externo.

## El punto de detección — **Confirmado (G6)**

> *"Uno de los datos clave del formulario completo es el colegio actual del alumno. Cuando se detecta que ese colegio pertenece a la propia red, el caso deja de considerarse un ingreso externo común y se clasifica como un pase o traspaso entre sedes."*

Secuencia: `lead de ingreso → enriquecimiento → identificación del colegio actual → si pertenece a la red, se reclasifica como pase`.

> *"La identificación del pase, por lo tanto, no necesariamente ocurre al crear el lead, sino cuando se dispone de información suficiente."*

## Qué implica para el modelo

1. **La clasificación es derivada y tiene fecha.** El lead nace como ingreso y se reclasifica después. El modelo tiene que poder reconstruir qué era en cada momento.
2. **La detectabilidad tiene techo.** Todo lead que nunca se enriquece se cuenta como ingreso nuevo aunque sea un pase. Es un sesgo estructural, **no cuantificado**.
3. **En la sede origen genera una baja probable** — *Confirmado (A5)*: *"debe tratarse inicialmente como una baja incierta/probable de su sede actual, ya que todavía puede afectar tanto la ocupación del ciclo vigente como la proyección del siguiente."*
4. **Sede y red miden distinto.** Para la sede destino es un alta; para la red no es matrícula nueva.
5. **`PASO DE SEDE` está excluido del denominador de prospectos** — *Confirmado (Diccionario Status, columna `regala`)*.

## Conflicto abierto — CF-08

El Diccionario Status describe el mismo estado de otra manera: *"puede darse en cualquier momento del proceso y es una recomendacion de la Sec. Ingresos de seguir el proceso en otra sede o modelo"*. Ahí lo empuja Sec. Ingresos; en G6 lo inicia la familia.

Podrían ser **dos fenómenos distintos con el mismo nombre**: una derivación interna y un pase. Decisión pendiente.

## Qué falta para medirlo bien

- ¿`Colegio actual` es lista cerrada con las sedes de la red o texto libre? Determina si la detección es automática o requiere normalización.
- ¿Qué porcentaje de leads nunca se enriquece? Es el techo de detectabilidad.
- ¿La baja en la sede origen se puede vincular al alta en destino? Sin eso no hay traslado neto medible.
- ¿El pase consume cupo de la sede destino igual que un ingreso nuevo?
