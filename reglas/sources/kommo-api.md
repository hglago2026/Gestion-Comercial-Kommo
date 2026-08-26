---
name: kommo-api
tipo: source
titulo: Kommo — API
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema: Kommo (CRM)
grano: A DEFINIR
metodo_extraccion: A DEFINIR (D6)
frecuencia: A DEFINIR (D6)
bloqueantes:
  - D6
  - J1
  - I2
reglas:
  - regla-landing-zone-raw
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Kommo — API

Es el reemplazo natural del [kommo-export-eventos](kommo-export-eventos.md) manual: lo que convierte la **foto** en
**película**.

## Estado

**A DEFINIR (D6).** No está confirmado que el proyecto vaya a usar la API, ni con qué
credenciales, ni quién la opera.

## Qué habría que definir antes de escribir esta página en serio

| Pregunta | Por qué bloquea |
|---|---|
| ¿Se habilita acceso de API y con qué usuario? (**J1**) | Sin credenciales no hay ingesta automática |
| ¿Frecuencia: diaria, horaria, continua? (**D6**) | Define si se puede archivar el status al cierre de cada mes |
| ¿Qué profundidad de historial devuelve? (**D6**) | Si no devuelve el pasado, el export manual sigue siendo la única historia |
| ¿Quién monitorea que la ingesta corrió? (**I2**) | Una ingesta que falla en silencio es peor que no tenerla |

**Sugerencia (no es decisión tomada):** aunque se automatice, conservar el export manual del
2026-08-04 como *snapshot fundacional* en la landing zone, para poder comparar contra él si
la API devuelve un pasado distinto.

## Decisiones abiertas

- **A DEFINIR (D6)** — método y frecuencia de extracción.
- **A DEFINIR (J1)** — permisos y credenciales.
