---
name: gq-cuantos-inscriptos
tipo: golden_question
titulo: ¿Cuántos inscriptos tenemos?
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
pregunta: "¿Cuántos inscriptos tenemos?"
metricas:
  - efectividad-comercial
entidades:
  - alumno
  - ciclo-lectivo
reglas:
  - regla-ciclo-lectivo
  - regla-fecha-de-corte
  - regla-canonicalizacion-estados
respuesta_esperada: A DEFINIR
tolerancia: A DEFINIR
bloqueantes:
  - K1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# ¿Cuántos inscriptos tenemos?

> "¿Cuántos inscriptos tenemos?"

La pregunta más simple del dominio, y esconde **al menos cuatro decisiones**. Si el
sistema la contesta bien, entendió el modelo; si contesta un número con seguridad, no
entendió nada.

## Las cuatro ambigüedades

1. **¿Qué ciclo?** De abril en adelante conviven el corriente y el siguiente. Sin ciclo, la
   respuesta es arbitraria. Ver [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md).
2. **¿Qué es "inscripto"?** ¿[grabado-abm](../statuses/grabado-abm.md), [inscripto](../statuses/inscripto.md), [pago-reserva](../statuses/pago-reserva.md)? Tres estados,
   tres números.
3. **¿Con qué corte?** ¿A hoy, o al cierre del último mes archivado? El equipo pidió poder
   comparar contra el 31 de marzo. Ver [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md).
4. **¿Toda la red o una sede?** Quien pregunta desde una sede probablemente quiera la suya.
   El [el contrato](../../CONTRATO.md) define si eso se asume o se pregunta.

**Sin contrato, la IA elige una combinación cualquiera y responde con seguridad. Una
respuesta segura y equivocada es peor que no tener respuesta.**

## Qué debería hacer la IA

Según el [el contrato](../../CONTRATO.md): resolver lo que tenga default declarado, **repreguntar** lo
que no, y etiquetar la respuesta como **dato certificado**, **interpretación** o
**hipótesis**. Nunca mezclarlos sin distinguir.

## Respuesta esperada

**A DEFINIR (G1)** — se completa cuando las métricas estén certificadas. El valor va con la
versión de la definición usada.
