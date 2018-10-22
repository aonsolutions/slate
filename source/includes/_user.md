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
    "name":"aaaa",
    "surname":"bbbb",
    "document": "XXXXXXXX",
    "birthdate": "05/06/1995",
    "companies":["B13268346","B70656012"],

    "permissions":[{
        "tag":"admin",
        "description": "Administrador",
        "status": true,
        "reader": true,
        "writer": true
    },
    {
      "tag":"user",
      "description": "Gestion de Usuario",
      "status": true,
      "reader": true,
      "writer": true,
      "global": false,
    }],
    "users": ["bbb@bbb.bb"]
  }
]
```

Obtener todos los usuarios a los que el usuario (token) que hace la petición tenga acceso. Devuelve los 25 primeros valores, para obtener los siguientes 25 objetos hay que especificar el atributo last a la hora de hacer a petición.

### HTTP Request

`GET https://api.tedi.center/user`

### Parámetros

| Name |  Type  | Description |
|------|--------|-------------|
| last | string | Email del último usuario del array devuelto en la anterior petición. |

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
  "name":"aaaa",
  "surname":"bbbb",
  "document": "XXXXXXXX",
  "birthdate": "05/06/1995",
  "actual_company":"B13268346",
  "companies":["B13268346","B70656012"],
  "permissions":[{
      "tag":"admin",
      "description": "Administrador",
      "status": true,
      "reader": true,
      "writer": true,
      "global": true
  }],
  "users": ["bbb@bbb.bb"]
}
```

### HTTP Request

`GET https://api.tedi.center/user/:email`

### Path paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| email | string | Email del usuario.|


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
  "name":"aaaa",
  "surname":"bbbb",
  "document": "XXXXXXXX",
  "birthdate": "05/06/1995",
  "actual_company":"B13268346",
  "companies":["B13268346","B70656012"],
  "permissions":[{
      "tag":"admin",
      "description": "Administrador",
      "status": true,
      "reader": true,
      "writer": true,
      "global": true
  }],
  "users": ["bbb@bbb.bb"]
}
```

### HTTP Request

`POST https://api.tedi.center/user`

### Parámetros

| Name |  Type  | Description |
|------|--------|-------------|
| email | string | Email del usuario. |
| name | string | Nombre del usuario. |
| surname | string | Apellidos del usuario. |
| document | string | Documentación del usuario (DNI). |
| password | string | Contraseña del usuario. |
| companies | [string] | Lista de empresas a las que el usuario tiene acces (CIF). |
| actual_company | string | Última empresa a la que el usuario a accedido (CIF). |
| users | [string] | Lista de usuarios a los que el usuario tiene acceso (tener permisos de gestión de usuarios). |
| permissions | [string] | Lista de Permisos |

### Permisos

Los Permisos son los siguienter:
  Administrador,
  Gestión de Usuarios,
  Gestión de Empresas,
  Gestión de Facturas Emitidas,
  Gestión de Facturas Recibidas,
  Gestión de Tickets.

| Name |  Type  | Description |
|------|--------|-------------|
| tag | string | Etiqueta para identificar el tipo de permiso. (admin, user, company, invoice, invoice_issued, invoice_received, invoice_ticket) |
| description | string | Descripción del permiso (Administrador, Gestion de usuarios, ...). |
| status | boolean | True sii el permiso está activado. |
| reader | boolean | True sii tiene permisos de lectura. |
| writer | boolean | True sii tiene permisos de lectura y escritura. |
| global | boolean | True sii tiene acceso a todos los datos de la empresa, si es False solo tiene acceso a la información aportada por el usuario. |

## Borrar un Usuario

> Ejemplo de llamada al servicio “Obtener Todas los usuarios:

```shell
curl --request DELETE "https://api.tedi.center/user/:email"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "email": "aaaa@aaaa.aa",
  "name": "aaaa",
  "surname": "bbbb",
  "document": "XXXXXXXX",
  "birthdate": "05/06/1995",
  "actual_company":"B13268346",
  "companies":["B13268346","B70656012"],
  "permissions":[{
      "tag":"admin",
      "description": "Administrador",
      "status": true,
      "reader": true,
      "writer": true,
      "global": true
  }],
  "users": ["bbb@bbb.bb"]
}
```

### HTTP Request

`DELETE https://api.tedi.center/user/:email`

### Path paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| email | string | Email del usuario.|
