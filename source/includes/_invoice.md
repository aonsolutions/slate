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
    }
  }
]
```

Este servicio permite obtener todas las facturas de una determinada empresa.

### HTTP Request

`GET https://api.tedi.center/invoice/:company/`

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
curl --request GET "https://api.tedi.center/invoice/:company"
 -H "session_id:YOURSESSIONID"
```

> Ejemplo de JSON de respuesta:

```json
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
  }
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
  }
}
```

Este servicio permite enviar información para crear/actualizar una factura de una determinada empresa.

### HTTP Request

`POST https://api.tedi.center/invoice`

### Header parameters

| Name |  Type  | Description |
|------|--------|-------------|
| session_id | string | Identificador del sistema devuelto por el servicio de Autenticación. |
| json | json | Factura en formato JSON. |

Si se específica number, la API interpreta que es una actualización de factura, en caso contrario se tratará como una creación de factura.

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
  }
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
