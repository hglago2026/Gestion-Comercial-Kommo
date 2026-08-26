# reglas/ — el detalle de cada definición

Una página por concepto, con su fuente citada y su estado de madurez.

> **Si sos una IA:** no traigas esta carpeta entera. Buscá en la tabla la página que
> corresponde a lo que te preguntaron y traé sólo esa. Estas páginas **explican** las
> definiciones; los **números** vienen de [`../datos/metricas.json`](../datos/metricas.json)
> y de ningún otro lado.

## Cómo leer el estado de cada página

| Estado | Qué significa |
|---|---|
| **certificado** | Tiene responsable y aprobador nombrados. Se puede usar para decidir |
| **en revisión** | La definición está escrita pero le falta ratificación |
| **borrador** | Es una transcripción o una medición, no una definición ratificada |

Hoy **casi todo está en borrador**, y eso no es un descuido: es el estado real del
modelo mientras no haya un aprobador nombrado por ámbito. Está explicado en
[`../CONTRATO.md`](../CONTRATO.md).

---

## Reglas transversales

Cómo se cuenta cada cosa: sedes, duplicados, prospectos, ocupación, tiempos, pases.

| Página | Tema | Estado |
|---|---|---|
| [`regla-canonicalizacion-estados`](rules/regla-canonicalizacion-estados.md) | Canonicalización de estados (negocio vs CRM) | borrador |
| [`regla-ciclo-lectivo`](rules/regla-ciclo-lectivo.md) | Ciclo lectivo y convivencia de ciclos | en revisión |
| [`regla-cierre-positivo`](rules/regla-cierre-positivo.md) | Qué cuenta como cierre positivo | borrador |
| [`regla-conciliacion-estados`](rules/regla-conciliacion-estados.md) | Conciliación de los dos catálogos de estados | en revisión |
| [`regla-duplicados`](rules/regla-duplicados.md) | Qué es un duplicado y qué no | borrador |
| [`regla-fecha-de-corte`](rules/regla-fecha-de-corte.md) | Fecha de corte, cierre al 31-3 y archivo mensual | en revisión |
| [`regla-grano`](rules/regla-grano.md) | El grano del modelo | borrador |
| [`regla-landing-zone-raw`](rules/regla-landing-zone-raw.md) | Dónde vive el dato crudo (landing zone del RAW) | en revisión |
| [`regla-ocupacion-y-vacancia`](rules/regla-ocupacion-y-vacancia.md) | Ocupación y vacancia | en revisión |
| [`regla-pase-de-sede`](rules/regla-pase-de-sede.md) | Pase de sede: cómo entra y cuándo se detecta | en revisión |
| [`regla-pipelines-en-alcance`](rules/regla-pipelines-en-alcance.md) | Qué pipelines entran en el análisis | en revisión |
| [`regla-promocion-de-niveles`](rules/regla-promocion-de-niveles.md) | Promoción de niveles para proyectar ocupación | borrador |
| [`regla-prospecto`](rules/regla-prospecto.md) | Qué cuenta como prospecto | borrador |
| [`regla-sedes`](rules/regla-sedes.md) | Las seis sedes y la separación de CDF Puertos | certificado |
| [`regla-tiempos`](rules/regla-tiempos.md) | Cómo se miden los tiempos del proceso | en revisión |

## Estados del proceso

Una página por estado del embudo, con de dónde entra y hacia dónde sale.

| Página | Tema | Estado |
|---|---|---|
| [`avanzan`](statuses/avanzan.md) | Avanzan | borrador |
| [`baja`](statuses/baja.md) | Baja | borrador |
| [`contactos-leads`](statuses/contactos-leads.md) | Contactos / Leads | borrador |
| [`desiste`](statuses/desiste.md) | Desiste | borrador |
| [`desisten-en-contacto-inicial`](statuses/desisten-en-contacto-inicial.md) | Desisten en contacto inicial | borrador |
| [`documentacion`](statuses/documentacion.md) | Documentación | borrador |
| [`duplicados`](statuses/duplicados.md) | Duplicados | borrador |
| [`en-curso`](statuses/en-curso.md) | En curso | borrador |
| [`esperando-familia`](statuses/esperando-familia.md) | Esperando familia | borrador |
| [`esperando-vacante-hno`](statuses/esperando-vacante-hno.md) | Esperando vacante (hermano) | borrador |
| [`filtro-semaforo`](statuses/filtro-semaforo.md) | Filtro Semáforo | borrador |
| [`grabado-abm`](statuses/grabado-abm.md) | Grabado en ABM | borrador |
| [`historico`](statuses/historico.md) | Histórico | borrador |
| [`icbio-ok`](statuses/icbio-ok.md) | ICBIO OK | borrador |
| [`incontactables`](statuses/incontactables.md) | Incontactables | borrador |
| [`inscripto`](statuses/inscripto.md) | Inscripto | borrador |
| [`intercambio-ok`](statuses/intercambio-ok.md) | Intercambio OK | borrador |
| [`invitados-a-reunion`](statuses/invitados-a-reunion.md) | Invitados a reunión | borrador |
| [`legajo`](statuses/legajo.md) | Legajo del estudiante | borrador |
| [`lista-de-espera`](statuses/lista-de-espera.md) | Lista de espera | borrador |
| [`nuevo`](statuses/nuevo.md) | Nuevo (Kommo) | borrador |
| [`pago-reserva`](statuses/pago-reserva.md) | Pago de reserva | borrador |
| [`paso-de-sede`](statuses/paso-de-sede.md) | Paso de sede | borrador |
| [`postulante`](statuses/postulante.md) | Postulante (Kommo) | borrador |
| [`prospectos`](statuses/prospectos.md) | Prospectos | borrador |
| [`rechazado`](statuses/rechazado.md) | Rechazado | borrador |
| [`reserva-pre-icbio`](statuses/reserva-pre-icbio.md) | Reserva pre-ICBIO | borrador |
| [`reunion-presentacion`](statuses/reunion-presentacion.md) | Reunión de presentación | borrador |
| [`taller-intercambio`](statuses/taller-intercambio.md) | Taller de intercambio | borrador |

## Métricas

Una página por métrica, con numerador, denominador y exclusiones.

| Página | Tema | Estado |
|---|---|---|
| [`calidad-de-leads`](metrics/calidad-de-leads.md) | Calidad de Leads | borrador |
| [`conversion-a-cierre-positivo`](metrics/conversion-a-cierre-positivo.md) | Conversión a cierre positivo | borrador |
| [`desisten`](metrics/desisten.md) | Desisten | borrador |
| [`efectividad-comercial`](metrics/efectividad-comercial.md) | Efectividad Comercial | borrador |
| [`efectividad-convocatoria`](metrics/efectividad-convocatoria.md) | Efectividad de Convocatoria | borrador |
| [`excedencia-de-vacancia`](metrics/excedencia-de-vacancia.md) | Excedencia de vacancia | borrador |
| [`leads-condicionados`](metrics/leads-condicionados.md) | Leads Condicionados | borrador |
| [`ocupacion-por-curso-y-nivel`](metrics/ocupacion-por-curso-y-nivel.md) | % de ocupación por curso y nivel | borrador |
| [`pases-de-sede`](metrics/pases-de-sede.md) | Pases de sede | borrador |
| [`postulantes-actividad-intercambio`](metrics/postulantes-actividad-intercambio.md) | Postulantes con y sin actividad de intercambio | borrador |
| [`rechazados`](metrics/rechazados.md) | Rechazados | borrador |
| [`reuniones-por-tipo`](metrics/reuniones-por-tipo.md) | Reuniones por tipo | borrador |
| [`tiempos-entre-status`](metrics/tiempos-entre-status.md) | Tiempos entre status | borrador |
| [`time-to-lead`](metrics/time-to-lead.md) | Time to Lead / permanencia por estado | borrador |

## Entidades y glosario

Qué es un alumno, una postulación, una familia, un cupo. Y el glosario del negocio.

| Página | Tema | Estado |
|---|---|---|
| [`alumno`](entities/alumno.md) | Alumno | borrador |
| [`ciclo-lectivo`](entities/ciclo-lectivo.md) | Ciclo lectivo | borrador |
| [`colegio-sede`](entities/colegio-sede.md) | Colegio / Sede | en revisión |
| [`cupo`](entities/cupo.md) | Cupo | borrador |
| [`curso-seccion-turno`](entities/curso-seccion-turno.md) | Curso, sección y turno | borrador |
| [`evento-de-lead`](entities/evento-de-lead.md) | Evento de lead | borrador |
| [`familia`](entities/familia.md) | Familia | borrador |
| [`glosario`](entities/glosario.md) | Glosario del modelo de admisiones | en revisión |
| [`lead`](entities/lead.md) | Lead (Kommo) | borrador |
| [`nivel`](entities/nivel.md) | Nivel | en revisión |
| [`persona`](entities/persona.md) | Persona | borrador |
| [`postulacion`](entities/postulacion.md) | Postulación | borrador |

## Procesos

El recorrido completo de una admisión, el pase de sede y el reingreso.

| Página | Tema | Estado |
|---|---|---|
| [`proceso-admision`](processes/proceso-admision.md) | Proceso de admisión (embudo completo) | en revisión |
| [`proceso-archivo-mensual`](processes/proceso-archivo-mensual.md) | Archivo mensual del status | borrador |
| [`proceso-ingesta-raw`](processes/proceso-ingesta-raw.md) | Ingesta: del RAW a la Capa 1 | borrador |
| [`proceso-pase-de-sede`](processes/proceso-pase-de-sede.md) | Pase de sede | borrador |
| [`proceso-reingreso-repostulacion`](processes/proceso-reingreso-repostulacion.md) | Reingreso y repostulación | borrador |

## Preguntas de control

Las preguntas con las que se verifica que el modelo responde bien.

| Página | Tema | Estado |
|---|---|---|
| [`gq-cuantos-inscriptos`](golden_questions/gq-cuantos-inscriptos.md) | ¿Cuántos inscriptos tenemos? | borrador |
| [`gq-efectividad-comercial-por-sede`](golden_questions/gq-efectividad-comercial-por-sede.md) | ¿Cuál es la efectividad comercial de cada sede este ciclo? | borrador |
| [`gq-hermanos-sin-cupo`](golden_questions/gq-hermanos-sin-cupo.md) | ¿Cuántas familias de la comunidad quedaron sin cupo este ciclo? | borrador |
| [`gq-ocupacion-por-nivel`](golden_questions/gq-ocupacion-por-nivel.md) | ¿Qué niveles van a quedar sin cupo el ciclo que viene? | borrador |
| [`gq-taller-devolucion-7-dias`](golden_questions/gq-taller-devolucion-7-dias.md) | ¿Qué proporción de las devoluciones del taller salió dentro de los 7 días? | borrador |

## Fuentes de dato

De dónde sale cada cosa y qué tan confiable es.

| Página | Tema | Estado |
|---|---|---|
| [`abm-sedna-hosking-handing`](sources/abm-sedna-hosking-handing.md) | ABM académico — Sedna / Hosking / Handing | borrador |
| [`app-doe`](sources/app-doe.md) | App del DOE | borrador |
| [`cupos-y-secciones`](sources/cupos-y-secciones.md) | Cupos y secciones por sede | borrador |
| [`kommo-api`](sources/kommo-api.md) | Kommo — API | borrador |
| [`kommo-export-eventos`](sources/kommo-export-eventos.md) | Kommo — export del log de eventos | borrador |
| [`reporte-neva`](sources/reporte-neva.md) | Reporte de Kommo desarrollado por NE+VA | borrador |
| [`sheet-a-nfs-reportes`](sources/sheet-a-nfs-reportes.md) | Google Sheet "A - NFSs reportes" | borrador |
| [`sheet-requerimientos-ingresos`](sources/sheet-requerimientos-ingresos.md) | Sheet — Requerimientos Tablero Ingresos (fuente de definiciones) | en revisión |
| [`visualizacion-vacancia`](sources/visualizacion-vacancia.md) | Visualización de Vacancia | borrador |

## Estado del modelo

Qué está definido, qué falta y de quién depende. Y el criterio con datos de menores.

| Página | Tema | Estado |
|---|---|---|
| [`datos-sensibles-menores`](governance/datos-sensibles-menores.md) | Datos sensibles y menores de edad | en revisión |
| [`estado-de-las-metricas`](governance/estado-de-las-metricas.md) | Fichas de métricas v1 y su estado real | en revisión |
| [`registro-faltantes`](governance/registro-faltantes.md) | Registro de faltantes | en revisión |

---

**92 páginas.** Se publican desde el repositorio del modelo semántico, que es donde
se editan y donde corre el control de calidad automático. Acá viven publicadas para que
cualquier asistente pueda leerlas sin credenciales.

**Lo que no está acá:** las rutas de archivos internos, los enlaces a documentos con
acceso nominal, y cualquier dato personal de las familias. Eso se filtra antes de publicar.
