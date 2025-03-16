# Checkmarx ZAP report 1

ZAP by [Checkmarx](https://checkmarx.com/).


## Sumario de Alertas

| Nivel de riesgo | Número de Alertas |
| --- | --- |
| Alto | 0 |
| Medio | 1 |
| Bajo | 0 |
| Informativo | 1 |




## Alertas

| Nombre | Nivel de riesgo | Número de Instancias |
| --- | --- | --- |
| Ausencia de Tokens Anti-CSRF | Medio | 2 |
| Petición de Autenticación Identificada | Informativo | 1 |




## Detalles de la Alerta



### [ Ausencia de Tokens Anti-CSRF ](https://www.zaproxy.org/docs/alerts/10202/)



##### Medio (Baja)

### Descripción

No se encontraron tokens Anti-CSRF en formulario de envío HTML.
Una solicutud falsa entre sitios en un ataque que compromete y obliga a una víctima a enviar su solicitud HTTP a un destino objetivo sin su conocimiento o intención para poder realizar una acción como víctima. La causa oculta es la funcionalidad de la aplicación utilizando acciones de URL/formulario que pueden ser adivinados de forma repetible. La naturaleza del ataque es que CSRG explota la confianza que un sitio web proporciona a un usuario. Por el contrario, las cadenas de comandos de los sitios cruzados (XSS) explotan la confianza que un usuario proporciona en un sitio web. Al igual que XSS, los ataques CSRG no son de forma necesaria de sitios cruzados, pero hay la posibilidad de que si pueden serlo. La falsificación de las solicitudes ente los sitios también se conoce como CSRF, XSRG, ataques con un solo clic, montaje de sesión, diputado confundido y navegación en alta mar.

Los ataques de CSRG son muy efectivos en varias situaciones, que incluyen:
*La victima tiene una sesión activa en el sitio de destino.
    *La víctima se autoriza por medio de la autenticación HTTP en el sitio de destino.
    *La víctima se encuentra en la misma red local que el sitio de destino.

CSRF se ha utilizado especialmente para poder realizar una acción contra un sitio objetivo utilizando los privilegios de la víctima, pero se han revelado técnicas recientes para difundir información al obtener el acceso a la respuesta. El riesgo de divulgación de información aumenta de forma drástica cuando el sitio de destino se encuentra vulnerable a XSS, porque XSS se puede utilizar como una plataforma para CSRF, lo que le permite al atacante que opere desde adentro de los líites de la misma política de origen.

* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `<form action="/login" method="POST">`
  * Otra información: `No se ha encontrado ningún token Anti-CSRF [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token] conocido en el siguiente formulario HTML: [Form 1: "password" "username" ].`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `<form action="/register" method="POST">`
  * Otra información: `No se ha encontrado ningún token Anti-CSRF [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token] conocido en el siguiente formulario HTML: [Form 1: "birthdate" "password" "username" ].`

Instancia: 2

### Solución

Fase: Arquitectura y Diseño
Utilizar una biblioteca o framework verificado y confiable que evite esta vulnerabilidad o proporcione elementos que faciliten evitarla.
Por ejemplo, utilice el paquete anti-CSRG como el CSRGuard de OWASP.

Fase: Implementación
Asegúrese de que su aplicación esté libre de fallas de secuencias de comandos entre sitios, ya que la mayoría de las defensas de CSRF pueden detenerse por alto por medio del uso de secuencias de comandos manejadas por el atacante.

Fase: Arquitectura y Diseño
Origina un nonce único para cada uno de los formularios, coloque el nonce en el formularo y confirme la independencia al obtener el formulario. Asegúrese de que el nonce no sea predecible (CWE-330).
Usted tiene que tener en cuenta que esto puede pasar desapercibido utilizando XSS.

Identificar las operaciones que sean especialmente peligrosas. Cuando el usuario desarrolla una operación peligrosa, envíe una solicitud de confirmación de forma separada para poder garantizar que el usuario tenga la intención de desarrollar esa operación.
Usted tiene que tener en cuenta que esto puede pasar desapercibido utilizando XSS.

Utilice el control de gestión de la sesión de ESAPI.
Este control introduce un elemento para CSRF.

No utilice el método GET para ninguna de las solicitudes que puedan desencadenar un cambio de estado.

Fase: Implementación
Revise que la solicitud se creó en la página esperada. Esto podría quebrar la funcionalidad auténtica, ya que los usuarios o los representantes puede ser que hayan desactivado el envío de Referer por motivos de privacidad.

### Referencia


* [ https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)
* [ https://cwe.mitre.org/data/definitions/352.html ](https://cwe.mitre.org/data/definitions/352.html)


#### CWE Id: [ 352 ](https://cwe.mitre.org/data/definitions/352.html)


#### WASC Id: 9

#### ID de la Fuente: 3

### [ Petición de Autenticación Identificada ](https://www.zaproxy.org/docs/alerts/10111/)



##### Informativo (Alta)

### Descripción

La petición en cuestión se ha identificado como una petición de autenticación. El campo "Otra información" contiene un conjunto de líneas key=vvalue que identifican cualquier campo relevante. Si la solicitud está en un contexto que tiene un método de autenticación configurado como "Detección automática", esta regla cambiará la autenticación para que coincida con la petición identificada.

* URL: http://localhost:8000/login
  * Método: `POST`
  * Parámetros: `username`
  * Ataque: ``
  * Evidencia: `password`
  * Otra información: `userParam=username
userValue=foo-bar@example.com
passwordParam=password
referer=http://localhost:8000/login`

Instancia: 1

### Solución

Se trata de una alerta informativa y no de una vulnerabilidad, por lo que no hay nada que corregir.

### Referencia


* [ https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/ ](https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/)



#### ID de la Fuente: 3


