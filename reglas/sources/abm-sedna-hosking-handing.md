---
name: abm-sedna-hosking-handing
tipo: source
titulo: ABM académico — Sedna / Hosking / Handing
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema: ABM académico (Sedna, Hosking, Handing)
grano: A DEFINIR (D1)
metodo_extraccion: A DEFINIR (D2)
frecuencia: A DEFINIR (D2)
bloqueantes:
  - D1
  - D2
  - D7
  - A1
  - J1
reglas:
  - regla-landing-zone-raw
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# ABM académico — Sedna / Hosking / Handing

**Es el bloqueante mayor del proyecto.** Acá es donde una persona deja de ser postulante y
**se convierte en alumno**.

## Por qué importa tanto

**Confirmado** (surge del mapa de status que escribió el equipo en
[sheet-requerimientos-ingresos](sheet-requerimientos-ingresos.md)): el embudo **no termina en Kommo**. El tramo final es

`INTERCAMBIO OK` → **`GRABADO ABM`** (alta en Sedna/Hosking/Handing) → `INSCRIPTO`
(contrato + DI) → `DOCUMENTACIÓN` → `LEGAJO`

Kommo registra que el caso pasó por ahí. **El alta real ocurre en el ABM.** Todo
requerimiento que el equipo pidió y hoy no cierra —hermanos, familia de la comunidad, pases
de sede, recupero de solicitudes de años anteriores, etiqueta de permanencia— depende de
esta fuente, porque son atributos del [alumno](../entities/alumno.md), no del [lead](../entities/lead.md).

## Lo que no sabemos

| Pregunta | Estado |
|---|---|
| ¿Sedna, Hosking y Handing son tres sistemas, tres módulos o tres instancias del mismo? | **A DEFINIR (D1)** |
| ¿Cuál es el maestro de alumnos de la red? | **A DEFINIR (D1)** |
| ¿Se puede extraer automáticamente o solo a mano? | **A DEFINIR (D2)** |
| ¿Es la fuente de verdad de la matrícula, o lo es otra? | **A DEFINIR (D7)** |
| ¿Qué identificador de persona usa, y se puede cruzar con Kommo? | **A DEFINIR (B2, B6)** |
| ¿Quién autoriza el acceso? | **A DEFINIR (J1, J3)** |

Hasta que D1 y D7 se respondan, **la entidad [alumno](../entities/alumno.md) no se puede modelar** y la Capa 2 no
se puede certificar.

## Decisiones abiertas

- **A DEFINIR (D1)** — qué es cada sistema y cuál es el maestro de alumnos.
- **A DEFINIR (D2)** — extracción automática.
- **A DEFINIR (D7)** — fuente de verdad de la matrícula.
