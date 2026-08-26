---
name: desisten
tipo: metric
titulo: Desisten
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - desisten
numerador: casos que desisten
denominador: A DEFINIR
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados:
  - desiste
  - desisten-en-contacto-inicial
entidades: []
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-duplicados
golden_questions: []
bloqueantes:
  - E6
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Desisten

Cuántas familias se bajan del proceso.

**Cuidado con el denominador y con el momento.** [desisten-en-contacto-inicial](../statuses/desisten-en-contacto-inicial.md) y
[desiste](../statuses/desiste.md) son etapas distintas del embudo. Sumarlos en un solo número esconde justamente
lo que interesa: **dónde** se caen.

**A DEFINIR (E6):** si se registra el motivo.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | casos que desisten |
| Denominador | A DEFINIR |
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
