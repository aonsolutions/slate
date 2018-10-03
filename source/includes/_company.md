# Empresas

## Obtener Todas las Empresas

> Ejemplo de llamada al servicio “Obtener Todas las Empresas”:

```shell
curl --request GET "https://api.tedi.center/company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
[
  {
    "document":"B99999999",
    "name":"ANONIMO SL",
    "address":"Calle mayor 10",
  }
]
```

Obtener todas las empresas a los que el usuario (token) que hace la petición tenga acceso.

### HTTP Request

`GET https://api.tedi.center/company`

## Obtener un Usuario Específico

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.tedi.center/company/:document"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "document":"B99999999",
  "name":"ANONIMO SL",
  "address":"Calle mayor 10",
}
```

### HTTP Request

`GET https://api.tedi.center/company/:document`

### Path paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| document | string | CIF de la empresa.|


## Crear / Actualizar un Usuario

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request POST "https://api.tedi.center/company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "document":"B99999999",
  "name":"ANONIMO SL",
  "address":"Calle mayor 10",
}
```

### HTTP Request

`POST https://api.tedi.center/company`

### Parámetros

| Name |  Type  | Description |
|------|--------|-------------|
| document | string | CIF de la empresa. |
| name | string | Nombre o Razón Social. |
| address | string | Dirección postal de la empresa. |

## Borrar un Empresa

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request DELETE "https://api.tedi.center/company/:document"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "document":"B99999999",
  "name":"ANONIMO SL",
  "address":"Calle mayor 10",
}
```

### HTTP Request

`DELETE https://api.tedi.center/user/:email`

### Path paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| document | string | CIF de la empresa.|
