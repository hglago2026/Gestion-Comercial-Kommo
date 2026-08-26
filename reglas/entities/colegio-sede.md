---
name: colegio-sede
tipo: entity
titulo: Colegio / Sede
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - sede
  - colegio
grano: una sede
clave_natural: nombre de sede
fuentes:
  - kommo-export-eventos
reglas:
  - regla-sedes
  - regla-pipelines-en-alcance
bloqueantes:
  - D8
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Colegio / Sede

**Confirmado: son 6 sedes**, y **CDF Puertos va separada** de las otras dos de CDF.

| Sede | Institución | Pipeline en Kommo |
|---|---|---|
| NFS Puertos | Northfield | NFS Puertos y Nordelta |
| NFS Nordelta | Northfield | NFS Puertos y Nordelta |
| CDF Escobar | CDF | CDF Benavidez y Escobar |
| CDF Benavidez | CDF | CDF Benavidez y Escobar |
| CDF Puertos | CDF | CDF Puertos |
| LTH Hudson | Lighthouse | LTH Hudson |

**Ojo con el desfasaje:** en Kommo los pipelines agrupan sedes (NFS Puertos y Nordelta
comparten pipeline). La sede individual **no siempre se puede derivar del pipeline**.
**A DEFINIR (D8):** de qué campo sale la sede cuando el pipeline agrupa dos.

Ver [regla-sedes](../rules/regla-sedes.md) y [regla-pipelines-en-alcance](../rules/regla-pipelines-en-alcance.md).
