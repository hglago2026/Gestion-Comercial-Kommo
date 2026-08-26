---
name: excedencia-de-vacancia
tipo: metric
titulo: Excedencia de vacancia
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - excedencia de vacancia
numerador: A DEFINIR (F3)
denominador: A DEFINIR (F3)
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados: []
entidades:
  - cupo
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-duplicados
golden_questions: []
bloqueantes:
  - F3
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Excedencia de vacancia

**A DEFINIR (F3):** el nombre admite dos lecturas opuestas — cuántos lugares **sobran**,
o cuántos casos hay **por encima** del cupo. El equipo sabe cuál quiso decir; el wiki no lo
adivina.

Es un ejemplo de manual de por qué esta capa existe: una métrica pedida, con nombre propio,
que nadie escribió y que puede significar dos cosas contrarias.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | A DEFINIR (F3) |
| Denominador | A DEFINIR (F3) |
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
