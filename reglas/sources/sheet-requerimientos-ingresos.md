---
name: sheet-requerimientos-ingresos
tipo: source
titulo: Sheet — Requerimientos Tablero Ingresos (fuente de definiciones)
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema: Google Sheets
grano: no aplica — documento de definiciones
metodo_extraccion: lectura
frecuencia: no aplica
bloqueantes:
  - G1
define:
  - mapa de status
  - indicadores de ingresos
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Sheet — Requerimientos Tablero Ingresos

**No es una fuente de dato: es una fuente de definiciones**, y es la más importante que
tiene el proyecto, porque **la escribió el propio equipo**.

*(El enlace al documento no se publica: es interno, con acceso nominal.)*

## Qué contiene

**Bloque 1 — Objetivo y alcance.** Evidenciar actividad comercial con hito de cierre al
**31 de marzo** de cada año; de abril en adelante mostrar ciclo corriente + siguiente.
Performance por rol responsable (Sec. Ingresos, Equipos Directivos, DOE). Corte por origen
(campaña vs orgánico, con etiquetas de referidos y familia de la comunidad/hermanos). Corte
por sede, nivel, curso y turno. **Archivar el status al cierre de cada mes** para curvas
históricas.

**Bloque 2 — Indicadores.** Los que están sembrados en `/metrics`.

**Bloque 3 — Mapa de status con gestor responsable.** El que está sembrado en `/statuses`.

## Cómo usarlo

Cada página de `/metrics` y `/statuses` cita este Sheet como origen. **Regla del proyecto:
lo que está acá no se reescribe ni se "mejora" desde el wiki.** Si algo del Sheet parece
inconsistente, se anota como pregunta al equipo, no se corrige por cuenta propia.

## Lo que le falta

**A DEFINIR (G1):** el Sheet declara las fórmulas pero **no las ratifica como oficiales**,
no les asigna `owner` ni `aprobador`, y no fija reglas temporales ni exclusiones. Eso es,
literalmente, el trabajo de la Fase 5.

## Decisiones abiertas

- **A DEFINIR (G1)** — ratificar los indicadores como oficiales y asignarles dueño.
