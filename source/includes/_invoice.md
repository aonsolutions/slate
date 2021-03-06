# Facturas

## Obtener Todas las Facturas

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.tedi.center/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
[
  {
    "company": "B70656012",
    "number": 42,
    "info": {
      "reference":"2017/000012312",
      "sender":{
        "document":{
          "document":"B13268346",
          "type":{
            "id":"01",
            "name":"NIF"
          },
          "country":"ES"
        },
        "name": "EMPRESA DEMO S.L.",
        "address":{
          "address":"Mayor 1",
          "city":"VITORIA-GASTEIZ",
          "province":"ALAVA/ARABA",
          "postal_code":"01008",
          "country":"ESP"
        }
      },
      "receiver":{
        "document":{
          "document":"B13268346",
          "type":{
            "id":"01",
            "name":"NIF"
          },
          "country":"ES"
        },
        "name": "EMPRESA DEMO S.L.",
        "address":{
          "address":"Mayor 1",
          "city":"VITORIA-GASTEIZ",
          "province":"ALAVA/ARABA",
          "postal_code":"01008",
          "country":"ESP"
        }
      },
      "date":2017-12-20,
      "taxable_base":100.00,
      "total":21.00,
      "taxes":[{
        "tax_type":21.00,
        "base":100.00,
        "percentage":21.00,
        "quota":21.00,
        "surcharge":0.00,
        "surcharge_quota":0.00,
        "vat_deduction_type":0.00,
        "withholding_type":0.00,
        "deductible_percent":0.00,
        "deductible_quota":0.00
      }],
      "type":{
        "type":"gasto",
        "pgc":{
          "account": "629.0.0",
          "name": "Otros gastos",
          "description": "629. Otros gastos",
          "icon": "receipt"
        },
        "value":"F1",
        "description":"Factura"
      },
      "transaction":false,
      "investment":false,
      "service":false,
      "surcharge":false,
      "vat_accrual_regime":false,
      "details":[{
        "product":"P001",
        "detalle":"",
        "detalle2":"",
        "detalle3":"",
        "description":"PRODUCTO 01",
        "quantity":12,
        "price":100.00,
        "purchase_price":95.2,
        "discount":10.0,
        "workplace":"",
        "warehouse":"PRINCIPAL",
        "vat":21.00
      }],
      "finances":[{
        "due_date":2018-10-10,
        "amount":100.00,
        "bank_account":"ES4236598653245698723657"
      }],
      "file":{
        "image_url":"",
        "pdf_url":"",
        "json_url":""
      }
    },
    "history":[{
      "action": "create",
      "user": "aaaa@aaa.a",
      "date": "2017-05-01"
    }, {
      "action": "edit",
      "user": "bbbb@bbb.b",
      "date": "2017-06-01"
    }]

  }
]
```

Este servicio permite obtener todas las facturas de una determinada empresa. Devuelve los 25 primeros valores, para obtener los siguientes 25 objetos hay que especificar el atributo last a la hora de hacer a petición.

### HTTP Request

`GET https://api.tedi.center/invoice/:company?filter={}`

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
| type | string | Tipo de la factura (emitidas, recibidas, ticket)  |
| status | string | Estado de la factura (pendiente, revision, aceptada) |
| last | string | Número de la última factura del array devuelto en la anterior petición. |

## Obtener una Factura específica

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.tedi.center/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "company": "B70656012",
  "number": 42,
  "info": {
    "code":"R-2018/1",
    "reference":"2017/000012312",
    "status":"pendiente || revision || aceptada",
    "source":"web || phone || mail",
    "sender":{
      "document":{
        "document":"B13268346",
        "type":{
          "id":"01",
          "name":"NIF"
        },
        "country":"ES"
      },
      "name": "EMPRESA DEMO S.L.",
      "address":{
        "address":"Mayor 1",
        "city":"VITORIA-GASTEIZ",
        "province":"ALAVA/ARABA",
        "postal_code":"01008",
        "country":"ESP"
      }
    },
    "receiver":{
      "document":{
        "document":"B13268346",
        "type":{
          "id":"01",
          "name":"NIF"
        },
        "country":"ES"
      },
      "name": "EMPRESA DEMO S.L.",
      "address":{
        "address":"Mayor 1",
        "city":"VITORIA-GASTEIZ",
        "province":"ALAVA/ARABA",
        "postal_code":"01008",
        "country":"ESP"
      }
    },
    "date":2017-12-20,
    "taxable_base":100.00,
    "total":21.00,
    "taxes":[{
      "tax_type":21.00,
      "base":100.00,
      "percentage":21.00,
      "quota":21.00,
      "surcharge":0.00,
      "surcharge_quota":0.00,
      "vat_deduction_type":0.00,
      "withholding_type":0.00,
      "deductible_percent":0.00,
      "deductible_quota":0.00
    }],
    "type":{
      "type":"emitidas || recibidas || ticket",
      "pgc":{
        "account": "629.0.0",
        "name": "Otros gastos",
        "description": "629. Otros gastos",
        "icon": "receipt"
      },
      "value":"F1",
      "description":"Factura"
    },
    "transaction":false,
    "investment":false,
    "service":false,
    "surcharge":false,
    "vat_accrual_regime":false,
    "details":[{
      "product":"P001",
      "detalle":"",
      "detalle2":"",
      "detalle3":"",
      "description":"PRODUCTO 01",
      "quantity":12,
      "price":100.00,
      "purchase_price":95.2,
      "discount":10.0,
      "workplace":"",
      "warehouse":"PRINCIPAL",
      "vat":21.00
    }],
    "finances":[{
      "due_date":2018-10-10,
      "amount":100.00,
      "bank_account":"ES4236598653245698723657"
    }],
    "file":{
      "image_url":"",
      "pdf_url":"",
      "json_url":""
    }
  },
  "history":[{
    "action": "create",
    "user": "aaaa@aaa.a",
    "date": "2017-05-01"
  }, {
    "action": "edit",
    "user": "bbbb@bbb.b",
    "date": "2017-06-01"
  }]
}
```

### HTTP Request

`GET https://api.tedi.center/invoice/:company/:number`

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
curl --request POST "https://api.tedi.center/invoice"
 -H "session_id:YOURSESSIONID"
 --data "json"
```

> Ejemplo de JSON de respuesta:

```json
{
  "company": "B70656012",
  "number": 42,
  "info": {
    "code":"R-2018/1",
    "reference":"2017/000012312",
    "status":"pendiente || revision || aceptada",
    "source":"web || phone || mail",
    "sender":{
      "document":{
        "document":"B13268346",
        "type":{
          "id":"01",
          "name":"NIF"
        },
        "country":"ES"
      },
      "name": "EMPRESA DEMO S.L.",
      "address":{
        "address":"Mayor 1",
        "city":"VITORIA-GASTEIZ",
        "province":"ALAVA/ARABA",
        "postal_code":"01008",
        "country":"ESP"
      }
    },
    "receiver":{
      "document":{
        "document":"B13268346",
        "type":{
          "id":"01",
          "name":"NIF"
        },
        "country":"ES"
      },
      "name": "EMPRESA DEMO S.L.",
      "address":{
        "address":"Mayor 1",
        "city":"VITORIA-GASTEIZ",
        "province":"ALAVA/ARABA",
        "postal_code":"01008",
        "country":"ESP"
      }
    },
    "date":2017-12-20,
    "taxable_base":100.00,
    "total":21.00,
    "taxes":[{
      "tax_type":21.00,
      "base":100.00,
      "percentage":21.00,
      "quota":21.00,
      "surcharge":0.00,
      "surcharge_quota":0.00,
      "vat_deduction_type":0.00,
      "withholding_type":0.00,
      "deductible_percent":0.00,
      "deductible_quota":0.00
    }],
    "type":{
      "type":"emitidas || recibidas || ticket",
      "pgc":{
        "account": "629.0.0",
        "name": "Otros gastos",
        "description": "629. Otros gastos",
        "icon": "receipt"
      },
      "value":"F1",
      "description":"Factura"
    },
    "transaction":false,
    "investment":false,
    "service":false,
    "surcharge":false,
    "vat_accrual_regime":false,
    "details":[{
      "product":"P001",
      "detalle":"",
      "detalle2":"",
      "detalle3":"",
      "description":"PRODUCTO 01",
      "quantity":12,
      "price":100.00,
      "purchase_price":95.2,
      "discount":10.0,
      "workplace":"",
      "warehouse":"PRINCIPAL",
      "vat":21.00
    }],
    "finances":[{
      "due_date":2018-10-10,
      "amount":100.00,
      "bank_account":"ES4236598653245698723657"
    }],
    "file":{
      "image_url":"",
      "pdf_url":"",
      "json_url":""
    }
  },
  "history":[{
    "action": "create",
    "user": "aaaa@aaa.a",
    "date": "2017-05-01"
  }, {
    "action": "edit",
    "user": "bbbb@bbb.b",
    "date": "2017-06-01"
  }]
}
```

Este servicio permite enviar información para crear/actualizar una factura de una determinada empresa.

### HTTP Request

`POST https://api.tedi.center/invoice`

### Header parameters

| Name |  Type  | Description |
|------|--------|-------------|
| session_id | string | Identificador del sistema devuelto por el servicio de Autenticación. |

### Parámetros

Si se específica number, la API interpreta que es una actualización de factura, en caso contrario se tratará como una creación de factura.

| Name |  Type  | Description |
|------|--------|-------------|
| company | string | CIF de la empresa a la que pertenece la factura. |
| number | number | Identificador de la factura. |
| info | json | Información de la factura. |
| history | [json] | Histórico de las modificaciones de la factura. |


### Parámetros (envío fichero)

Para enviar el fichero de una factura (en formato imagen o pdf), se deberá de hacer la petición con los siguientes parámetros.

| Name |  Type  | Description |
|------|--------|-------------|
| company | string | CIF de la empresa a la que pertenece la factura. |
| content | string | Fichero en base64. |
| contentType | string | Formato del fichero ('image/png'). |
| contentEncoding | string | 'base64' |

## Borrar una Factura

> Ejemplo de llamada al servicio “Obtener Todas las Facturas”:

```shell
curl --request GET "https://api.tedi.center/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
{
  "company": "B70656012",
  "number": 42,
  "info": {
    "code":"R-2018/1",
    "reference":"2017/000012312",
    "status":"pendiente || revision || aceptada",
    "source":"web || phone || mail",
    "sender":{
      "document":{
        "document":"B13268346",
        "type":{
          "id":"01",
          "name":"NIF"
        },
        "country":"ES"
      },
      "name": "EMPRESA DEMO S.L.",
      "address":{
        "address":"Mayor 1",
        "city":"VITORIA-GASTEIZ",
        "province":"ALAVA/ARABA",
        "postal_code":"01008",
        "country":"ESP"
      }
    },
    "receiver":{
      "document":{
        "document":"B13268346",
        "type":{
          "id":"01",
          "name":"NIF"
        },
        "country":"ES"
      },
      "name": "EMPRESA DEMO S.L.",
      "address":{
        "address":"Mayor 1",
        "city":"VITORIA-GASTEIZ",
        "province":"ALAVA/ARABA",
        "postal_code":"01008",
        "country":"ESP"
      }
    },
    "date":2017-12-20,
    "taxable_base":100.00,
    "total":21.00,
    "taxes":[{
      "tax_type":21.00,
      "base":100.00,
      "percentage":21.00,
      "quota":21.00,
      "surcharge":0.00,
      "surcharge_quota":0.00,
      "vat_deduction_type":0.00,
      "withholding_type":0.00,
      "deductible_percent":0.00,
      "deductible_quota":0.00
    }],
    "type":{
      "type":"emitidas || recibidas || ticket",
      "pgc":{
        "account": "629.0.0",
        "name": "Otros gastos",
        "description": "629. Otros gastos",
        "icon": "receipt"
      },
      "value":"F1",
      "description":"Factura"
    },
    "transaction":false,
    "investment":false,
    "service":false,
    "surcharge":false,
    "vat_accrual_regime":false,
    "details":[{
      "product":"P001",
      "detalle":"",
      "detalle2":"",
      "detalle3":"",
      "description":"PRODUCTO 01",
      "quantity":12,
      "price":100.00,
      "purchase_price":95.2,
      "discount":10.0,
      "workplace":"",
      "warehouse":"PRINCIPAL",
      "vat":21.00
    }],
    "finances":[{
      "due_date":2018-10-10,
      "amount":100.00,
      "bank_account":"ES4236598653245698723657"
    }],
    "file":{
      "image_url":"",
      "pdf_url":"",
      "json_url":""
    }
  },
  "history":[{
    "action": "create",
    "user": "aaaa@aaa.a",
    "date": "2017-05-01"
  }, {
    "action": "edit",
    "user": "bbbb@bbb.b",
    "date": "2017-06-01"
  }]
}
```

Este servicio permite borrar una factura de una determinada empresa.

### HTTP Request

`DELETE https://api.tedi.center/invoice/:company/:number`

### Path paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| company | string | NIF de la empresa a la que pertenece la factura. |
| number | string | Número identificativo de la factura en tEDI. |

### Header paramaters

| Name |  Type  | Description |
|------|--------|-------------|
| session_id | string | Identificador del sistema devuelto por el servicio de Autenticación. |
