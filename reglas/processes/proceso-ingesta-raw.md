---
name: proceso-ingesta-raw
tipo: process
titulo: Ingesta: del RAW a la Capa 1
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema_soporte: A DEFINIR (I1)
entidades:
  - evento-de-lead
estados: []
metricas: []
bloqueantes:
  - I1
  - I2
  - D6
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Ingesta: del RAW a la Capa 1

## Secuencia

1. **Extracción** — se obtiene el archivo del origen.
2. **Aterrizaje** — se deposita en la landing zone con nomenclatura y ficha, según
   [regla-landing-zone-raw](../rules/regla-landing-zone-raw.md).
3. **Validación** — cantidad de filas, cobertura temporal, hash. Si no hay ficha, va a
   `_cuarentena/`.
4. **Carga a RAW** — copia fiel, sin transformar, conservando el valor original.
5. **Transformación a la Capa 1** — canonicalización de estados
   ([regla-canonicalizacion-estados](../rules/regla-canonicalizacion-estados.md)), resolución de dimensiones, `lineage` a la fila de
   origen.
6. **Bitácora** — se anota en `log.md` qué se ingestó, de qué archivo y con qué resultado.

## Lo que hoy no existe

Los pasos 1 a 6 se hacen **a mano y una sola vez**. Convertir esto en un proceso corrido es
la Fase 3–4 del piloto.

## Decisiones abiertas

- **A DEFINIR (I1)** — motor de la base.
- **A DEFINIR (I2)** — quién opera y monitorea la carga.
- **A DEFINIR (D6)** — frecuencia.
