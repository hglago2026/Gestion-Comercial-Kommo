---
name: regla-tiempos
tipo: rule
titulo: Cómo se miden los tiempos del proceso
estado: en_revision
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - E5
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Tiempos

## No hay una sola fecha de inicio — **Confirmado (E5)**

> *"No existe una única fecha de inicio para todos los indicadores. La fecha depende del tipo de lead y de la etapa del proceso que se quiera medir."*

Esta es la regla que rompe cualquier intento de armar un "time to lead" único.

## Dos caminos según cómo entró el lead — **Confirmado (E5)**

**Lead de form corto:** trae lo mínimo (nombre, apellido, contacto). La primera etapa es enriquecerlo hasta tener sede, ciclo, cantidad de alumnos y niveles.
- Primer indicador: **creación → primer contacto**.
- También puede medirse el tiempo hasta completar la información, *"aunque este indicador debe interpretarse con cuidado porque parte de la demora puede depender de la respuesta de la familia y no exclusivamente de la gestión interna"*.

**Lead de form largo o ya enriquecido:** pasa de la gestión inicial multisede a la Secretaría de Ingresos de la sede.
- Desde que el lead queda completo/asignable → primer contacto de Sec. Ingresos.
- Y luego → invitación a reunión.

## La cadena de hitos — **Confirmada (E5)**

```
creación → primer contacto → información completa / form largo →
asignación a Ingresos → contacto de Ingresos → invitación a reunión → etapas posteriores
```

> *"cada tiempo se calcula entre los hitos específicos de la etapa y del responsable cuya eficiencia se quiere medir"*

## Separar gestión de espera — **Confirmado (E5)**

> *"conviene diferenciar entre tiempo interno de gestión y tiempo de espera por respuesta de la familia, para no atribuir al equipo demoras que dependen del postulante"*

Todo indicador de tiempo tiene que declarar cuál de los dos mide.

## Unidad — **Confirmado (E6)**

Días **hábiles**.

## El único umbral declarado

> *"Fundamental: Devoluc. Act.Ibio - Fecha del Taller menor o = 7 días"* (Requerimientos · Indicadores)

Es el único SLA que las fuentes ponen por escrito.

## ⚠️ Lo que hoy no se puede medir

De los siete hitos que E5 declara, el modelo tiene dato para **tres**: creación, primer contacto e invitación a reunión.

**No existen como campo ni como estado:**

- **"Form corto" vs "form largo"** — toda la lógica de E5 se apoya en esta distinción, y no hay dónde leerla.
- **"Información completa"** — no hay marca de cuándo un lead quedó enriquecido.
- **"Asignación a Ingresos"** — no hay evento de traspaso de la gestión multisede a la sede.

Sin esos tres, la mitad de los tiempos que el negocio pidió no se puede calcular. **Es el hueco de dato más grande del bloque de tiempos.**

## Advertencia sobre los campos de reunión

`FechaInvitacionReunión` guarda *"la última Fecha de Invitacion"* y `FechaAsistioReunion` *"la Fecha para la cual el CONTACTO asistió a la última Reunión"*. Los dos **pisan la historia**: no se puede reconstruir la primera invitación ni contar cuántas hubo. Cualquier "tiempo hasta la primera reunión" calculado con estos campos es, en rigor, "tiempo hasta la última reunión registrada".
