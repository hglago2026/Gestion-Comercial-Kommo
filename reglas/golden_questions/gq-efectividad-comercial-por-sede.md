---
name: gq-efectividad-comercial-por-sede
tipo: golden_question
titulo: ¿Cuál es la efectividad comercial de cada sede este ciclo?
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
pregunta: "¿Cuál es la efectividad comercial de cada sede este ciclo?"
metricas:
  - efectividad-comercial
entidades:
  - colegio-sede
reglas:
  - regla-sedes
  - regla-duplicados
  - regla-pipelines-en-alcance
respuesta_esperada: A DEFINIR
tolerancia: A DEFINIR
bloqueantes:
  - K1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# ¿Cuál es la efectividad comercial de cada sede este ciclo?

> "¿Cuál es la efectividad comercial de cada sede este ciclo?"

Prueba tres cosas a la vez: que la métrica esté definida, que las sedes estén bien
separadas y que los pipelines de ruido estén excluidos.

## Ambigüedades

1. **¿Qué cuenta como reserva** en el numerador — [reserva-pre-icbio](../statuses/reserva-pre-icbio.md) o [pago-reserva](../statuses/pago-reserva.md)?
2. **¿Los [duplicados](../statuses/duplicados.md) están excluidos** del denominador? Si no, el número está inflado
   hacia abajo. Ver [regla-duplicados](../rules/regla-duplicados.md).
3. **¿Red Itínere entra?** Si entra, hunde el promedio de la red. Ver
   [regla-pipelines-en-alcance](../rules/regla-pipelines-en-alcance.md).
4. **NFS Puertos y NFS Nordelta comparten pipeline** en Kommo: separarlas requiere
   [colegio-sede](../entities/colegio-sede.md) y **A DEFINIR (D8)**.

## Qué debería hacer la IA

Según el [el contrato](../../CONTRATO.md): resolver lo que tenga default declarado, **repreguntar** lo
que no, y etiquetar la respuesta como **dato certificado**, **interpretación** o
**hipótesis**. Nunca mezclarlos sin distinguir.

## Respuesta esperada

**A DEFINIR (G1)** — se completa cuando las métricas estén certificadas. El valor va con la
versión de la definición usada.
