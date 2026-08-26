---
name: pases-de-sede
tipo: metric
titulo: Pases de sede
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - pases de sede
numerador: pases concretados
denominador: solicitudes de pase
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados:
  - paso-de-sede
entidades: []
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-duplicados
golden_questions: []
bloqueantes:
  - B6
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Pases de sede

**Confirmado:** el equipo pidió tres cosas — solicitudes, concretados y **tiempo** entre
una y otro.

**Hoy no se puede calcular.** Un pase es la misma persona cambiando de sede, y sin
[persona](../entities/persona.md) estable en el dato aparece como dos casos separados o como un
[duplicados](../statuses/duplicados.md). Ver [proceso-pase-de-sede](../processes/proceso-pase-de-sede.md) y **A DEFINIR (B6)**.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | pases concretados |
| Denominador | solicitudes de pase |
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
