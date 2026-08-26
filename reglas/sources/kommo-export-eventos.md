---
name: kommo-export-eventos
tipo: source
titulo: Kommo — export del log de eventos
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema: Kommo (CRM)
grano: un evento (cambio de estado o de campo) por fila
metodo_extraccion: export manual desde la interfaz de Kommo
frecuencia: puntual — A DEFINIR (D6)
archivo_actual: kommo__eventos__20260804.xlsx
bloqueantes:
  - D6
  - D2
  - I1
define:
  - evento kommo
reglas:
  - regla-landing-zone-raw
  - regla-canonicalizacion-estados
  - regla-pipelines-en-alcance
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Kommo — export del log de eventos

Es **la única fuente de dato histórico que el proyecto tiene hoy en la mano**. Todo lo que
el prototipo de auditoría v11 muestra sale de acá.

**Confirmado.** Relevado el 2026-08-04: **935.468 filas**, hoja única `Recent Events`,
~74 MB, rango 2016 → 2026.

## Qué contiene

Una fila por **evento** registrado por el CRM: cambios de etapa, creación de leads,
mensajes, mails, cambios de campo, cambios de responsable, etiquetas. No es una tabla de
leads: es la **bitácora** de lo que le fue pasando a cada lead.

- ~**43.893** `Object ID` distintos de leads.
- **14.828** leads con al menos un cambio de etapa.
- **35.744** eventos de cambio de etapa (`Type ID = 14`), que son los que importan para el
  embudo.

## Cómo se extrae

**Confirmado:** hoy, export manual desde la interfaz. Eso es una **foto**, no una película:
alcanza para auditar, no para reconstruir el pasado ni para actualizarse solo.

**A DEFINIR (D6):** si el reemplazo es la [kommo-api](kommo-api.md), con qué frecuencia y con qué
profundidad de historial. **A DEFINIR (D2):** quién opera y monitorea la extracción.

El archivo aterriza en la landing zone según [regla-landing-zone-raw](../rules/regla-landing-zone-raw.md):
`raw/kommo/eventos/2026/kommo__eventos__AAAAMMDD.xlsx`.

## Campos clave

| Campo | Qué es | Notas |
|---|---|---|
| `Event ID` | id del evento | |
| `Date / Time` | fecha y hora | `dd/mm/aaaa HH:MM` en el 99,5%. ~4.800 filas vienen como "Hoy HH:MM" / "Ayer HH:MM" y hay que resolverlas contra la fecha de extracción. **Tienen hora**: el dwell se puede medir al minuto. |
| `Object Entity` | tipo de objeto | `leads` (591k), `contacts` (180k), `talk` (153k), `companies` (9,5k). Para el embudo se usa **solo `leads`**. |
| `Object ID` | **el número de lead** | Acá está el lead, no en `Object Title`. También aparece en `Kommo URL` como `/leads/detail/NNN`. |
| `Object Title` | tipo de entidad en texto | Siempre dice `Lead` / `Contacto` / `Conversación` / `Compañía` / `Tarea`. **No es el nombre del caso.** |
| `Entity Name` | nombre de la familia | Dato personal: ver [datos-sensibles-menores](../governance/datos-sensibles-menores.md). |
| `Type ID` | tipo de evento | `14` = cambio de etapa (**el clave**) · `1` = nuevo lead · `7` = lead eliminado · `24` = cambio del campo Fecha 1ra Comunicación (433k) · `89/90` mensajes · `152/16` mails · `63/64` etiquetas · `25` responsable. |
| `Value Before` / `Value After` | JSON | Para `Type ID = 14`: `{"color","name","status_id","pipeline"}`, donde `name` es el estado y `pipeline` es el colegio/unidad. Para otros eventos el JSON tiene otra forma (`text`, `plug`) y **no representa estados**. |

## Trampas conocidas

1. **El lead está en `Object ID`, no en `Object Title`.** Es el error más fácil de cometer
   y el que más tiempo costó en el relevamiento.
2. **Los pipelines son colegios**, pero no todos: `Historico`, `NoEsLead`, `Prueba` y
   `Embudo de ventas` son ruido, y `Red Itinere` es un embudo de marketing con vocabulario
   propio y 0,2% de cierre. Ver [regla-pipelines-en-alcance](../rules/regla-pipelines-en-alcance.md).
3. **Dos vocabularios de estado conviven** (`ESPERANDO FLIA` / `ESPERANDO FAMILIA`). Ver
   [regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md).
4. **El último estado de cada lead queda abierto** (censurado): no tiene dwell.

## Calidad conocida

**Confirmado (medido, no estimado):** el 99,5% de las fechas parsea directo; los dwell
negativos y los mayores a 2000 días existen y se filtran.

**A DEFINIR:** si el export trae **todo** el historial o solo los eventos recientes
retenidos por el plan de Kommo. Es determinante para la Capa 1.

## Limitaciones

- No trae la matrícula: el embudo **no termina en Kommo**, sigue en
  [abm-sedna-hosking-handing](abm-sedna-hosking-handing.md). Ver [proceso-admision](../processes/proceso-admision.md).
- No permite responder "¿cómo estaba esto al 31 de marzo?" de forma confiable mientras siga
  siendo un export puntual.
- No tiene entidad [alumno](../entities/alumno.md). Tiene leads.

## Quién depende de esta fuente

- Entidades: [lead](../entities/lead.md) · [postulacion](../entities/postulacion.md) · [persona](../entities/persona.md)
- Métricas: [time-to-lead](../metrics/time-to-lead.md) · [conversion-a-cierre-positivo](../metrics/conversion-a-cierre-positivo.md) y todo el embudo comercial.

## Decisiones abiertas

- **A DEFINIR (D6)** — API vs export, frecuencia y profundidad del historial.
- **A DEFINIR (D2)** — quién opera la extracción.
- **A DEFINIR (I1)** — a qué motor se ingesta.
