---
name: cupo
tipo: entity
titulo: Cupo
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - cupo
  - vacante
grano: lugares disponibles por sede × nivel × curso × turno × ciclo
clave_natural: A DEFINIR
fuentes:
  - cupos-y-secciones
reglas:
  - regla-fecha-de-corte
bloqueantes:
  - F1
  - F3
  - D4
  - D7
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Cupo

Cuántos lugares hay. Parece el dato más simple del modelo y es de los más discutidos.

**A DEFINIR (F1):** qué se cuenta como ocupado — matriculados, matriculados + reservas, o
capacidad física. Los tres números son distintos y los tres se llaman "ocupación".

**A DEFINIR (F3):** qué es la **excedencia de vacancia** que pidió el equipo: ¿cuántos
lugares sobran, o cuántos casos hay por encima del cupo? Ver [excedencia-de-vacancia](../metrics/excedencia-de-vacancia.md).

**El cupo necesita historia.** Si solo se guarda el valor de hoy, la pregunta *"¿cómo estaba
la ocupación al 31 de marzo?"* no tiene respuesta. Ver [regla-fecha-de-corte](../rules/regla-fecha-de-corte.md).
