# Tipos de Factura

## Obtener Todos los Tipos de Factura

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.tedi.center/type"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
[
  {
    "account": "629.0.0",
    "name": "Otros gastos",
    "description": "629. Otros gastos",
    "icon": "receipt"
  }
]
```

Obtener todos los tipos de factura a los que el usuario (token) que hace la petición tenga acceso.

### HTTP Request

`GET https://api.tedi.center/type`
