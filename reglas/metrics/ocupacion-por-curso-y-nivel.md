---
name: ocupacion-por-curso-y-nivel
tipo: metric
titulo: % de ocupación por curso y nivel
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - % de ocupación por curso y nivel
numerador: lugares ocupados
denominador: cupo
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
  - curso-seccion-turno
  - nivel
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-duplicados
golden_questions: []
bloqueantes:
  - D7
  - F1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# % de ocupación por curso y nivel

El porcentaje de llenado por sede × nivel × curso × turno.

**A DEFINIR (F1):** qué se cuenta como ocupado — matriculados, matriculados + reservas, o
capacidad física.
**A DEFINIR (D7):** contra qué fuente se mide la matrícula.

Para proyectar a futuro hace falta [regla-promocion-de-niveles](../rules/regla-promocion-de-niveles.md): sin promoción de niveles,
la ocupación proyectada está sistemáticamente mal.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | lugares ocupados |
| Denominador | cupo |
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
