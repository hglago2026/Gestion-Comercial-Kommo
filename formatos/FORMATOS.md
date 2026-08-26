# Formatos de salida

**Antes de producir cualquier informe, preguntale a la persona cómo lo quiere.** No lo asumas: un
número para chequear algo rápido y un documento para llevar a una reunión de directorio no son lo
mismo, y producir el segundo cuando pedían el primero hace perder tiempo.

La pregunta, tal cual:

> ¿Cómo lo querés? Puedo darte la respuesta acá en el chat, o armarte un documento de Word, un PDF,
> una página web o una planilla.

---

## Las cinco formas

| Formato | Cuándo | Qué sale |
|---|---|---|
| **En el chat** | Es lo más pedido y el que conviene por defecto para una pregunta puntual | El encabezado, el número, y de dónde sale. Nada más |
| **Word** | Va a circular, alguien lo va a comentar o editar | Documento con encabezado, cuerpo y pie de trazabilidad |
| **PDF** | Se presenta y no se edita: directorio, acta, adjunto formal | Igual que Word, cerrado |
| **Página web** | Tiene varias vistas, se consulta más de una vez, o se comparte por link | HTML autocontenido, con tabla además de los gráficos |
| **Planilla** | La persona va a seguir trabajando sobre los números | Una fila por registro, sin celdas combinadas, con las etiquetas en una columna |

---

## El encabezado obligatorio

**Los cinco formatos empiezan igual.** Sin excepción, ni siquiera la respuesta corta en el chat.

```
[ETIQUETA]  ·  Métrica: <nombre canónico>
Fecha de corte del dato: <AAAA-MM-DD>   ·   Métricas versión <n>
Universo: <sobre qué se calcula, y qué queda afuera>
```

Ejemplo real:

```
[INTERPRETACIÓN]  ·  Métrica: ocupación y vacancia 2027
Fecha de corte del dato: 2026-08-04   ·   Métricas versión 1
Universo: 5 sedes. LTH Hudson excluida porque sus números no cierran contra su cupo.
```

*Por qué es obligatorio:* dos informes del mismo dato tienen que poder compararse sin leerlos
enteros. Si uno dice «ocupación 83,6 %» y otro dice «81,2 %», el encabezado resuelve en dos segundos
si es un error o si son cortes distintos.

## El pie obligatorio

Al final de todo informe, en cualquier formato:

```
Fuente: Gestión Comercial · Red Itínere, métricas v<n> del <fecha>.
Fórmula: <la fórmula usada, textual>
Este número lo <calcula el modelo | reporta desde una planilla externa>.
<Si hubo instrucción supletoria: quién la dio y cuándo.>
```

---

## Reglas que valen para todos los formatos

**Los números se muestran como están publicados.** No se redondean, no se convierten a porcentaje si
vienen en cantidad, no se cambia la unidad. Si en el archivo dice `93.5`, en el informe dice 93,5 %.

**Lo que falta se muestra, no se esconde.** Si una sede quedó afuera, aparece igual, con el motivo.
Una fila ausente se lee como cero, y no es lo mismo.

**Nunca se rellena una serie.** Si falta un mes, falta. No se interpola.

**Los gráficos no reemplazan a la tabla.** En página web y en documento, todo gráfico va acompañado
de los números en tabla.

**Una sola idea por informe.** Si la pregunta tiene tres partes, se pregunta si quieren tres
informes o uno solo; no se apilan tres cosas distintas bajo un mismo título.
