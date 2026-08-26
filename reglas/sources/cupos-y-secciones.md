---
name: cupos-y-secciones
tipo: source
titulo: Cupos y secciones por sede
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema: A DEFINIR (D4)
grano: cupo por sede × nivel × curso × turno
metodo_extraccion: A DEFINIR (D4)
frecuencia: A DEFINIR (D4)
bloqueantes:
  - D4
  - D7
  - F1
reglas:
  - regla-landing-zone-raw
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Cupos y secciones por sede

Sin cupo no hay ocupación, y sin ocupación no hay vacancia ni lista de espera calificada.

## Qué contiene

La cantidad de lugares por **sede × nivel × curso × turno** y la apertura de secciones.
El prototipo v11 ya trabaja con cupos extraídos de planilla — **Confirmado** que el dato
existe; **A DEFINIR (D4)** cuál es la planilla oficial y quién la mantiene.

## Por qué es delicada

El cupo **cambia durante el ciclo** (se abre una sección, se corre un alumno de turno). Si
se guarda solo el cupo de hoy, no se puede reconstruir la ocupación de marzo, que es
justamente lo que pide el equipo. Esto es un requerimiento directo sobre la Capa 1:
el cupo necesita **historia**, no solo valor corriente.

## Decisiones abiertas

- **A DEFINIR (D4)** — cuál es la planilla oficial, quién la mantiene y con qué frecuencia.
- **A DEFINIR (F1)** — qué se cuenta como cupo: matriculados, matriculados + reservas,
  o capacidad física.
- **A DEFINIR (D7)** — contra qué fuente se compara la ocupación.
