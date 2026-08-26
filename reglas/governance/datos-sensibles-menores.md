---
name: datos-sensibles-menores
tipo: governance
titulo: Datos sensibles y menores de edad
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: toda la ingesta y todo el wiki
bloqueantes:
  - J1
  - J2
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Datos sensibles y menores de edad

**El sujeto de este modelo es, casi siempre, un menor de edad.** Eso cambia lo que se puede
guardar, dónde y por cuánto tiempo.

## Reglas duras de este repositorio

1. **En el wiki no va ningún dato de una persona real.** Ni de ejemplo. Si hace falta un
   ejemplo, se inventa uno obviamente ficticio.
2. **Ningún archivo de datos entra al repo.** Ver [regla-landing-zone-raw](../rules/regla-landing-zone-raw.md).
3. Lo que sale de la [app-doe](../sources/app-doe.md) merece cuidado especial: son observaciones sobre chicos.
   **Sugerencia (no es decisión tomada):** ingestar **solo el resultado** (apto / requiere
   taller / fecha), nunca el contenido de la encuesta.

## Lo que hay que resolver antes de ingestar el ABM o el DOE

- **A DEFINIR (J2):** qué campos se pueden traer y cuáles quedan fuera por definición.
- **A DEFINIR (J1):** quién puede verlos una vez adentro.
- Dónde vive físicamente la landing zone. Hoy es una carpeta de Google Drive personal, y eso
  **conviene revisarlo antes de sumar fuentes con datos de menores**, no después.

Esto no es una formalidad que se completa al final: condiciona el diseño de la Capa 1.
