---
name: glosario
tipo: entity
titulo: Glosario del modelo de admisiones
estado: en_revision
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - A1
  - B6
  - G2
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Glosario

Cada término lleva su etiqueta: **Confirmado** (está escrito en una fuente), **A definir** (hay hueco), **Sugerencia** (lo propongo yo y no es regla).

## Las personas

**Persona** — *Sugerencia.* El chico o chica alrededor del cual gira el proceso, independientemente de cuántas veces haya postulado. No existe hoy en ninguna fuente: es la entidad que el modelo v3 introduce.

**Postulante** — *Confirmado (A3).* Estado de una persona con al menos una postulación viva que todavía no ocupa vacancia.

**Ingresante** — *Confirmado (A1).* Desde el status `RESERVA PRE ICBIO`. **Ocupa vacancia.** Es el umbral que separa el interés de la reserva efectiva.

**Alumno** — *Confirmado (A1, Definiciones).* *"a partir del momento en que pagó la Reserva de Vacante y el primer arancel y por lo tanto está ingresado físicamente en el colegio. Y ahí pasa a formar parte de la CARTERA."*
⚠️ **Hoy el modelo no puede identificar a nadie como alumno**: el dato de pago vive en Sedna, y no hay conexión con Kommo.

**Ex alumno** — *Confirmado (Definiciones).* *"ALUMNO dado de baja. Los graduados no los consideramos como Ex Alumnos."*

**Grad team** — *Confirmado (Definiciones).* *"Alumno GRADUADO, que finalizó 6to año de secundaria."*

**Cartera** — *Confirmado (Definiciones).* *"Son los alumnos reales en aula en cada momento del año que generan aranceles, ya sea mensualmente (coincidencia de devengado y emitido) o pagos anuales (arancel devengado mensualmente)."*
Es un concepto **económico**, no operativo: la cartera se define por el arancel, no por la asistencia.

**Rechazados** — *A definir.* La hoja Definiciones declara la entidad pero deja la celda de significado **vacía**.

## Los objetos del CRM

**Lead / Postulación** — *Confirmado (B2, Definiciones).* *"Es el Alumno o potencial Alumno. Aplica a un UNICO ALUMNO."* Es individual por chico, no por familia. Su identificador es el ID de Kommo.

**Contacto** — *Confirmado (Definiciones, C1).* *"Son los datos del Responsable del LEAD."* Cumple además la función de identificador de familia, porque se decidió no crear una entidad FAMILIA.

**Tarea** — *Confirmado (Definiciones · Object Entity).* Tercer tipo de objeto del CRM, junto con LEAD y CONTACTO.

**Reunión** — *Confirmado en la definición, A definir en el dato.* *"Es una reunion que puede ser presencial o virtual entre el USUARIO RESPONSABLE y el CONTACTO. Puede ser una REUNION GRUPAL o INDIVIDUAL."*
⚠️ E3: hoy **no se registra** ni el tipo ni quién la hizo.

## Los conteos

**Prospecto** — *A definir.* Hay tres definiciones incompatibles en las fuentes (ver CF-02). La más operativa dice: *"LEADS que esta en cualquier estado menos DUPLICADO - CONTACTO POR ERROR - PASO DE SEDE"*. Es el denominador de casi todas las mediciones de eficiencia, así que este hueco bloquea buena parte del tablero.

**Duplicado** — *A definir (B6).* *"cuando lead es identificado como el mismo ingresante, para un mismo ciclo y nivel"*. La misma persona postulando a otro ciclo o nivel **no** es duplicado: son oportunidades distintas.

**Fusión** — *Confirmado (Event Action).* *"Es cuando un LEAD se identifica como duplicado y el VENDEDOR lo fusiona en un único LEAD."* Es una deduplicación manual, ya ocurrida, que queda registrada en el log.

## El tiempo

**Ciclo** — *Confirmado (Definiciones).* *"Refiere al año."*

**Ciclo al que postula** — *Confirmado (Definiciones).* *"Es el CICLO pedido por el CONTACTO para la inscripción. No significa que esté confirmado."* Es mutable: puede cambiarlo la Secretaría de Ingresos por falta de vacante, decisión de la familia o error de carga (G4).

**Hito de cierre** — *Confirmado (Requerimientos · Alcance).* El 31 de marzo de cada año. De abril en adelante se reporta a la vez el ciclo corriente y el siguiente.

**Días hábiles** — *Confirmado (E6).* Unidad de todos los indicadores de tiempo.

## La capacidad

**Cupo** — *Confirmado (D4).* Cupo bruto definido anualmente por la Dirección de Desarrollo, que fija secciones y cupos por sede y turno.

**Vacancia disponible** — *Confirmado (D4).* `Cupo definido − Alumnos que ocupan/proyectan ocupar vacante`. Es dinámica: cambia con cada baja, cada ingreso confirmado y cada apertura o cierre de secciones.

**Permanencia** — *Confirmado en la definición (G8), inexistente como dato.* *"indica que ese estudiante no debe ser promocionado al curso inmediato siguiente en el ciclo lectivo siguiente"*. Es la excepción a la promoción automática de F3. El campo no existe todavía en Kommo (Solicitud 3): hoy se gestiona a mano.

## Los movimientos

**Pase de sede** — *Confirmado (G6, A5), con un conflicto abierto (CF-08).* Una familia con un hijo que ya es alumno de una sede postula a otra sede de la red. Entra como un lead común; se detecta recién cuando aparece el dato de `colegio actual`.

**Baja inmediata / a fin de año / probable** — *Confirmado (A5).* Las tres formas de salida. Se registran siempre como tipo + fecha de efecto.

## Los sistemas

**Kommo** — *Confirmado (D1).* El CRM. *"El Maestro para esta etapa es Kommo."*

**Sedna** — *Confirmado (D1).* Sistema de **facturación y cobranzas**. Ahí vive el dato de pago que define al ALUMNO.

**Hosking** — *Confirmado (D1).* Sistema de **calificación** de alumnos.

**Handing** — *Confirmado (D1).* Sistema de **comunicación** con las familias.

**ABM** — *Confirmado (Mapa de status).* El acto de dar de alta en Sedna, Hosking y Handing. Es donde el proceso sale de Kommo.

**App DOE** — *A definir (D3).* Plataforma donde se cargan encuestas, informes, boletines y la devolución del DOE. La definición del DOE (aceptado / aceptado condicionado / rechazado) **cambia el status del lead**.

**Visualización de Vacancia** — *Confirmado (D4).* La vista dinámica de lugares disponibles por sede, nivel, turno y ciclo.
