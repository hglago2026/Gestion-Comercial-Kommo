---
name: nivel
tipo: entity
titulo: Nivel
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
define:
  - nivel
grano: un nivel de la escalera académica
clave_natural: nombre del nivel
reglas:
  - regla-promocion-de-niveles
bloqueantes: []
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Nivel

**Confirmado: 17 niveles en escalera**, de `Sala 1` a `6.º Año` y luego `Egresado`.

La escalera importa porque la ocupación futura no se calcula sobre el nivel actual: los
alumnos **promocionan**. Proyectar vacancia sin promoción da un resultado sistemáticamente
equivocado. Ver [regla-promocion-de-niveles](../rules/regla-promocion-de-niveles.md) y [ocupacion-por-curso-y-nivel](../metrics/ocupacion-por-curso-y-nivel.md).

**Confirmado (regla de negocio del embudo):** el nivel bifurca el proceso — **K1–K2** van
directo a [intercambio-ok](../statuses/intercambio-ok.md), **K3 en adelante** pasan por [taller-intercambio](../statuses/taller-intercambio.md). Ver
[postulantes-actividad-intercambio](../metrics/postulantes-actividad-intercambio.md).
