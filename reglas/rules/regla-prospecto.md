---
name: regla-prospecto
tipo: rule
titulo: Qué cuenta como prospecto
estado: borrador
version: 0.1
owner_doc: Horacio (PDEP)
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-21
bloqueantes:
  - G2
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Prospecto

## Por qué esta página está en borrador

Prospecto es el denominador de casi todas las mediciones de eficiencia — y hoy tiene **tres definiciones incompatibles**. Mientras eso siga así, ninguna métrica de eficiencia es reproducible.

## Las tres definiciones

**1 · Diccionario Status, columna `regala`:**
> *"Prospectos = LEADS que esta en cualquier estado menos DUPLICADO - CONTACTO POR ERROR - PASO DE SEDE que es un lead para otra sede"*

**2 · Requerimientos Tablero Ingresos, hoja Proceso:**
> *"Son los leads reales (restados los grupos anteriores a Contactos) base para todas las mediciones de eficiencia. Son los leads ya procesados con información completa que se derivan a la Secretaría de Ingresos"*

Los "grupos anteriores" en esa hoja son: duplicados, incontactables, desisten en contacto inicial y filtro semáforo.

**3 · Cuestionario G2:** la respuesta es literalmente **"ok"** a una sugerencia que decía dejar el Filtro Semáforo **dentro** de prospectos y sacar sólo *"lo que es error de dato: duplicados, incontactables, proveedores y CVs"*.

## Dónde chocan

| | Def. 1 | Def. 2 | Def. 3 |
|---|---|---|---|
| Duplicados | fuera | fuera | fuera |
| Contactó por error | fuera | — | fuera ("error de dato") |
| Paso de sede | **fuera** | — | — |
| Incontactables | — | **fuera** | **fuera** |
| Desisten en contacto inicial | — | **fuera** | — |
| Filtro semáforo | — | **fuera** | **adentro** |
| Proveedores y CVs | — | — | fuera *(no existen como estado)* |
| En curso / bajas | adentro | — | — |

Además, la definición 2 agrega una condición que las otras no tienen: *"con información completa que se derivan a la Secretaría de Ingresos"*. Eso es un **estado del proceso**, no una exclusión — y en el catálogo de Kommo se parece a `POSTULANTE`, no a un universo depurado.

## Qué hace falta para cerrarlo

Una lista, por **código de estado**, de qué se resta de CONTACTOS/LEADS. Responsable: Sec. Ingresos.

Preguntas concretas a responder:

1. ¿El Filtro Semáforo entra o sale? (G2 dice adentro, Requerimientos dice afuera)
2. ¿`PASO DE SEDE` se resta siempre?
3. ¿"Proveedores" y "CVs" tienen algún estado en Kommo, o son parte de "Contactó por error"?
4. ¿`EN CURSO`, las bajas y los estados post-ABM cuentan como prospecto? Evidentemente no, pero ninguna definición los excluye.
5. ¿Prospecto es un universo depurado (definiciones 1 y 3) o una etapa del proceso (definición 2)? **No pueden ser las dos cosas.**

## Mientras tanto

Cualquier métrica que use prospectos como denominador sale rotulada como **hipótesis**, declarando cuál de las tres definiciones se usó.
