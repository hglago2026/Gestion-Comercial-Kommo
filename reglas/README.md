# reglas/

El detalle de cada definición del modelo, una página por concepto, con su fuente citada.

**→ El catálogo completo está en [`INDICE.md`](INDICE.md).** 92 páginas, agrupadas por tema,
cada una con su estado de madurez.

---

## Qué hay acá y qué no

Estas páginas **explican** las definiciones: qué cuenta como prospecto, qué es un pase de sede,
cómo se mide la ocupación, de dónde sale cada dato y qué tan confiable es.

**Los números no están acá.** Viven en [`../datos/metricas.json`](../datos/metricas.json), ya
calculados. Es la regla que hace que dos personas con dos asistentes distintos obtengan lo
mismo — está explicada en [`../CONTRATO.md`](../CONTRATO.md).

## De dónde salen estas páginas

Se publican desde el repositorio del modelo semántico, que es donde se editan y donde corre el
control de calidad automático.

**Acá no se edita.** Se corrige allá, pasa el lint, y recién entonces se publica. Si alguien
corrige una página en este repositorio, el próximo refresco se la lleva puesta.

## Qué se filtra antes de publicar

Cada refresco pasa por un filtro que saca:

- **rutas de archivos internos** — se reemplazan por una referencia genérica
- **enlaces a documentos con acceso nominal** — Sheets y carpetas de Drive del equipo
- **credenciales de cualquier tipo**
- **datos personales de las familias** — no llegan hasta acá por diseño: el dato crudo, con
  nombres y documentos de menores, vive en una carpeta privada y nunca entra a este repositorio

Los nombres de **roles y áreas** sí se publican (Secretaría de Ingresos, Equipos Directivos,
DOE): son parte de cómo funciona el proceso. Los nombres de **personas** sólo aparecen como
responsable o aprobador de una definición, que es justamente lo que el contrato pide que quede
asentado.
