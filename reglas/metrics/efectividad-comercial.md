---
name: efectividad-comercial
tipo: metric
titulo: Efectividad Comercial
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - efectividad comercial
numerador: Reservas + Lista de Espera
denominador: Asisten a Reunión
dimensiones: sede, ciclo, nivel, canal — A DEFINIR (G2) cuáles aplican
regla_temporal: A DEFINIR (G3)
exclusiones: A DEFINIR (B6) — duplicados, pruebas, bajas
implementacion: A DEFINIR — vista SQL / medida en la Capa 2
fuentes:
  - sheet-requerimientos-ingresos
  - kommo-export-eventos
estados:
  - reunion-presentacion
  - lista-de-espera
  - reserva-pre-icbio
entidades: []
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-duplicados
golden_questions: []
bloqueantes:
  - E1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Efectividad Comercial

**La métrica más mirada del embudo.** De las familias que llegaron a la reunión,
cuántas terminaron reservando o quedando en lista de espera.

**Confirmado:** el equipo decidió **incluir la lista de espera en el numerador**. Es una
decisión de negocio, no un detalle técnico: dice que una familia que quiere entrar pero no
tiene cupo es un éxito comercial, no una pérdida. Quien lea el número sin saber esto va a
compararlo mal contra cualquier benchmark externo.

**Lo que falta no es menor.** Sin **regla temporal**, dos personas que apliquen la misma
fórmula en fechas distintas obtienen números distintos. Sin **exclusiones** definidas, los
[duplicados](../statuses/duplicados.md) del CRM inflan el denominador. Sin **owner**, no hay quién firme.

**A DEFINIR (E1):** qué cuenta como *reserva* — ¿[reserva-pre-icbio](../statuses/reserva-pre-icbio.md)? ¿[pago-reserva](../statuses/pago-reserva.md)?
Son dos números distintos.

## Ficha

| Campo | Valor |
|---|---|
| Numerador | Reservas + Lista de Espera |
| Denominador | Asisten a Reunión |
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
