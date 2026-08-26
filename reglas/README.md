# reglas/

El detalle de cada definición del modelo, una página por concepto, con su fuente citada.

**Estas páginas se copian desde el repositorio del modelo semántico** (`kommo-knowledge`), que es
donde se editan y donde corre el control de calidad automático. Acá viven publicadas para que
cualquier asistente pueda leerlas sin credenciales.

## Qué traer de allá

| Carpeta origen | Qué aporta |
|---|---|
| `governance/contrato-semantico.md` | Ya está publicado acá como `CONTRATO.md`, reescrito en criollo |
| `rules/` | Las reglas transversales: sedes, duplicados, prospectos, pase de sede, ocupación, tiempos |
| `statuses/` | Una página por estado del proceso |
| `metrics/` | Una página por métrica, con numerador, denominador y exclusiones |
| `entities/glosario.md` | Los términos del negocio |

## Qué NO traer

- Nada de `sources/` que nombre rutas de archivos internos o credenciales.
- Las páginas que citan nombres y apellidos de personas del equipo, hasta decidir si se publican.
- El registro de conflictos completo: acá va sólo el resumen que le sirve a quien consulta.

## La regla de oro

**No se edita acá.** Se edita en `kommo-knowledge`, pasa el lint, y recién entonces se publica. Si
alguien corrige una página en este repositorio, el próximo refresco se la lleva puesta.
