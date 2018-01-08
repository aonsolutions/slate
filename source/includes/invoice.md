# Factura

## Obtener Todas las Facturas


> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.aonSolutions.es/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
[
  {
    "company": "B70656012",
    "number": 42,
    "info": {

    }
  }
]
```

Este servicio permite obtener todas las facturas de una determinada empresa.

### HTTP Request

`GET https://api.aonSolutions.es/invoice/:company/`

### Path paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| company | string | NIF de la empresa a la que pertenece la factura.|

### Header parameters

| Name |  Type  | Description |
|------|--------|-------------|
| session_id | string | Identificador del sistema devuelto por el servicio de Autenticación.|

### Filter Parameters

You can use the filter query parameter to fetch User. See the table below for more information.

| Name |  Type  | Description |
|------|--------|-------------|
| reference | string | invoice reference. |
| sender | string | sender document (NIF) |
| receiver | string | receiver document (NIF) |
| date | date | from date |



## Obtener una Factura específica

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.aonSolutions.es/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "company": "B70656012",
  "number": 42,
  "info": {

  }
}
```

### HTTP Request

`GET https://api.aonSolutions.es/invoice/:company/:number`

### Path parameters

| Name |  Type  | Description |
|------|--------|-------------|
| company | string | NIF de la empresa a la que pertenece la factura. |
| number | string | Número identificativo de la factura en tEDI. |

### Header parameters

| Name |  Type  | Description |
|------|--------|-------------|
| session_id | string | Identificador del sistema devuelto por el servicio de Autenticación. |

## Crear/Actualizar una Factura

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.aonSolutions.es/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "company": "B70656012",
  "number": 42,
  "info": {

  }
}
```

Este servicio permite enviar información para crear/actualizar una factura de una determinada empresa.

### HTTP Request

`POST https://api.aonSolutions.es/invoice`

### Header parameters

| Name |  Type  | Description |
|------|--------|-------------|
| session_id | string | Identificador del sistema devuelto por el servicio de Autenticación. |

## Borrar una Factura

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.aonSolutions.es/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "company": "B70656012",
  "number": 42,
  "info": {

  }
}
```

Este servicio permite borrar una factura de una determinada empresa.

### HTTP Request

`DELETE https://api.aonSolutions.es/invoice/:company/:number`

### Path paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| company | string | NIF de la empresa a la que pertenece la factura. |
| number | string | Número identificativo de la factura en tEDI. |

### Header paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| session_id | string | Identificador del sistema devuelto por el servicio de Autenticación. |
