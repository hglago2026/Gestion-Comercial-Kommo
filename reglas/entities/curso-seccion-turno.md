---
name: curso-seccion-turno
tipo: entity
titulo: Curso, sección y turno
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - curso
  - seccion
  - turno
grano: una sección de un nivel en una sede y un ciclo
clave_natural: A DEFINIR
fuentes:
  - cupos-y-secciones
bloqueantes:
  - F1
  - F2
  - D4
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Curso, sección y turno

**Confirmado:** el equipo pidió cortar por sede, nivel, **curso y turno** (el turno es
específicamente relevante en CDF).

Es el grano en el que realmente se llena o no se llena un colegio: la ocupación de un nivel
puede estar bien y la de una sección puntual estar desbordada.

**A DEFINIR (F2):** si una sección se puede abrir durante el ciclo y cómo se registra ese
cambio. De eso depende que la ocupación histórica sea reconstruible.

Ver [cupo](cupo.md) y [cupos-y-secciones](../sources/cupos-y-secciones.md).
