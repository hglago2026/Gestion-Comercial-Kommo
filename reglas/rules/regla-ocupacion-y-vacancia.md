---
name: regla-ocupacion-y-vacancia
tipo: rule
titulo: Ocupación y vacancia
estado: en_revision
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: Dirección de Desarrollo
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - F2
  - F4
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Ocupación y vacancia

## La fórmula — **Confirmada (D4)**

> **Vacancia disponible = Cupo definido − Alumnos que ocupan/proyectan ocupar vacante**

## De dónde sale el cupo — **Confirmado (D4, F1)**

> *"La vacancia parte de un cupo bruto definido anualmente por la Dirección de Desarrollo, que determina la cantidad de secciones y cupos disponibles por sede y turno."*

El cupo **no es un dato de Kommo**. Es un dato de gobierno externo, y puede cambiar en cualquier momento si la Dirección de Desarrollo abre o cierra secciones. Por eso entra al modelo con dueño, versión y vigencia.

## Qué se descuenta — **Confirmado (D4)**

> *"Sobre ese cupo se descuentan los alumnos que ocupan o proyectan ocupar una vacante, principalmente: alumnos existentes/promocionables; ingresantes confirmados; y se consideran las novedades que liberan vacantes, como bajas inmediatas y bajas a fin de año."*

| Componente | Efecto |
|---|---|
| Alumnos existentes / promocionables | Ocupan |
| Ingresantes confirmados (desde `RESERVA PRE ICBIO`) | Ocupan |
| Bajas inmediatas | Liberan, desde la fecha efectiva |
| Bajas a fin de año | Ocupan el ciclo actual, liberan el siguiente |
| Bajas probables | **A definir** — A5 dice *"en principio"* no computar como cartera segura |

⚠️ **Conflicto CF-03:** F2 respondió sólo *"alumnos exitentes"* a la pregunta de qué cuenta como ocupado, sin mencionar a los ingresantes. D4 y A1 sí los incluyen. Falta confirmar.

## Promoción de nivel — **Confirmada (F3)**

> *"Si, exceptuando los casos que requieren permenencia en el curso actual que hoy se gestionan manualmente"*

La base oficial **debe** proyectar la promoción. La excepción son los casos de permanencia, que hoy se llevan a mano porque la etiqueta no existe en Kommo (G8, Solicitud 3).

**Consecuencia honesta:** mientras la permanencia sea manual, la ocupación proyectada tiene un error conocido y no cuantificado en cada nivel.

⚠️ **Bloqueante:** la promoción requiere un **orden de niveles**, y ninguna fuente aporta el catálogo de niveles.

## Dos lecturas, una fórmula — **Confirmado (D4)**

> *"Para la gestión operativa, la visualización debe reflejar la situación actual online. Para análisis histórico o dashboards, pueden generarse snapshots o fotos a una fecha determinada, por ejemplo al cierre de cada mes, utilizando exactamente las mismas reglas de cálculo vigentes en ese momento."*

Eso obliga a **versionar las reglas de cálculo**, no sólo los datos: un snapshot de abril tiene que poder recalcularse con las reglas de abril, no con las de hoy.

La foto se toma *"el último día hábil del mes, a última hora"* (Requerimientos · Indicadores).

## Granularidad pedida

Por sede, nivel, curso y turno — *"en el caso de los CDF´s"* (Requerimientos · Alcance). El % de ocupación se reporta *"Por cada fila. Para cada curso y subtotal por nivel"*.

## Y la matrícula real

Cita D7: *"Ninguna de las sugerencias. Está bien que estos datos no coincidan con la cartera."*

El negocio **acepta** que la ocupación reconstruida desde Kommo difiera de la cartera facturada. Eso obliga a rotular siempre de qué fuente sale cada número (CF-10).
