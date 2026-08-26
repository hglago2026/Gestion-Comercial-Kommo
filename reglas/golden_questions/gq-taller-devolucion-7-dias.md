---
name: gq-taller-devolucion-7-dias
tipo: golden_question
titulo: ¿Qué proporción de las devoluciones del taller salió dentro de los 7 días?
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
pregunta: "¿Qué proporción de las devoluciones del taller salió dentro de los 7 días?"
metricas:
  - tiempos-entre-status
entidades:
  - nivel
reglas:
  - regla-fecha-de-corte
respuesta_esperada: A DEFINIR
tolerancia: A DEFINIR
bloqueantes:
  - K1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# ¿Qué proporción de las devoluciones del taller salió dentro de los 7 días?

> "¿Qué proporción de las devoluciones del taller salió dentro de los 7 días?"

Prueba si el modelo puede medir el compromiso operativo más concreto que escribió el
equipo: `Devolución Act. Ibio − Fecha Taller ≤ 7 días`.

## Ambigüedades

1. **¿De qué campos salen las dos fechas?** **A DEFINIR (E7)**. Si no están registradas como
   fecha, la respuesta correcta es *"no se puede calcular con el dato disponible"* — y saber
   eso vale tanto como el número.
2. **¿Días corridos o hábiles?**
3. **¿Se cuentan los casos todavía sin devolución** (censurados) o se excluyen? Excluirlos
   sesga el resultado hacia arriba.

## Qué debería hacer la IA

Según el [el contrato](../../CONTRATO.md): resolver lo que tenga default declarado, **repreguntar** lo
que no, y etiquetar la respuesta como **dato certificado**, **interpretación** o
**hipótesis**. Nunca mezclarlos sin distinguir.

## Respuesta esperada

**A DEFINIR (G1)** — se completa cuando las métricas estén certificadas. El valor va con la
versión de la definición usada.
