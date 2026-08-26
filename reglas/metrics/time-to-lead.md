---
name: time-to-lead
tipo: metric
titulo: Time to Lead / permanencia por estado
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - time to lead / permanencia por estado
numerador: días entre eventos consecutivos
denominador: no aplica — mediana y percentiles
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados:
  - postulante
entidades:
  - evento-de-lead
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-duplicados
golden_questions: []
bloqueantes:
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Time to Lead / permanencia por estado

Cuánto tiempo pasa un caso en cada estado. **No viene del Sheet: viene del prototipo
v11**, y por eso está en `borrador` y no en `en_revision`.

**Confirmado (medido sobre el export del 2026-08-04, mediana de días en
[postulante](../statuses/postulante.md)):** NFS 46 · CDF Benavidez 24,8 · CDF Puertos 15,2 · LTH Hudson 17,5.
[grabado-abm](../statuses/grabado-abm.md) da 115–188 días, pero es una sala de espera administrativa, no una demora.

**Cómo se calcula:** ver [evento-de-lead](../entities/evento-de-lead.md). El último estado queda censurado (sin dwell) y
se excluye; se filtran dwell negativos y mayores a 2000 días.

**Sugerencia (no es decisión tomada):** reportar **mediana**, no promedio. La distribución
tiene cola larga y el promedio la exagera.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | días entre eventos consecutivos |
| Denominador | no aplica — mediana y percentiles |
| Dimensiones compatibles | **A DEFINIR (G2)** |
| Regla temporal | **A DEFINIR (G3)** |
| Exclusiones | **A DEFINIR (B6)** |
| Implementación (Capa 2) | **A DEFINIR** |

## Historial de definición

| Versión | Fecha | Qué cambió | Quién |
|---|---|---|---|
| 0.1 | 2026-08-20 | Se transcribe la definición del equipo al wiki | Horacio + Claude |

---

*Origen de la fórmula: [sheet-requerimientos-ingresos](../sources/sheet-requerimientos-ingresos.md) — la escribió el equipo, no el proyecto. Lo que falta no es la fórmula: es la **regla temporal**, las **exclusiones**, el **owner** y el **aprobador**. Sin eso no se certifica (**A DEFINIR G1**).*
