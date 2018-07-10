# Autenticación

> Para autenticarse, debes hacerlo con la siguiente llamada al servicio web:

```shell

# El servicio Login es una llamada POST
curl --request POST "https://api.tedi.center/auth"
  --data "user=youruser@email.xxx"
  --data "password=yourtEDICenterpassword"
```

> La respuesta devolverá la session_id que deberás utilizar en cada petición a los servicios de tEDI Center:

```json
{
  "session_id": "234QWEREWRewfq23ehjHF456..."
}
```

tEDI Center utiliza un sistema de identificadores de sesión para autorizar a un usuario a realizar llamadas a cualquier servicio web.

### HTTP Request

`POST https://api.tedi.center/auth`

### Parámetros

| Name |  Type  | Description |
|------|--------|-------------|
| user | string | Cuenta de correo registrada en tEDI Center. Si no dispones de una, por favor regístrate en https://tedi.center |
| password | string | Contraseña utilizada en el registro de tEDI Center |

Si el usuario no utiliza este identificador, el servicio devolverá el error “Unauthorized” y se deberá volver a identificar para seguir haciendo uso de los servicios.

<aside class="notice">Se necesita el valor de session_id para cualquier otra llamada a la API de tEDI Center.</aside>
