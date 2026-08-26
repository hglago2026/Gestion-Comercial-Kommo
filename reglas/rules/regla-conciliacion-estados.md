---
name: regla-conciliacion-estados
tipo: rule
titulo: Conciliación de los dos catálogos de estados
estado: en_revision
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - E1
  - G2
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Conciliación de estados

## El problema

Las fuentes traen **dos catálogos de estados que no coinciden**, con nomenclaturas distintas y granularidades distintas:

| Catálogo | Filas | Qué es | Columnas |
|---|---|---|---|
| **Ref - Mapa de status** | 18 filas de status transcriptas | El **proceso de negocio** de punta a punta, incluido el tramo que ocurre fuera de Kommo | STATUS · DESCRIPCIÓN · GESTOR |
| **Diccionario Status** | 39 filas | Los **estados operativos que existen en Kommo**, incluidos los que están mal definidos o duplicados | # · Status · Definición · dato en Kommo que genera el cambio |

**No los fusioné por criterio propio.** Abajo va la conciliación fila por fila. Donde la equivalencia está escrita en la fuente, se marca `certificada`. Donde la deduje por coincidencia de nombre o de definición, se marca `propuesta` y requiere confirmación.

> **Nota de conteo:** el encabezado del volcado del Sheet declara 17 status para "Ref - Mapa de status", pero se transcribieron 18 filas. Verificar en la fuente. (CF-07)

---

## Tabla de conciliación

Convenciones: **OV** = ocupa vacancia · **PR** = cuenta como prospecto · *cert.* = la fuente lo dice explícitamente · *prop.* = equivalencia propuesta por el modelador, a confirmar.

| Código canónico propuesto | Ref - Mapa de status | Diccionario Status | Definición (fuente) | Dato de Kommo que dispara | Gestor | OV | PR | Decisión pendiente |
|---|---|---|---|---|---|---|---|---|
| `CONTACTO_INICIAL` | CONTACTOS / LEADS | 1 · Contacto inicial · *(prop.)* | "Todos los leads que se generan por cualquier canal en Kommo" / "1er registro de la familia x impulso redes o ingreso web" | — | Automático | No | Sí | ¿`Incoming leads` (Dicc., "??? creo que es igual a CONTACTO INICIAL") es el mismo estado? La fuente lo pregunta, no lo afirma |
| `NUEVO` | — | 2 · NUEVO | "registro en Form Full tenemos todos los datos del alumno y la familia" | — | — | No | Sí | El mapa de proceso no tiene este estado. ¿Es un subestado de CONTACTO_INICIAL? |
| `POSTULANTE` | PROSPECTOS *(prop., ver CF-02)* | 3 · POSTULANTE | "la secretaria de ingresos reviso el lead e hizo 1er contacto" | **FECHA 1ERA COM** | Sec. Ingresos | No | Sí | PROSPECTOS tiene dos definiciones incompatibles (CF-02) |
| `INCONTACTABLE` | INCONTACTABLES | *(no figura)* | "Leads incompletos o calificados como tal tras la primera gestión de contacto" | — | Front Comercial | No | Sí | ¿Cómo se registra en Kommo? Candidato: `Leads perdidos (No contesta)` |
| `DESISTE_CONTACTO_INICIAL` | DESISTEN EN CONTACTO INICIAL | 11-25 · variantes de "Leads perdidos (...)" *(prop.)* | "Error de zona, nivel arancelario, impulso o error en la postulación" | — | Front Comercial | No | Sí | ¿Cada motivo del mapa mapea a una variante de Leads perdidos? |
| `FILTRO_SEMAFORO` | FILTRO SEMÁFORO | *(no figura)* | "Casos que se filtran al leer la información de postulación" | — | Sec. Ingresos | No | Sí | **No existe en Kommo.** ¿Es un paso manual o un estado a crear? |
| `INVITADO_A_REUNION` | INVITADOS A REUNIÓN | *(no figura como status)* | *(sin descripción en la fuente)* | *(FechaInvitacionReunión, prop.)* | Sec. Ingresos | No | Sí | El dato existe como campo del lead, no como status |
| `REUNION_PRESENTACION` | REUNIÓN PRESENTACIÓN | *(no figura como status)* | "Si asisten pasan a Desiste, Esperando Familia o Avanzan. Si no asisten vuelven a Prospectos" | *(FechaAsistioReunion, prop.)* | E. Directivos | No | Sí | Este es el punto donde el mapa declara el **retroceso** ("vuelven a Prospectos"), consistente con E2 |
| `ESPERANDO_FAMILIA` | ESPERANDO FAMILIA | 4 · ESPERANDO FAMILIA + 4 · ESPERANDO FLIA | "asistieron a reunion - aun no avanzan" | **FECHA ASISTIOREUNION** | Sec. Ingresos | No | Sí | La propia fuente marca el duplicado: "idem anterior status duplicado??" → **unificar** (CF-01a) |
| `ESPERANDO_VACANTE` | LISTA DE ESPERA *(prop.)* | 5 · ESPERANDO VACANTE | "asistio a reunion - quiere avanzar pero no hay vacante" | **FECHA ASISTIOREUNION** | Sec. Ingresos | No | Sí | ¿"Lista de espera" del mapa = "Esperando vacante" de Kommo? Nombres distintos, definición compatible |
| `ESPERANDO_VACANTE_HNO` | *(no figura)* | 5 · ESPERANDO VACANTE HNO | "asistio a reunion - quiere avanzar pero no hay vacante y tiene otro/s hermanos para el ingreso o es hno de un alumno del colegio" | **FECHA ASISTIOREUNION** | — | No | Sí | Resuelve la **Solicitud 7** (calificar la lista de espera por hermano). Ojo: comparte el `#5` con el anterior en la fuente |
| `AVANZAN` | AVANZAN | *(no figura como status)* | "Pasan al DOE para lectura de encuestas. K1-K2 con vacante → Intercambio OK; K3+ con vacante → Taller; sin vacante → Lista de Espera; o Rechazo" | — | DOE | No | Sí | Es una **bifurcación por nivel**, no un estado estable. Define ruta según K1-K2 vs K3+ |
| `TALLER_INTERCAMBIO` | TALLER INTERCAMBIO | *(no figura como status)* | "Aprobados pasan a Intercambio OK. Aprobados condicionados y rechazados pasan a Devolución" | *(FechaTallerDOE, prop.)* | DOE | No | Sí | "Devolución" aparece como destino pero no existe como estado en ningún catálogo |
| `RESERVA_PRE_ICBIO` | *(no figura)* | 6 · RESERVA PRE ICBIO | "asistieron a reunion - piden avanzar hay vacante. No implica definicion de avance a taller. Puede haber reservas que luego se bajen si la encuesta en rechazada" | FECHA ASISTIOREUNION + FECHA TALLER DOE *(no obligatoria si es KINDER DE 1 A 3 años, donde no se hace taller)* | — | **Sí** *(cert. A1)* | Sí | **Umbral de INGRESANTE.** El mapa de proceso NO tiene este estado, aunque es el más importante del modelo (CF-01b) |
| `RECHAZADO` | *(implícito en AVANZAN: "o Rechazo")* | 7 · RECHAZADO | "Puede darse post reunion o post taller" | FECHA ASISTIOREUNION + FECHA TALLER DOE (podría no estar si el rechazo fue sobre la encuesta) | DOE | No | Sí | La hoja Definiciones tiene una entidad RECHAZADOS **sin definición** (celda vacía). Solicitud 2 pide vincularlos con futuros leads por DNI |
| `ICBIO_OK` | INTERCAMBIO OK | 8 · ICBIO OK | "asistio a reunion avanzo y aprobo taller. Aun no envio los datos del ALTA" | FECHA ASISTIOREUNION + FECHA TALLER DOE + **FECHA CONFIRMACION VACANTE** | Sec. Ingresos | Sí *(deriv. A1)* | Sí | **Mismo estado, dos nombres.** La 4ª columna del mapa trae literalmente "Icbio Ok", lo que confirma la equivalencia (CF-01c) |
| `GRABADO_EN_ABM` | GRABADO ABM | 9 · GRABADO EN ABM | "Alta en Sedna, Hosking y Handing" / "asistio a reunion avanzo y aprobo taller, confirmamos y envio datos para el alta" | FECHA ASISTIOREUNION + FECHA TALLER DOE + FECHA CONFIRMACION VACANTE | Soporte | Sí *(deriv. A1)* | Sí | **Mismo estado, dos nombres.** La 4ª columna del mapa trae "Grab ABM" (CF-01c). Es el punto donde el proceso sale de Kommo |
| `PAGO_MATRICULA` | *(no figura)* | *(propuesto)* · PAGO MATRICULA | "identifica alumnos que luego de la confirmacion dieron el alta y realizaron el pago de matricula. estado siguiente a GRABADO EN ABM" | — | — | Sí | Sí | **No existe todavía.** Está en la sección "Status para Kommo que no tenemos y podrian servir". Es exactamente el estado que A1 necesita para poder declarar ALUMNO. Solicitud 8 |
| `INSCRIPTO` | INSCRIPTO | *(no figura)* | "Emite contrato y cobra DI" | — | Administración | Sí | — | Fuera de Kommo |
| `DOCUMENTACION` | DOCUMENTACIÓN | *(no figura)* | "Recopila y hace seguimiento del legajo inicial" | — | Front | Sí | — | Fuera de Kommo |
| `LEGAJO` | LEGAJO | *(no figura)* | "Completa el legajo del estudiante" | — | Sec. Pedagógica | Sí | — | Fuera de Kommo |
| `EN_CURSO` | *(no figura)* | 29 · EN CURSO | "alumnos que pasaron por todo el proceso y al iniciar el ciclo lectivo los sumamos al curso" | — | — | **Sí** | No *(prop.)* | Es el estado de alumno activo. ¿Debe seguir contando como prospecto? Evidentemente no, pero la regla de la columna `regala` no lo excluye |
| `PASO_DE_SEDE` | *(no figura)* | 10 · PASO DE SEDE | "puede darse en cualquier momento del proceso y es una recomendacion de la Sec. Ingresos de seguir el proceso en otra sede o modelo" | — | — | No | **No** *(cert.)* | Excluido de prospectos por la regla de la columna `regala`. **Ojo:** esta definición (recomendación de Sec. Ingresos) NO es la misma que la de G6, donde el pase lo inicia la familia (CF-08) |
| `DUPLICADO` | DUPLICADOS | 14 · Leads perdidos (Duplicado) | "Deberían restarse o eliminarse. Ojo: diferenciar si postularon más de una vez en años anteriores u otra sede" / "el lead se contacto varias veces. El seguimiento debe hacerse en un mismo lead. Distorsiona la base de postulaciones" | "No es prospecto" | Soporte Ventas | No | **No** *(cert.)* | Definición operativa en B6, marcada A DEFINIR |
| `CONTACTO_POR_ERROR` | *(no figura)* | 13 · Leads perdidos (Contactó por Error) | "sirve para evaluar la efectividad de campañas. No suma a postulaciones porque no es un prospecto" | "No es prospecto" | — | No | **No** *(cert.)* | — |
| `LEAD_PERDIDO` | *(no figura)* | 11 · Leads perdidos + 12 · Closed - lost | "puede darse en cualquier momento del proceso desde el inicio cuando el lead no es contactable o informa que desiste del proceso" | — | — | No | Sí | La fuente dice explícitamente que `Closed - lost` "es lo mismo que LEAD PERDIDO" → **unificar** *(cert.)* |
| `LEAD_PERDIDO_<MOTIVO>` | *(no figura)* | 15-25 · Económico, Egresado, Familiar, Fuera de Nivel, Mudanza, No contesta, No se mudó, No se van de su colegio actual, Proyecto, Sin Reunión, Viaje | Todas comparten el mismo texto genérico salvo "Fuera de Nivel": "el curso del alumno no corresponde a los disponibles en esa sede (ej, sala de 1 en CDF)" | — | — | No | Sí | ¿Son estados distintos o un estado `LEAD_PERDIDO` con dimensión `motivo`? **Recomendación del modelador: lo segundo** (SUGERENCIA) |
| `BAJA` | *(no figura)* | 26 · BAJA | "baja durante el año en curso" | — | — | No | No *(prop.)* | Ver `baja.yaml` |
| `BAJA_FIN_DE_ANIO` | *(no figura)* | 27 · BAJA FIN DE AÑO | "baja al finalizar el año en curso" | — | — | Sí, hasta fin de ciclo | No *(prop.)* | En la fuente aparece con encoding roto: `BAJA FINDEAÃO` (CF-09) |
| `BAJA_PROBABLE` | *(no figura)* | 28 · BAJA PROBABLE | "informacion referida a una posible baja" | — | — | Sí, provisoriamente | No *(prop.)* | A5 dice "en principio" no computar en cartera: sin cerrar |
| `DESISTE_EN_ADM` | *(no figura)* | *(propuesto)* · Leads perdidos (Desiste en ADM) | "identifica a alumnos que habiendo pasado por el proceso desistieron luego de la confirmacion / matriculacion" | — | — | — | — | **No existe todavía.** Sin él no se puede medir la caída post-confirmación |

## Estados declarados como no usados o sin definir

| Status (Diccionario) | Qué dice la fuente | Decisión requerida |
|---|---|---|
| `DESISTE` | "NO USAMOS ESTE ESTADO" — pero el Mapa de proceso **sí** lo incluye como estado gestionado por Sec. Ingresos | Contradicción directa entre las dos fuentes (CF-01d) |
| `Historico` | *(sin definición)* | ¿Qué es? |
| `Incoming leads` | "??? creo que es igual a CONTACTO INICIAL" | Confirmar y unificar |
| `Leads perdidos (Razón eliminada)` | "????" | ¿Se depreca? |
| `NO DEFINIDO` | "????" | ¿Se depreca? |

---

## Reglas de estado que sí quedan certificadas

1. **Umbral de ocupación de vacancia.** Cita A1: *"A partir del status RESERVA PRE ICBIO (Reserva Pre Intercambio), lo consideramos INGRESANTE. Implica que ocupa vacancia."* Todo estado anterior no ocupa; ese y los posteriores sí.
2. **Umbral de ALUMNO.** Cita A1: *"ALUMNO es a partir del momento en que pagó la Reserva de Vacante y el primer arancel."* Ese dato **no está en Kommo**: vive en Sedna. Hoy ningún estado de Kommo alcanza para declarar ALUMNO.
3. **Definición de PROSPECTO.** Cita del Diccionario Status, columna `regala`: *"Prospectos = LEADS que esta en cualquier estado menos DUPLICADO - CONTACTO POR ERROR - PASO DE SEDE que es un lead para otra sede"*.
4. **El proceso no es lineal.** Cita E2. Un lead puede volver de `INVITADO_A_REUNION` a un estado anterior, cambiar de ciclo, pasar a `ESPERANDO_VACANTE` o cambiar de sede y reiniciar parte del recorrido. **Por lo tanto no existe un orden total de estados**, y cualquier embudo debe construirse sobre la tabla de transiciones, no sobre el estado actual.
5. **El tramo final ocurre fuera de Kommo.** Nota al pie del Mapa de status: *"Resaltado: el tramo final del embudo ocurre fuera de Kommo. Es ahí donde la persona se convierte en ALUMNO, y es justamente el tramo que el modelo actual no contempla."*

## Lo que NO se puede cerrar sin una decisión del negocio

- La equivalencia entre los estados del **proceso** (mapa) y los estados **operativos** (Kommo). Seis estados del mapa no tienen contraparte en Kommo: `FILTRO_SEMAFORO`, `INVITADO_A_REUNION`, `REUNION_PRESENTACION`, `AVANZAN`, `TALLER_INTERCAMBIO`, `INCONTACTABLE`.
- Si las 12 variantes de `Leads perdidos (...)` son estados o un estado con motivo.
- Si `EN CURSO`, las bajas y los estados post-ABM deben excluirse del denominador de prospectos.
- El orden canónico de estados, sin el cual no hay embudo ni "avance" calculable.
