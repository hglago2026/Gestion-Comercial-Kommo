---
name: registro-faltantes
tipo: governance
titulo: Registro de faltantes
estado: en_revision
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - I1
  - I2
  - I3
  - J1
  - J2
  - J3
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Registro de faltantes

## A · Preguntas sin responder (5)

| ID | Pregunta | Qué bloquea | Quién decide |
|---|---|---|---|
| **I2** | ¿Quién opera el proceso de carga una vez construido? | El proceso diario de D2/D6 no tiene responsable. Sin dueño operativo no hay SLA de actualización, y toda métrica queda sin fecha de corte garantizada | Sistemas + Sec. Ingresos |
| **I3** | ¿La base oficial tiene que permitir carga manual desde el negocio? | Si la respuesta es sí, hace falta un circuito de validación y atribución para ese dato. Hoy el modelo asume que todo entra por el pipeline | Sistemas + E. Directivos |
| **J1** | ¿Quién puede ver qué? | **Seguridad a nivel fila por sede.** Con 6 sedes en la red, ningún tablero tiene hoy una regla que le impida cruzar datos entre colegios | E. Directivos |
| **J2** | ¿Qué datos de menores se pueden almacenar y por cuánto tiempo? | Retención y minimización de PII: `nro_doc`, `fecha_nacimiento`, `inclusion`, `informacion_relevante` (texto libre). También la Solicitud 2, que pide guardar rechazados y cruzarlos por DNI | E. Directivos + Legales |
| **J3** | ¿Quién es el dueño de la base oficial? | **Es el bloqueante estructural.** Sin aprobador declarado, ninguna regla puede pasar de `en_revision` a `certificado`. Todo el modelo queda provisorio | E. Directivos |

## B · Preguntas respondidas pero marcadas `A DEFINIR` (8)

| ID | Tema | Qué dice la respuesta | Qué falta cerrar |
|---|---|---|---|
| **B6** | Definición de duplicado | "A confirmar con NE y NV" + la definición operativa cargada en la columna equivocada | Confirmar. Bloquea `persona_id` y todo conteo de personas únicas |
| **D2** | Extracción automática | Scraper diario → MySQL; "en primera instancia será el mismo archivo en un excel" | Fecha en que deja de ser Excel manual |
| **D3** | App DOE | Qué guarda y qué se necesita; "A definir con NE" | Qué campos se traen y cómo se integran |
| **D6** | Frecuencia de refresco | "export diario incremental sobre una base MySQL en un servidor web" | Confirmar que existe; hoy es un export manual (2026-08-04) |
| **F4** | Curso y turno por sede | NFS: turno sólo K1-K3 · LTHP: sin turnos · CDF Benavídez y Escobar: todos los cursos | **Falta LTH Hudson**, que la respuesta no menciona |
| **G1** | Lista de indicadores | "Si tal cual en una primera etapa" | Ratificación definitiva y congelamiento como v1 |
| **G5** | Normalización de etiquetas | "Parcialmente" — bots + carga manual de las secretarias | Qué subconjunto de etiquetas es gobernado y usable para medir |
| **G7** | Recupero de años anteriores | "no esta procedimentado tan especificamente" | Procedimiento, si se quiere medir la Solicitud 4 |

## C · Preguntas marcadas `Pendiente` (4)

| ID | Tema | Respuesta cargada | Qué falta |
|---|---|---|---|
| **G8** | Etiqueta de permanencia | "indica que ese estudiante no debe ser promocionado al curso inmediato siguiente" | El campo **no existe en Kommo** (Solicitud 3). Es la excepción a F3 |
| **H1** | Snapshots mensuales | "A validar con NE. Sí, y además historial completo de transiciones" | Validación |
| **H3** | Corrección retroactiva | "Si pero el reporte publicado se congela" | Cómo se implementa el congelamiento |
| **I1** | Motor de la base | "Validar con NE" | **Sin esto no se puede construir la Capa 1.** Es el bloqueante técnico principal |

## D · Huecos estructurales que no vienen del cuestionario

| Hueco | Qué falta | Qué bloquea | Prioridad |
|---|---|---|---|
| **Catálogo de niveles y cursos** | Ninguna fuente lista los niveles por sede ni su orden. Aparecen sueltos K1, K2, K3, K4, "sala de 1", "segundo grado", "6to año" | Promoción de nivel (F3) · métricas 8 y 9 · dominio de `cupo` · consistencia edad↔curso (B3) | **Alta** |
| **Orden canónico de estados** | No existe en ninguna fuente | No hay embudo calculable ni definición formal de "avanzar" / "retroceder" | **Alta** |
| **Turno de LTH Hudson** | F4 no la menciona | Grano de la dimensión turno para esa sede | Media |
| **Dominios de desplegables** | "Motiva su postulacion", "Motivo Baja/Desiste", "Tipo Doc" | Filtros y agrupaciones por esos campos | Media |
| **Form corto vs form largo** | E5 basa toda su lógica de tiempos en esa distinción, pero no existe como campo ni como estado | La mitad de los tiempos que pide E5 | **Alta** |
| **"Información completa" / "asignación a Ingresos"** | Hitos que E5 nombra y que no existen como dato | Los tiempos de la segunda etapa del embudo | Media |
| **Actividad comercial real** | Ninguna fuente declara que el log registre mensajes, llamados o contactos efectivos | Toda métrica de esfuerzo comercial | Media |
| **Autoría de las reglas** | La columna `RESPONDE` está vacía en 49 de 50 preguntas | El contrato semántico exige atribución; hacia atrás no la hay | **Alta** |

## E · Solicitudes del negocio y su estado en el modelo

Las 12 solicitudes de la hoja `Solicitudes`, contra lo que el modelo puede sostener hoy:

| # | Solicitud | ¿El modelo la soporta? |
|---|---|---|
| 1 | Validación fecha de nacimiento ↔ año y curso, con alerta de excepciones | **No** — falta el catálogo de niveles/cursos |
| 2 | Base de rechazados vinculada a futuros leads por DNI | **Parcial** — el DNI existe (B1) pero no es identificador (B4); y J2 no define si se puede conservar |
| 3 | Etiqueta de permanencia en Kommo | **No** — el campo no existe |
| 4 | Recupero de solicitudes anteriores | **No** — G7: sin procedimiento |
| 5 | Foto mensual de ocupación y vacancia | **Sí, modelado** — D4 + H1, pendiente de validación |
| 6 | Transformar PDF históricos de NV en base | **Fuera de alcance del modelo** — es una migración |
| 7 | Lista de espera calificada por hermano sin cupo | **Sí** — existe `ESPERANDO VACANTE HNO` |
| 8 | Identificar quiénes pagaron reserva y firmaron CE | **No** — depende de la conexión con Sedna (A1) |
| 9 | Proyección de cartera | **Parcial** — F3 da la promoción, pero la permanencia es manual |
| 10 | Usuarios individuales para medir performance | **No** — E4 |
| 11 | Cambios de turno para el ciclo siguiente | **Modelado** — `TurnoAñoSig` existe |
| 12 | Recalificación de solicitudes para un ciclo lectivo en NFSP | **Parcial** — G4 da la regla de reasignación de ciclo |
