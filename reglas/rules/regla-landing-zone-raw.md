---
name: regla-landing-zone-raw
tipo: rule
titulo: Dónde vive el dato crudo (landing zone del RAW)
estado: en_revision
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
alcance: todas las fuentes de dato del piloto
afecta_a:
  - kommo-export-eventos
  - kommo-api
  - abm-sedna-hosking-handing
  - app-doe
  - cupos-y-secciones
  - sheet-a-nfs-reportes
  - proceso-ingesta-raw
bloqueantes:
  - I1
  - J1
  - J3
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# Dónde vive el dato crudo (landing zone del RAW)

## Enunciado

**El repositorio de conocimiento no aloja dato.** Los archivos crudos aterrizan en una
**landing zone** separada, inmutable, con nomenclatura fija y una ficha por archivo.

```
carpeta-privada/raw/
├── README.md                     ← la convención, en el lugar donde se usa
├── kommo/
│   └── eventos/
│       └── 2026/
│           ├── kommo__eventos__20260804.xlsx
│           └── kommo__eventos__20260804.meta.md
├── abm/
├── doe/
├── cupos/
├── sheets/
└── _cuarentena/                  ← llegó sin ficha o sin origen claro
```

## Las cinco reglas

**1 · Nomenclatura fija**

```
<fuente>__<dataset>__<AAAAMMDD>[_HHMM].<ext>
```

`<fuente>` es **el mismo `name` que la página de `/sources`** (`kommo`, `abm`, `doe`…).
La fecha es la de **extracción**, no la del contenido ni la de descarga.

**2 · Toda extracción trae ficha**

Junto a cada archivo va un `.meta.md` con: fuente, quién y cómo la extrajo, fecha y hora,
cantidad de filas, cobertura temporal del contenido, hash `sha256` y destino en la Capa 1.
Un archivo sin ficha va a `_cuarentena/` y no se ingesta.

El hash no es burocracia: es lo que permite decir *"el número de marzo salió de este archivo
exacto"* seis meses después.

**3 · Inmutable**

Un archivo que aterrizó **no se edita, no se renombra y no se pisa**. Si hubo un error en la
extracción, se hace una nueva con fecha nueva y se anota en la ficha vieja qué la reemplaza.
Corregir el RAW en el lugar destruye la única copia del pasado.

**4 · Nunca dentro del repo de conocimiento**

El `.gitignore` bloquea `*.xlsx`, `*.csv`, `raw/` y `kommo_all_events*`. No se desactiva.
Motivo doble: la regla *el Markdown explica, el Modelo Semántico ejecuta*, y el hecho
concreto de que el export de eventos pesa 74 MB.

**5 · El RAW se lee, no se consulta**

Nadie construye un reporte leyendo la landing zone. Se ingesta a la Capa 1 y se consulta
ahí. Ver [proceso-ingesta-raw](../processes/proceso-ingesta-raw.md).

## Por qué existe

Sin RAW conservado, si una regla cambia dentro de seis meses no se puede recalcular el
pasado: **el error queda congelado para siempre**. Y el requerimiento del equipo de
*archivar el status al cierre de cada mes* depende enteramente de esta capa.

## Advertencias sobre la ubicación actual

**Sugerencia (no es decisión tomada).** Hoy la landing zone queda dentro de
`la carpeta sincronizada de Drive`, que es Google Drive. Eso sirve para arrancar, pero conviene saber tres
cosas:

- **Drive sincroniza, no versiona.** Si alguien pisa un archivo, se pisa en todas las
  máquinas. La regla 3 (inmutabilidad) es la única protección real y depende de disciplina.
- **El destino natural de la landing zone es donde el motor de la Capa 1 pueda leerla**
  (un blob storage, un bucket, un share montado). Mudarla es parte de **A DEFINIR (I1)**.
- **Datos personales de menores** en una carpeta de Drive personal: antes de sumar el ABM o
  la [app-doe](../sources/app-doe.md) hay que resolver [datos-sensibles-menores](../governance/datos-sensibles-menores.md) y **A DEFINIR (J1, J3)**.

## Qué se rompe si esta regla cambia

Todas las páginas de `/sources`, [proceso-ingesta-raw](../processes/proceso-ingesta-raw.md) y el `.gitignore` del repo.
