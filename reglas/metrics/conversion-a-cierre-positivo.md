---
name: conversion-a-cierre-positivo
tipo: metric
titulo: Conversión a cierre positivo
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - conversión a cierre positivo
numerador: casos que alcanzaron un estado positivo
denominador: total de casos del pipeline
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados:
  - grabado-abm
entidades:
  - lead
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

# Conversión a cierre positivo

**No viene del Sheet: viene del prototipo v11**, con una **definición de trabajo que el
equipo todavía no ratificó**. Ver [regla-cierre-positivo](../rules/regla-cierre-positivo.md).

**Medido con esa definición provisoria (export 2026-08-04):** CDF Puertos 27,3% · NFS 24,2%
· CDF Benavidez 17,4% · LTH Hudson 12,9% · Red Itínere 0,2%.

El 0,2% de Red Itínere **no es un mal desempeño**: es un embudo de marketing con otro
vocabulario que no debería mezclarse con los de admisión. Ver
[regla-pipelines-en-alcance](../rules/regla-pipelines-en-alcance.md). Es el mejor ejemplo de un número correcto que, sin la página
que lo explica, se lee como un desastre.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | casos que alcanzaron un estado positivo |
| Denominador | total de casos del pipeline |
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
