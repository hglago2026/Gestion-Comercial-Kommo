---
name: tiempos-entre-status
tipo: metric
titulo: Tiempos entre status
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - tiempos entre status
numerador: A DEFINIR
denominador: no aplica — duración
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados:
  - taller-intercambio
  - reunion-presentacion
entidades: []
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-duplicados
golden_questions: []
bloqueantes:
  - E7
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Tiempos entre status

Cuánto tarda un caso en pasar de un estado a otro.

**Confirmado — el más específico que pidió el equipo:**
`Devolución Act. Ibio − Fecha Taller` debe ser **≤ 7 días**.

**A DEFINIR (E7):** de qué campos salen esas dos fechas. Si no están registradas como fecha,
el indicador no existe.

Se apoya en el mismo mecanismo que [time-to-lead](time-to-lead.md).

## Ficha

| Campo | Valor |
|---|---|
| Numerador | A DEFINIR |
| Denominador | no aplica — duración |
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
