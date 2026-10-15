# API de Pagos — Referencia

> ✏️ Editado en GitHub: se corrigió la concordancia en `GET /v1/pagos`.

Referencia de `pagos-api v0.3.0 (Express + Zod). URL base: http://localhost:3000 (puerto configurable con PORT). Todas las solicitudes y respuestas usan JSON.`

## Endpoints

| Método | Ruta                    | Descripción                                                |
| ------ | ----------------------- | ---------------------------------------------------------- |
| POST   | `/v1/hitos`             | Crea un hito con presupuesto dentro de un proyecto         |
| POST   | `/v1/hitos/:id/aprobar` | El cliente aprueba la entrega y se libera el pago del hito |
| GET    | `/v1/pagos`             | Lista los pagos de un proyecto                             |

***

## POST /v1/hitos

Crea un hito. El cuerpo se valida con Zod; si no es válido, la solicitud falla.

**Parámetros (cuerpo)**

| Campo            | Tipo   | Regla                            |
| ---------------- | ------ | -------------------------------- |
| `proyectoId`     | string | Obligatorio                      |
| `titulo`         | string | Obligatorio, mínimo 3 caracteres |
| `presupuestoUsd` | number | Obligatorio, mayor que 0         |
| `fechaEntrega`   | string | Obligatorio, fecha `AAAA-MM-DD`  |

**Ejemplo**

```shellscript
curl -X POST http://localhost:3000/v1/hitos \
  -H "Content-Type: application/json" \
  -d '{"proyectoId":"proy_123","titulo":"Diseño de la landing","presupuestoUsd":500,"fechaEntrega":"2026-11-30"}'
```

**Respuesta \`201\`**

```json
{ "id": "3f0c…", "estado": "pendiente", "proyectoId": "proy_123", "titulo": "Diseño de la landing", "presupuestoUsd": 500, "fechaEntrega": "2026-11-30" }
```

***

## POST /v1/hitos/:id/aprobar

El cliente aprueba la entrega del hito, lo que libera su pago.

**Parámetros (ruta)**

| Campo | Tipo   | Regla       |
| ----- | ------ | ----------- |
| `id`  | string | ID del hito |

**Ejemplo**

```shellscript
curl -X POST http://localhost:3000/v1/hitos/3f0c…/aprobar
```

**Respuesta \`200\`**

```json
{ "id": "3f0c…", "estado": "aprobado", "pago": "liberado" }
```

***

## GET /v1/pagos

Lista los pagos de un proyecto.

**Parámetros (query)**

| Campo        | Tipo   | Regla                                                            |
| ------------ | ------ | ---------------------------------------------------------------- |
| `proyectoId` | string | ID del proyecto                                                  |
| `estado`     | string | Opcional: `pendiente o liberado. Si se omite, se devuelven todos` |

**Ejemplo**

```shellscript
curl "http://localhost:3000/v1/pagos?proyectoId=proy_123&estado=liberado"
```

**Respuesta \`200\`**

```json
{ "proyectoId": "proy_123", "estado": "liberado", "items": [] }
```

***

## Regla de comisión

La comisión del desarrollador es el **4 % del monto del hito, redondeado a 2 decimales (**`comision() en src/routes/pagos.js).`

`comision = round(montoUsd × 0.04, 2)`

Ejemplo: un hito de 500 USD genera una comisión de **20.00 USD.**

***

## Notas sobre el estado actual

* Los endpoints devuelven datos de ejemplo: no hay persistencia y `GET /v1/pagos siempre devuelve items: [].`
* `comision() está definida y exportada, pero ningún endpoint la aplica todavía.`
* `proyectoId en GET /v1/pagos no se valida.`
* `POST /v1/hitos/:id/aprobar no comprueba que el hito exista.`
