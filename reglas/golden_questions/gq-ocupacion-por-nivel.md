---
name: gq-ocupacion-por-nivel
tipo: golden_question
titulo: ¿Qué niveles van a quedar sin cupo el ciclo que viene?
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
pregunta: "¿Qué niveles van a quedar sin cupo el ciclo que viene?"
metricas:
  - ocupacion-por-curso-y-nivel
entidades:
  - cupo
  - nivel
reglas:
  - regla-promocion-de-niveles
  - regla-fecha-de-corte
respuesta_esperada: A DEFINIR
tolerancia: A DEFINIR
bloqueantes:
  - K1
  - G1
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# ¿Qué niveles van a quedar sin cupo el ciclo que viene?

> "¿Qué niveles van a quedar sin cupo el ciclo que viene?"

La pregunta que la dirección hace de verdad, y la que más supuestos encadena.

## Ambigüedades

1. **¿Ocupado es matriculado, matriculado + reserva, o capacidad física?**
   **A DEFINIR (F1)** — tres números distintos con el mismo nombre.
2. **¿Se promocionan los niveles?** Sin [regla-promocion-de-niveles](../rules/regla-promocion-de-niveles.md) la respuesta está
   sistemáticamente mal.
3. **¿Cuántos se van?** La tasa de permanencia es **A DEFINIR (F4)**; asumir que nadie se va
   infla la ocupación proyectada.
4. **¿De dónde sale la matrícula?** Hoy sale de Kommo, que no es donde vive el
   [alumno](../entities/alumno.md). **A DEFINIR (D7)**.

**Con cuatro supuestos encadenados, la respuesta honesta es una hipótesis etiquetada como
tal**, no un dato certificado.

## Qué debería hacer la IA

Según el [el contrato](../../CONTRATO.md): resolver lo que tenga default declarado, **repreguntar** lo
que no, y etiquetar la respuesta como **dato certificado**, **interpretación** o
**hipótesis**. Nunca mezclarlos sin distinguir.

## Respuesta esperada

**A DEFINIR (G1)** — se completa cuando las métricas estén certificadas. El valor va con la
versión de la definición usada.
