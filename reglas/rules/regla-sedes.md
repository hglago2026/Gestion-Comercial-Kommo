---
name: regla-sedes
tipo: rule
titulo: Las seis sedes y la separación de CDF Puertos
estado: certificado
version: 0.1
owner_doc: Horacio
owner_negocio: Equipo de Ingresos
aprobador: Horacio
actualizado: 2026-08-20
alcance: dimensión sede
afecta_a:
  - colegio-sede
bloqueantes: []
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Las seis sedes y la separación de CDF Puertos

## Enunciado

**Confirmado y ya aplicado en el prototipo v11:** el análisis se corta por **6 sedes**, y
**CDF Puertos se reporta separada** de CDF Benavidez y CDF Escobar.

NFS Puertos · NFS Nordelta · CDF Escobar · CDF Benavidez · **CDF Puertos** · LTH Hudson

## Por qué

CDF Puertos tiene pipeline propio en Kommo y un comportamiento distinto del resto de CDF
—es la sede con mejor conversión medida (27,3%)—. Agruparla con las otras dos esconde tanto
su desempeño como el de ellas.

## Ojo con derivar la sede del pipeline

Los pipelines de Kommo **agrupan** sedes: `NFS Puertos y Nordelta` contiene dos. Cómo se
resuelve la sede individual cuando el pipeline agrupa es una decisión abierta que se trata
en [colegio-sede](../entities/colegio-sede.md) — esta regla fija cuáles son las seis sedes y que CDF Puertos va
separada, no de qué campo se extraen.
