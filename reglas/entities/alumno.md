---
name: alumno
tipo: entity
titulo: Alumno
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - alumno
grano: A DEFINIR (A1)
clave_natural: A DEFINIR (B2)
fuentes:
  - abm-sedna-hosking-handing
reglas:
  - regla-grano
bloqueantes:
  - A1
  - A2
  - B2
  - B6
  - D1
  - D7
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Alumno

**Esta es la entidad que el modelo no tiene, y por eso existe el replanteo v3.**

El [lead](lead.md) es un artefacto del CRM: nace cuando alguien deja un dato y muere cuando el caso
se cierra. El **alumno** es el cliente real del colegio: existe antes del lead (si tiene un
hermano en la red), sobrevive al lead, cambia de nivel todos los años y puede volver a
aparecer como postulante en otra sede.

Todo lo que el equipo pidió y hoy no se puede calcular es, en el fondo, esta ausencia:

| Requerimiento del equipo | Por qué no cierra hoy |
|---|---|
| Hermanos / familia de la comunidad | Requiere [familia](familia.md), que requiere [persona](persona.md) estable |
| Lista de espera calificada por hermano sin cupo | Ídem — y el CRM ya tiene el estado [esperando-vacante-hno](../statuses/esperando-vacante-hno.md) |
| Pases de sede | Es la misma persona en dos sedes; sin persona son dos casos |
| Recupero de solicitudes de años anteriores | Requiere unir postulaciones de distintos ciclos |
| Etiqueta de permanencia ("alumnos de K1") | Requiere saber quién ya es alumno |

## Grano

**A DEFINIR (A1).** Una persona, o una persona por ciclo lectivo. No es lo mismo: la
segunda opción permite decir "alumno de 3.º en 2027" sin ambigüedad, la primera es más
simple pero necesita una tabla de trayectoria.

## Identidad

**A DEFINIR (B2).** Qué identifica a un alumno: DNI, un id del ABM, una combinación de
nombre + fecha de nacimiento. La respuesta determina si Kommo y el ABM se pueden cruzar.

**A DEFINIR (B6).** Qué hacer cuando la misma persona aparece dos veces. Ver
[regla-duplicados](../rules/regla-duplicados.md).

## Dónde nace

**Confirmado:** en [grabado-abm](../statuses/grabado-abm.md), cuando se da el alta en
[abm-sedna-hosking-handing](../sources/abm-sedna-hosking-handing.md). Ese es el corte entre [postulacion](postulacion.md) y alumno.

**A DEFINIR (A1):** si se es alumno desde el alta en el ABM, desde [inscripto](../statuses/inscripto.md) o desde
[legajo](../statuses/legajo.md).

## Relaciones

- Pertenece a una [familia](familia.md)
- Tiene una o varias [postulacion](postulacion.md)
- Ocupa un lugar en [curso-seccion-turno](curso-seccion-turno.md) de una [colegio-sede](colegio-sede.md) en un [ciclo-lectivo](ciclo-lectivo.md)

## Datos sensibles

Es una persona menor de edad. Ver [datos-sensibles-menores](../governance/datos-sensibles-menores.md) antes de decidir qué campos
se ingestan.

## Decisiones abiertas

- **A DEFINIR (A1)** — qué es un alumno y desde cuándo lo es. *Pregunta madre del proyecto.*
- **A DEFINIR (B2, B6)** — identidad y unicidad.
- **A DEFINIR (D1, D7)** — cuál es el maestro y cuál la fuente de verdad de la matrícula.
