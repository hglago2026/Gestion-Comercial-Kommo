---
name: persona
tipo: entity
titulo: Persona
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - persona
grano: una persona física
clave_natural: A DEFINIR (B2)
fuentes:
  - kommo-export-eventos
  - abm-sedna-hosking-handing
reglas:
  - regla-duplicados
bloqueantes:
  - B1
  - B2
  - B6
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Persona

La entidad que permite decir "esta es la misma de antes". Sin ella no hay hermanos, no hay
pases de sede y no hay recupero de solicitudes anteriores.

**A DEFINIR (B1):** si el modelo necesita distinguir *persona candidata* (el chico o la
chica) de *persona adulta responsable* (quien gestiona), o si alcanza con una sola entidad
persona con un rol.

Es una distinción que parece técnica y no lo es: hoy el lead de Kommo trae el nombre de la
familia en `Entity Name`, no el del postulante. **A DEFINIR (B3):** si el lead trae datos
del chico/a o solo del adulto que consulta.

## Identidad

**A DEFINIR (B2).** Ver [regla-duplicados](../rules/regla-duplicados.md).

## Decisiones abiertas

- **A DEFINIR (B1)** — ¿una entidad persona con roles, o dos entidades?
- **A DEFINIR (B2, B6)** — clave de identidad y deduplicación.
