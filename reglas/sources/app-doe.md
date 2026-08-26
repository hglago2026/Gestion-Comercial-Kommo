---
name: app-doe
tipo: source
titulo: App del DOE
estado: borrador
version: 0.1
owner_doc: A DEFINIR
owner_negocio: A DEFINIR
aprobador: A DEFINIR
actualizado: 2026-08-20
sistema: App del DOE
grano: A DEFINIR (D3)
metodo_extraccion: A DEFINIR (D3)
frecuencia: A DEFINIR (D3)
bloqueantes:
  - D3
  - J2
reglas:
  - regla-landing-zone-raw
---

> *Página publicada desde el modelo semántico. **Acá no se edita**: se corrige en el
> repositorio del modelo, pasa el control de calidad y recién entonces se publica.*

# App del DOE

Herramienta del Departamento de Orientación Educativa. **Confirmado** por
[sheet-requerimientos-ingresos](sheet-requerimientos-ingresos.md): el DOE interviene en el embudo leyendo las encuestas
después de la reunión de presentación, y de ahí sale la bifurcación entre
[intercambio-ok](../statuses/intercambio-ok.md) (K1–K2) y [taller-intercambio](../statuses/taller-intercambio.md) (K3 en adelante).

## Lo que no sabemos

- **A DEFINIR (D3):** qué guarda exactamente la app, con qué grano y si es extraíble.
- **A DEFINIR (D3):** si la decisión del DOE vuelve a Kommo como cambio de estado o queda
  solo en la app.
- **A DEFINIR (J2):** contiene material sensible sobre menores. Antes de ingestarlo hay que
  definir qué se puede traer y qué no. Ver [datos-sensibles-menores](../governance/datos-sensibles-menores.md).

**Sugerencia (no es decisión tomada):** que la Capa 1 ingeste de esta fuente **solo el
resultado** (apto / requiere taller / fecha), nunca el contenido de la encuesta.

## Decisiones abiertas

- **A DEFINIR (D3)** — contenido, grano y extracción.
- **A DEFINIR (J2)** — qué está permitido traer.
