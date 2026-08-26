---
name: regla-duplicados
tipo: rule
titulo: Qué es un duplicado y qué no
estado: borrador
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - B6
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Regla de duplicado

## La regla — **A definir** (B6)

> *"La definición de duplicado es cuando lead es identificado como el mismo ingresante, para un mismo ciclo y nivel. Si ese Lead es identificado como una misma persona, pero que la postulación es para años o niveles diferentes al original, eso no es considerado como duplicado. Si no que son oportunidades diferentes y hay que conservar ambos leads (aunque el potencial alumno sea el mismo)"*

En criollo: **duplicado = misma persona + mismo ciclo + mismo nivel.** Cambiá cualquiera de los tres y ya no es duplicado: son dos postulaciones distintas de la misma persona, y las dos se conservan.

**Estado: A definir.** La celda RESPUESTA de B6 dice *"A confirmar con NE y NV"*. Hasta que eso pase, la regla no se certifica.

## Por qué importa tanto

Esta regla decide la forma del modelo. Si un duplicado fuera "la misma persona apareciendo dos veces", lo correcto sería colapsar. Como no lo es, hace falta:

- una entidad **persona** separada de la postulación,
- una relación **1 a N**,
- y una regla de resolución de identidad para saber cuándo dos leads son la misma persona.

Esa última regla **no existe todavía**, y el identificador disponible no ayuda: *"el ID que se usa en Kommo es el ID de Kommo, no el DNI"* (B4).

## Lo que ya pasó con los duplicados

El log registra fusiones manuales: *"Es cuando un LEAD se identifica como duplicado y el VENDEDOR lo fusiona en un único LEAD"* (Event Action · La fusión realizada). O sea que parte de la deduplicación ya ocurrió a mano, sin criterio documentado.

## Advertencia del mapa de proceso

> *"Deberían restarse de la base o eliminarse en Kommo. Ojo! diferenciar si postularon más de una vez en años anteriores u otra sede"*

El propio mapa advierte contra el error de tratar como duplicado a quien volvió a postular. Coherente con B6.

## Consecuencia para el consumo

Toda métrica que cuente **personas únicas** sale rotulada como **interpretación**, no como dato certificado, hasta que B6 se confirme.
