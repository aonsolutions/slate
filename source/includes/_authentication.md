# Autenticación

> Para autenticarse, debes hacerlo con la siguiente llamada al servicio web:

```shell

# El servicio Login es una llamada POST
curl --request POST "https://api.aonSolutions.es/auth"
  --data "user=youruser@email.xxx"
  --data "password=youraonSolutionspassword"
```

> La respuesta devolverá la session_id que deberás utilizar en cada petición a los servicios de aonSolutions:

```json
{
  "session_id": "234QWEREWRewfq23ehjHF456..."
}
```

aonSolutions utiliza un sistema de identificadores de sesión para autorizar a un usuario a realizar llamadas a cualquier servicio web.

### HTTP Request

`POST https://api.aonSolutions.es/auth`

### Parámetros

| Name |  Type  | Description |
|------|--------|-------------|
| user | string | Cuenta de correo registrada en aonSolutions. Si no dispones de una, por favor regístrate en https://aonSolutions.es |
| password | string | Contraseña utilizada en el registro de aonSolutions |

Si el usuario no utiliza este identificador, el servicio devolverá el error “Unauthorized” y se deberá volver a identificar para seguir haciendo uso de los servicios.

<aside class="notice">Se necesita el valor de session_id para cualquier otra llamada a la API de aonSolutions.</aside>
