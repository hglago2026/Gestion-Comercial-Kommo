---
name: ciclo-lectivo
tipo: entity
titulo: Ciclo lectivo
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - ciclo lectivo
grano: un año lectivo
clave_natural: año
reglas:
  - regla-ciclo-lectivo
bloqueantes:
  - G4
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Ciclo lectivo

**Confirmado:** en el dato aparecen ciclos de **2021 a 2028**.

**Confirmado (requerimiento del equipo):** de abril en adelante conviven el ciclo corriente
y el siguiente, y el reporte debe mostrar los dos. Esa convivencia es la primera ambigüedad
que enfrenta cualquier pregunta del tipo *"¿cuántos inscriptos tenemos?"*. Ver
[gq-cuantos-inscriptos](../golden_questions/gq-cuantos-inscriptos.md) y [regla-ciclo-lectivo](../rules/regla-ciclo-lectivo.md).

**A DEFINIR (G4):** el segundo campo de ciclo (`ciclo_nivel`), hoy un placeholder sin carga.
