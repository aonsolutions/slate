# Usuarios

## Obtener Todos los Usuarios

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.tedi.center/user"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
[
  {
    "email":"aaaa@aaaa.aa",
    "alias":"aaaa",
    "companies":["B13268346","B70656012"],
    "groups":["fiscal","laboral"]
  }
]
```

List all User.

### HTTP Request

`GET https://api.tedi.center/user`

### Parámetros de Búsqueda

You can use the filter query parameter to fetch User. See the table below for more information.

| Name |  Type  | Description |
|------|--------|-------------|
| email | string | Email |
| company | string | Company |
| group | string | Group |

## Obtener un Usuario Específico

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.tedi.center/user/:email"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "email":"aaaa@aaaa.aa",
  "alias":"aaaa",
  "companies":["B13268346","B70656012"],
  "groups":["fiscal","laboral"]
}
```

### HTTP Request

`GET https://api.tedi.center/user/:email`

## Crear / Actualizar un Usuario

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request POST "https://api.tedi.center/user"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "email":"aaaa@aaaa.aa",
  "alias":"aaaa",
  "companies":["B13268346","B70656012"],
  "groups":["fiscal","laboral"]
}
```

### HTTP Request

`POST https://api.tedi.center/user`

### Parámetros

| Name |  Type  | Description |
|------|--------|-------------|
| email | string | User email. |
| alias | string | User alias. |
| password | string | User password. |
| companies | [string] | Array of companies (CIF) |
| groups | [string] | Array of groups |

## Borrar un Usuario

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request DELETE "https://api.tedi.center/user/:email"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "email":"aaaa@aaaa.aa",
  "alias":"aaaa",
  "companies":["B13268346","B70656012"],
  "groups":["fiscal","laboral"]
}
```

### HTTP Request

`DELETE https://api.tedi.center/user/:email`
