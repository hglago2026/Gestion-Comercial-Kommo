---
name: estado-de-las-metricas
tipo: governance
titulo: Fichas de métricas v1 y su estado real
estado: en_revision
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - G1
  - G2
  - G3
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Fichas de métricas

## Base de estas fichas

La lista de indicadores y sus fórmulas salen del Sheet **"Requerimientos Tablero Ingresos"** (`1p0RjtKo2So_tiDG5CCKeMI9pyaKMXo6fd7EohCxKOqg`, hoja *Indicadores*), y fueron **ratificadas por el equipo** en la pregunta G1.

> Cita G1 (verbatim): **"Si tal cual en una primera etapa"**
> Estado en la fuente: `A DEFINIR` — la ratificación es explícitamente provisoria.

Por lo tanto: **ninguna métrica de este documento está certificada.** Todas son `en_revision`, versión 1, con vigencia "primera etapa".

## Reglas transversales

| Regla | Cita | Estado |
|---|---|---|
| Unidad de tiempo | E6: **"dias habiles"** | certificado |
| No hay una única fecha de inicio | E5: *"cada tiempo se calcula entre los hitos específicos de la etapa y del responsable cuya eficiencia se quiere medir"* | certificado |
| Separar gestión de espera | E5: *"conviene diferenciar entre tiempo interno de gestión y tiempo de espera por respuesta de la familia, para no atribuir al equipo demoras que dependen del postulante"* | certificado |
| Hito de cierre | Alcance: *"visibilidad de status a la fecha con mismo hito de cierre al 31-3 de cada año. Por lo tanto de abril en adelante hay que mostrar actividad para el ciclo lectivo corriente y para el ciclo lectivo siguiente"* | certificado |
| Dimensiones mínimas | Alcance: *"por sede, nivel, curso y turno en el caso de los CDF´s"* + origen (campaña vs orgánico) y canal | certificado |

---

## 0. `prospectos` — el denominador de todo

**⚠️ ESTA MÉTRICA NO SE PUEDE CALCULAR TODAVÍA. Hay dos definiciones incompatibles en las fuentes.**

| Variante | Fuente | Qué excluye |
|---|---|---|
| **A** | Diccionario Status, columna `regala` | DUPLICADO · CONTACTO POR ERROR · PASO DE SEDE |
| **B** | Cuestionario G2 (respuesta "ok" a la sugerencia) | duplicados · incontactables · proveedores · CVs — y **deja el Filtro Semáforo DENTRO** |
| **C** | Requerimientos Tablero Ingresos, hoja Proceso | *"los leads reales (restados los grupos anteriores a Contactos)"* → duplicados, incontactables, desisten en contacto inicial, filtro semáforo |

Las tres listas son distintas. La variante B excluye "proveedores y CVs", que **no existen como estado** en ningún catálogo. La variante A excluye PASO DE SEDE, que las otras dos no mencionan.

- **Numerador:** —
- **Denominador:** —
- **Decisión requerida:** enumerar de una vez, por código de estado, qué se resta de CONTACTOS/LEADS.
- **Responsable:** Sec. Ingresos.
- **Estado:** `A DEFINIR`. **Bloquea 6 de las 10 métricas de abajo.**

> Nota sobre la respuesta G2: la celda dice literalmente **"ok"**, y la columna ESTADO quedó vacía. Se interpreta como aceptación de la sugerencia ofrecida en esa fila, pero es una interpretación: un "ok" no enumera. No se certifica.

---

## 1. `calidad_de_leads`

- **Pregunta de negocio:** de todo lo que entra, ¿cuánto es real?
- **Fórmula (fuente):** `Prospectos / Contactos-Leads`
- **Comentario de la fuente:** *"(depuramos errores, proveedores, cvs, etc)"*
- **Numerador:** cantidad de postulaciones que califican como prospecto → **bloqueado por la métrica 0**
- **Denominador:** todas las postulaciones creadas en el período (`CONTACTO_INICIAL` = universo completo)
- **Dimensiones:** sede · nivel · curso · turno · ciclo · canal · campaña/orgánico
- **Regla temporal:** por fecha de creación del lead
- **Exclusiones:** las del denominador de prospectos
- **Fuente:** Requerimientos Tablero Ingresos · Indicadores · fila "Calidad de Leads"
- **Owner:** Sec. Ingresos · **Aprobador:** A DEFINIR · **Versión:** 1 · **Estado:** `bloqueada`

## 2. `leads_condicionados`

- **Fórmula (fuente):** `Filtro Semáforo / Prospectos`
- **Comentario de la fuente:** *"ejemplo límite para incorporar necesidades especiales"*
- **Numerador:** postulaciones en `FILTRO_SEMAFORO`
- **⚠️ HUECO:** `FILTRO_SEMAFORO` **no existe como estado en Kommo** (no figura en el Diccionario Status). El indicador está ratificado pero no tiene dato de origen.
- **Relación con `inclusion`:** el atributo `Inclusion` del lead ("Son aqullos LEADS que requieren integración especial") parece cubrir el mismo fenómeno. **No confirmado.**
- **Estado:** `sin fuente de datos`

## 3. `efectividad_convocatoria`

- **Fórmula (fuente):** `Asisten a Reunión / Prospectos invitados`
- **Responsable de la medición (fuente):** *"Medición S.I."* (Secretaría de Ingresos)
- **Numerador:** postulaciones con `fecha_asistio_reunion` no nula *(mapeo propuesto, no certificado)*
- **Denominador:** postulaciones invitadas → `INVITADO_A_REUNION`
- **⚠️ HUECO:** `INVITADO_A_REUNION` no existe como estado en Kommo. Existe el campo `FechaInvitacionReunión`, pero **guarda sólo la última invitación**, así que no permite contar invitaciones ni reconstruir el universo de invitados a una fecha pasada.
- **Estado:** `en_revision con reserva metodológica`

## 4. `reuniones_por_tipo`

- **Fórmula (fuente):** conteo por `Presencial Individual · Presencial Grupal · Virtual Individual · Virtual Grupal`
- **Comentario de la fuente:** *"Efectividad dependiendo del tipo de reunión"*
- **⚠️ SIN FUENTE DE DATOS.** Cita E3 (verbatim): *"No, y tampoco por tipo de entrevista que puede ser individual presencial, individual virtual, grupal presencial o grupal virtual. Debería quedar identificada la tipología al momento de generar la reunión."*
- **Estado:** `imposible de calcular hoy`. Requiere el cambio operativo que pide E3.

## 5. `efectividad_comercial`

- **Fórmula (fuente):** `(Reservas + Lista de Espera) / Asisten a Reunión`
- **Responsable de la medición (fuente):** *"Medición E.D./S.I."*
- **Numerador:**
  - **Reservas = `RESERVA_PRE_ICBIO`.** Cita G3 (verbatim): *"Reserva Pre Intercambio."* — el equipo **descartó** la sugerencia (INTERCAMBIO OK) y eligió el estado anterior. Coherente con A1: es el momento en que se ocupa vacancia.
  - **Lista de Espera = `ESPERANDO_VACANTE`** *(mapeo propuesto)*. **Pendiente:** ¿incluye también `ESPERANDO_VACANTE_HNO`? Las fuentes no lo dicen.
- **Denominador:** postulaciones con `fecha_asistio_reunion` no nula
- **Dimensiones:** sede · nivel · curso · turno · ciclo · rol responsable
- **Regla temporal:** ambos términos medidos sobre el mismo período de asistencia a reunión
- **⚠️ Pregunta abierta que trae la propia fuente:** *"tenemos identificado quién hizo la entrevista en el caso de las individuales?"* → **E3 responde que NO.** La métrica se puede calcular a nivel sede, **no** a nivel persona.
- **Estado:** `en_revision` — es la métrica mejor definida del conjunto.

## 6. `excedencia_vacancia`

- **Fórmula (fuente):** `Lista de Espera / Asisten a Reunión`
- **Numerador:** `ESPERANDO_VACANTE` *(+ hermano, pendiente)*
- **Denominador:** ídem métrica 5
- **Lectura:** mide demanda insatisfecha; es el complemento comercial de la vacancia.
- **Estado:** `en_revision`

## 7. `desisten`

- **Fórmula (fuente):** `Desisten / Asisten a Reunión`
- **⚠️ CONFLICTO:** el estado `DESISTE` figura en el Diccionario Status con la nota **"NO USAMOS ESTE ESTADO"**, pero el mapa de proceso sí lo tiene como estado gestionado por Sec. Ingresos, y este indicador lo requiere. Candidatos de reemplazo: las 12 variantes de `Leads perdidos (...)`.
- **Decisión requerida:** ¿qué estados componen "Desisten"?
- **Estado:** `A DEFINIR`

## 8. `postulantes_sin_actividad_intercambio` / `postulantes_con_actividad_intercambio`

- **Fórmula (fuente):**
  - SIN: *"Cuenta y % postulantes Reserva para Kinder 1 y 2"*
  - CON: *"Cuanta y % postulantes Kinder 3 +"*
- **Regla de negocio que lo sostiene** (Mapa de status · AVANZAN): *"K1-K2 con vacante → Intercambio OK; K3+ con vacante → Taller"*. Y el Diccionario Status confirma la excepción: en `RESERVA PRE ICBIO`, la fecha de taller *"No esta completa si es KINDER DE 1 A 3 años donde no se hace taller"*.
- **⚠️ BLOQUEADO POR `dim_nivel`:** ninguna fuente aporta el catálogo de niveles. Sin saber qué niveles existen y en qué orden, "K3 +" no es computable.
- **Estado:** `bloqueada por dimensión`

## 9. `rechazados`

- **Fórmula (fuente):** `Rechazados / Postulantes CON Act.Ibio.`
- **Numerador:** `RECHAZADO` — *"Puede darse post reunion o post taller"*
- **Denominador:** métrica 8 (CON actividad de intercambio)
- **Nota:** la hoja Definiciones tiene una entidad **RECHAZADOS con la definición vacía**. Y la Solicitud 2 pide que la base de rechazados se vincule con futuros leads por DNI para generar alerta si vuelven a aplicar.
- **Estado:** `bloqueada por dimensión` (depende de la 8)

## 10. `tiempos_entre_status`

Cita de la fuente: *"Fundamental: Devoluc. Act.Ibio - Fecha del Taller menor o = 7 días"*, más *"Otros: 1° contacto - fecha lead / Fecha 1° reunión - fecha lead / Promedio de días contactos en status Esperando Familia"*.

| Sub-métrica | Hito inicial | Hito final | Umbral declarado | Fuente del dato | Estado |
|---|---|---|---|---|---|
| `tiempo_devolucion_doe` | `fecha_taller_doe` | `fecha_devolucion_doe` | **≤ 7 días** — el único umbral que las fuentes declaran | ambos campos existen | `en_revision` |
| `time_to_first_contact` | creación del lead | `fecha_1ra_comunicacion` | — | ambos existen | `en_revision` |
| `tiempo_a_primera_reunion` | creación del lead | `fecha_asistio_reunion` | — | ⚠️ el campo guarda la **última** reunión, no la primera | `con reserva metodológica` |
| `permanencia_en_esperando_familia` | entrada a `ESPERANDO_FAMILIA` | salida del estado | — | requiere `transicion_estado` | `en_revision` |

**Refinamiento que agrega E5** (verbatim, y que la lista original no contemplaba):

> *"Lead proveniente de 'form corto' (...) Primer indicador: tiempo desde la creación del lead hasta el primer contacto. También puede medirse el tiempo hasta completar la información requerida, aunque este indicador debe interpretarse con cuidado porque parte de la demora puede depender de la respuesta de la familia. Lead proveniente de 'form largo' o lead ya enriquecido (...) desde que el lead queda completo/asignable hasta el primer contacto de la Secretaría de Ingresos, y luego hasta la invitación a reunión."*

Cadena de hitos que E5 declara: `creación → primer contacto → información completa/form largo → asignación a Ingresos → contacto de Ingresos → invitación a reunión → etapas posteriores`.

**⚠️ HUECO:** de esos siete hitos, el modelo sólo tiene dato para tres (creación, primer contacto, invitación). **"Form corto vs form largo", "información completa" y "asignación a Ingresos" no existen como campo ni como estado en ninguna fuente.** Sin ellos, la mitad de los tiempos que pide E5 no se puede calcular.

- **Unidad:** días hábiles (E6) · **Estado:** `parcialmente calculable`

## 11. `pases_de_sede`

- **Fórmula (fuente):** *"Solicitudes recibidas · Pases concretados · Tiempo entre Solicitud (Lead) y Reserva"*
- **Regla de detección:** ver `06_wiki/reglas/regla-pase-de-sede.md` (G6). Se detecta por el campo `colegio_actual` cuando el colegio pertenece a la red.
- **⚠️ Techo de detectabilidad:** un lead que entra por form corto y nunca se enriquece se cuenta como ingreso nuevo. El sesgo es estructural y **no está cuantificado**.
- **⚠️ Conflicto de definición:** el estado `PASO DE SEDE` del Diccionario lo describe como *"una recomendacion de la Sec. Ingresos"*, mientras que G6 lo describe como una postulación que inicia la familia. Ver CF-08.
- **A nivel red:** un pase **no es matrícula nueva**. Cita A5: en la sede origen se registra como baja probable.
- **Estado:** `en_revision con sesgo declarado`

## 12. `ocupacion_y_vacancia`

- **Fórmula (fuente D4):** `Vacancia disponible = Cupo definido − Alumnos que ocupan/proyectan ocupar vacante`
- **Granularidad pedida:** *"% de ocupación: Por cada fila. Para cada curso y subtotal por nivel"*
- **Componentes:** ver `01_entidades/cupo_y_ocupacion.yaml`
- **Doble lectura obligatoria:** online para gestión, snapshot para análisis, *"utilizando exactamente las mismas reglas de cálculo vigentes en ese momento"*
- **Foto mensual:** *"el último día hábil del mes, a última hora"* (Requerimientos) / *"A fin de mes"* (Solicitud 5)
- **Promoción de nivel:** obligatoria (F3), con excepción manual de permanencia
- **⚠️ Conflicto F2 vs D4 vs A1** sobre qué cuenta como ocupado: ver CF-03
- **Estado:** `en_revision`

## 13. `pagaron_reserva_de_vacante`

- **Pedido (fuente):** *"Después de Grab en ABM deberíamos poder identificar quiénes pagar y firmaron CE y son efectivamente altas"*
- **⚠️ IMPOSIBLE HOY.** El dato de pago vive en Sedna. Cita A1: *"Podremos vincular esto en el momento que tengamos conexión entre el sistema de ingresos KOMMO y SEDNA"*. El estado `PAGO MATRICULA` figura en el Diccionario dentro de *"Status para Kommo que no tenemos y podrian servir"*.
- **Consecuencia:** **mientras esto no exista, el modelo no puede declarar a nadie ALUMNO**, y por lo tanto no puede calcular cartera real ni conversión hasta el alta efectiva.
- **Estado:** `bloqueada por integración`

---

## Métricas nombradas sin fórmula utilizable

| Métrica | Qué dice la fuente | Por qué no se puede fichar |
|---|---|---|
| `ofrecimos_otro_colegio_ri` | *"Consultar Lore, no se si es ofrecimos o pasaron realmente a otro colegio"* | La fuente misma no sabe qué mide |
| `recupero_solicitudes_anteriores` | Solicitud 4 + G7: *"no esta procedimentado tan especificamente"* | Depende de etiquetas no gobernadas |
| `etiqueta_de_permanencia` | G8: *"indica que ese estudiante no debe ser promocionado"* | El campo **no existe todavía** en Kommo (Solicitud 3) |
| `costo_por_lead` | D5: *"cuando se dispone del dato de inversión"* | El dato de inversión no está declarado como disponible |
| `performance_por_persona` | E4: *"Actualmente no se mide performance"* | No hay usuarios individuales (Solicitud 10) |

---

## Resumen del estado de las métricas

| Estado | Cantidad | Cuáles |
|---|---|---|
| Calculable con reservas menores | 3 | `efectividad_comercial`, `excedencia_vacancia`, `ocupacion_y_vacancia` |
| Parcialmente calculable | 2 | `tiempos_entre_status`, `pases_de_sede` |
| Bloqueada por el denominador prospectos | 1 | `calidad_de_leads` |
| Bloqueada por `dim_nivel` | 2 | `postulantes_con/sin_actividad`, `rechazados` |
| Sin fuente de datos | 3 | `leads_condicionados`, `reuniones_por_tipo`, `pagaron_reserva` |
| A definir | 1 | `desisten` |

**Ninguna métrica está certificada.** La ratificación de G1 es explícitamente "para una primera etapa" y su propio ESTADO en el Sheet quedó marcado `A DEFINIR`.
