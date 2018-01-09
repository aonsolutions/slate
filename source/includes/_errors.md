# Errores

<aside class="notice">TLas respuestas proporcionadas por esta API siempre se reciben en un formato de JSON</aside>

Los códigos de error más habituales en aonSolutions:

Código | Mensaje | Descripción
------ | ------- | -----------
400 | Bad Request | Tu petición no es válida, reformula la petición al servidor para obtner una respuesta válida.
401 | Unauthorized | Tu session_id en aonSolutions no es válida, por favor vuelve a hacer login en aonSolutions.
403 | Forbidden | No tienes acceso a este servicio.
404 | Not Found | El servicio solicitado no existe.
405 | Method Not Allowed | El servicio solicitado no está activo.
406 | Not Acceptable | La petición realizada no es un JSON.
410 | Gone | El servicio ha sido eliminado de los servidores de aonSolutions.
429 | Too Many Requests | Se han realizado demasiadas peticiones a los servicios en un periodo muy corto de tiempo.
500 | Internal Server Error | Ha habido algún problema en los servidores de aonSolutions. Por favor, inténtelo más tarde.
503 | Service Unavailable | El servicio no está disponible por razones de mantenimiento. Por favor, inténtelo más tarde.
