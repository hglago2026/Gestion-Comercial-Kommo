---
name: postulantes-actividad-intercambio
tipo: metric
titulo: Postulantes con y sin actividad de intercambio
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - postulantes con y sin actividad de intercambio
numerador: postulantes por rama
denominador: total de postulantes que avanzan
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados:
  - avanzan
  - intercambio-ok
  - taller-intercambio
entidades:
  - nivel
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

# Postulantes con y sin actividad de intercambio

**Confirmado:** la bifurcación por nivel — **K1–K2** van directo a [intercambio-ok](../statuses/intercambio-ok.md);
**K3 en adelante** pasan por [taller-intercambio](../statuses/taller-intercambio.md).

Separar las dos ramas es necesario porque tienen tiempos distintos: comparar el tiempo total
de embudo de un K1 contra el de un K4 sin separarlos produce una diferencia que parece
gestión y es diseño del proceso.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | postulantes por rama |
| Denominador | total de postulantes que avanzan |
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
