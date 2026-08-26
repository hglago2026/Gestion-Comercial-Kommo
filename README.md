# Gestión Comercial · Red Itínere

Las reglas y los números vigentes del proceso de admisiones de la red.

**Este repositorio es público a propósito.** Contiene el modelo de negocio y métricas agregadas —
nada de datos personales. El dato crudo, con nombres y documentos de menores, vive en una carpeta
privada con acceso nominal y no se publica acá nunca.

---

## Para usarlo con una IA

Pasale a tu asistente el link a **[`INDICE.md`](INDICE.md)** y preguntale lo que necesites.

Eso es todo. No hay que copiar reglas ni pegar datos: el asistente los trae del repositorio cada vez
que empieza una conversación. **Si mañana cambia una regla o se actualizan los números, la próxima
pregunta ya toma lo nuevo, sin que hagas nada.**

## Para leerlo vos

| Archivo | Qué tiene |
|---|---|
| [`CONTRATO.md`](CONTRATO.md) | Las siete reglas de cómo se responde. En criollo |
| [`datos/metricas.json`](datos/metricas.json) | Los números vigentes, y la lista de lo que todavía no se puede responder |
| [`datos/VERSION.json`](datos/VERSION.json) | Qué versión y de qué fecha es el dato |
| [`formatos/FORMATOS.md`](formatos/FORMATOS.md) | Cómo se entrega cada informe |
| [`reglas/`](reglas/) | El detalle de cada definición, con su fuente |

## Cómo se actualiza

Los números se recalculan **cuando llega un export nuevo del CRM**, a mano por ahora. El proceso
automático diario está diseñado pero todavía no construido.

Al publicar una versión nueva:

1. se actualiza `datos/metricas.json` con los valores y se sube `version`
2. se actualiza `datos/VERSION.json` con la fecha de corte
3. se anota qué cambió y por qué

Quien lea el sistema después ve la versión nueva automáticamente. **No hay que avisarle a nadie.**

## Cómo se corrige una regla

Por pull request, nunca editando directo. Cada regla tiene un responsable, y el cambio queda con
fecha y autor. Si una regla no tiene responsable nombrado, ese es el primer problema a resolver: hoy
**ninguna regla del modelo está certificada** justamente por eso.

## Lo que este sistema NO hace

- No reemplaza al CRM: no se carga nada acá.
- No responde por alumnos, sólo hasta ingresante confirmado. El sistema de facturación no está
  conectado.
- No calcula en el momento: publica números ya calculados. Es lo que garantiza que dos personas
  distintas obtengan lo mismo.
