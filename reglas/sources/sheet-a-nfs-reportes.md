---
name: sheet-a-nfs-reportes
tipo: source
titulo: Google Sheet "A - NFSs reportes"
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema: Google Sheets
grano: A DEFINIR
metodo_extraccion: lectura manual / descarga
frecuencia: A DEFINIR (D5)
bloqueantes:
  - D5
reglas:
  - regla-landing-zone-raw
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Google Sheet "A - NFSs reportes"

**Confirmado:** es una de las dos fuentes que consumió el prototipo de auditoría v11, junto
con [kommo-export-eventos](kommo-export-eventos.md). Está en `la carpeta privada del proyecto` como archivo `.gsheet`.

## Estado de la documentación

**A DEFINIR (D5):** hace falta relevar hoja por hoja qué contiene, quién la mantiene y con
qué frecuencia se actualiza, antes de que la Capa 1 dependa de ella.

**Sugerencia (no es decisión tomada):** una planilla mantenida a mano es una fuente
legítima mientras esté documentada y tenga dueño; deja de serlo cuando nadie sabe quién la
toca. Esta página debería cerrarse antes de que el DWH la lea.

## Decisiones abiertas

- **A DEFINIR (D5)** — contenido, dueño y frecuencia.
