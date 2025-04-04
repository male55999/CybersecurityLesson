# Checkmarx ZAP report 3

ZAP by [Checkmarx](https://checkmarx.com/).


## Sumario de Alertas

| Nivel de riesgo | Número de Alertas |
| --- | --- |
| Alto | 0 |
| Medio | 3 |
| Bajo | 4 |
| Informativo | 3 |




## Alertas

| Nombre | Nivel de riesgo | Número de Instancias |
| --- | --- | --- |
| Ausencia de Tokens Anti-CSRF | Medio | 1 |
| Cabecera Content Security Policy (CSP) no configurada | Medio | 8 |
| Falta de cabecera Anti-Clickjacking | Medio | 8 |
| Divulgación de Marcas de Tiempo - Unix | Bajo | 6 |
| El servidor filtra información de versión a través del campo "Server" del encabezado de respuesta HTTP | Bajo | 1 |
| Falta encabezado X-Content-Type-Options | Bajo | 9 |
| Strict-Transport-Security Header No Establecido | Bajo | 25 |
| Petición de Autenticación Identificada | Informativo | 3 |
| Reexaminar las Directivas de Control de Caché | Informativo | 18 |
| Respuesta de Gestión de Sesión Identificada | Informativo | 51 |




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

* URL: http://localhost:8000/resources
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `<form action="/resources" method="POST">`
  * Otra información: `No se ha encontrado ningún token Anti-CSRF [anticsrf, CSRFToken, __RequestVerificationToken, csrfmiddlewaretoken, authenticity_token, OWASP_CSRFTOKEN, anoncsrf, csrf_token, _csrf, _csrfSecret, __csrf_magic, CSRF, _token, _csrf_token] conocido en el siguiente formulario HTML: [Form 1: "resource_id" "resource_name" ].`

Instancia: 1

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

### [ Cabecera Content Security Policy (CSP) no configurada ](https://www.zaproxy.org/docs/alerts/10038/)



##### Medio (Alta)

### Descripción

La Política de seguridad de contenido (CSP) es una capa adicional de seguridad que ayuda a detectar y mitigar ciertos tipos de ataques, incluidos Cross Site Scripting (XSS) y ataques de inyección de datos. Estos ataques se utilizan para todo, desde el robo de datos hasta la desfiguración del sitio o la distribución de malware. CSP proporciona un conjunto de encabezados HTTP estándar que permiten a los propietarios de sitios web declarar fuentes de contenido aprobadas que los navegadores deberían poder cargar en esa página; los tipos cubiertos son JavaScript, CSS, marcos HTML, fuentes, imágenes y objetos incrustados como applets de Java, ActiveX, archivos de audio y video.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696267841&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223763&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223793&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742310213&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``

Instancia: 8

### Solución

Asegúrese de que su servidor web, servidor de aplicaciones, balanceador de carga, etc. esté configurado para establecer la cabecera Content-Security-Policy.

### Referencia


* [ https://developer.mozilla.org/en-US/docs/Web/Security/CSP/Introducing_Content_Security_Policy ](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/Introducing_Content_Security_Policy)
* [ https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
* [ https://www.w3.org/TR/CSP/ ](https://www.w3.org/TR/CSP/)
* [ https://w3c.github.io/webappsec-csp/ ](https://w3c.github.io/webappsec-csp/)
* [ https://web.dev/articles/csp ](https://web.dev/articles/csp)
* [ https://caniuse.com/#feat=contentsecuritypolicy ](https://caniuse.com/#feat=contentsecuritypolicy)
* [ https://content-security-policy.com/ ](https://content-security-policy.com/)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### ID de la Fuente: 3

### [ Falta de cabecera Anti-Clickjacking ](https://www.zaproxy.org/docs/alerts/10020/)



##### Medio (Media)

### Descripción

La respuesta no protege contra ataques de "ClickJacking". Debes incluir Content-Security-Policy con la directiva "frame-ancestors" o X-Frame-Options.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696267841&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223763&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223793&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742310213&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2
  * Método: `GET`
  * Parámetros: `x-frame-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``

Instancia: 8

### Solución

Los navegadores web modernos admiten las cabeceras HTTP Content-Security-Policy y X-Frame-Options. Asegúrese de que una de ellas está configurada en todas las páginas web devueltas por su sitio/aplicación.
Si espera que la página esté enmarcada solo por páginas en su servidor (por ejemplo, si forma parte de un FRAMESET), utilice SAMEORIGIN; de lo contrario, si no espera que la página esté enmarcada, utilice DENY. Alternativamente, considere implementar la directiva "frame-ancestors" de la Política de Seguridad de Contenidos.

### Referencia


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options)


#### CWE Id: [ 1021 ](https://cwe.mitre.org/data/definitions/1021.html)


#### WASC Id: 15

#### ID de la Fuente: 3

### [ Divulgación de Marcas de Tiempo - Unix ](https://www.zaproxy.org/docs/alerts/10096/)



##### Bajo (Baja)

### Descripción

Una marca de tiempo fue revelada por la aplicación/servidor web. - Unix

* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `1673999601`
  * Otra información: `1673999601, que se evalúa como: 2023-01-18 01:53:21.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `1679317318`
  * Otra información: `1679317318, que se evalúa como: 2023-03-20 15:01:58.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `1696267841`
  * Otra información: `1696267841, que se evalúa como: 2023-10-02 20:30:41.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `1742223763`
  * Otra información: `1742223763, que se evalúa como: 2025-03-17 17:02:43.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `1742223793`
  * Otra información: `1742223793, que se evalúa como: 2025-03-17 17:03:13.`
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `1742310213`
  * Otra información: `1742310213, que se evalúa como: 2025-03-18 17:03:33.`

Instancia: 6

### Solución

Confirmar que los datos encontrados de información sobre la marca de tiempo no son sensibles, ni se pueden usar en patrones explotables de divulgación.

### Referencia


* [ https://cwe.mitre.org/data/definitions/200.html ](https://cwe.mitre.org/data/definitions/200.html)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### ID de la Fuente: 3

### [ El servidor filtra información de versión a través del campo "Server" del encabezado de respuesta HTTP ](https://www.zaproxy.org/docs/alerts/10036/)



##### Bajo (Alta)

### Descripción

El servidor web/aplicación está filtrando información de versión a través de la cabecera de respuesta HTTP "Server". El acceso a dicha información puede facilitar a los atacantes la identificación de otras vulnerabilidades a las que está sujeto su servidor web/aplicación.

* URL: https://clientservices.googleapis.com/uma/v2
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: `scaffolding on HTTPServer2`
  * Otra información: ``

Instancia: 1

### Solución

Asegúrese de que su servidor web, servidor de aplicaciones, balanceador de carga, etc. está configurado para suprimir la cabecera "Server" o proporcionar detalles genéricos.

### Referencia


* [ https://httpd.apache.org/docs/current/mod/core.html#servertokens ](https://httpd.apache.org/docs/current/mod/core.html#servertokens)
* [ https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10) ](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10))
* [ https://www.troyhunt.com/shhh-dont-let-your-response-headers/ ](https://www.troyhunt.com/shhh-dont-let-your-response-headers/)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### ID de la Fuente: 3

### [ Falta encabezado X-Content-Type-Options ](https://www.zaproxy.org/docs/alerts/10021/)



##### Bajo (Media)

### Descripción

La cabecera Anti-MIME-Sniffing X-Content-Type-Options no se ha establecido en 'nosniff'. Esto permite que las versiones anteriores de Internet Explorer y Chrome realicen MIME-sniffing en el cuerpo de la respuesta, lo que puede provocar que el cuerpo dé la respuesta se interprete y se muestre como un tipo de contenido distinto del tipo de contenido declarado. Las versiones actuales (principios de 2014) y heredadas de Firefox utilizarán el tipo de contenido declarado (si se establece uno), en lugar de realizar MIME-sniffing.

* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696267841&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223763&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223793&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742310213&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2
  * Método: `GET`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`
* URL: https://clientservices.googleapis.com/uma/v2
  * Método: `POST`
  * Parámetros: `x-content-type-options`
  * Ataque: ``
  * Evidencia: ``
  * Otra información: `Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor.`

Instancia: 9

### Solución

Asegúrese de que la aplicación/servidor web establece el encabezado Content-Type adecuadamente, y que establece el encabezado X-Content-Type-Options a 'nosniff' para todas las páginas web.
Si es posible, asegúrese de que el usuario final utiliza un navegador web moderno y compatible con los estándares que no realiza MIME-sniffing en absoluto, o que puede ser dirigido por la aplicación web/servidor web para que no realice MIME-sniffing.

### Referencia


* [ https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85) ](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85))
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### ID de la Fuente: 3

### [ Strict-Transport-Security Header No Establecido ](https://www.zaproxy.org/docs/alerts/10035/)



##### Bajo (Alta)

### Descripción

HTTP Strict Transport Security (HSTS) es un mecanismo de política de seguridad web mediante el cual un servidor web declara que los agentes de usuario conformes (como un navegador web) deben interactuar con él utilizando únicamente conexiones HTTPS seguras (es decir, HTTP superpuesto a TLS/SSL). HSTS es un protocolo de seguimiento de estándares del IETF y se especifica en RFC 6797.

* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAl1ApdiiMzY3hIFDVNVgbUSBQ3OQUx6IScM3bmNkBbw%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAlunE71hp83uBIFDTQ30ysSBQ3c5MosIdCkzK_phCFy%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAmiwikU8viQKRIFDTQ30ysSBQ3c5MosIWbmUHs3fhtBEiAJbpxO9YafN7gSBQ00N9MrEgUN3OTKLCFm5lB7N34bQQ==%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAmq2TcViyKTQRIFDWaQe0sSBQ3MSQIEIUHtElSPfbg2%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAmq2TcViyKTQRIFDWaQe0sSBQ3MSQIEIUHtElSPfbg2El8JGm8lAD5fZyQSBQ00N9MrEgUN3OTKLBIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yEmaL_HQKHcHhIgCW6cTvWGnze4EgUNNDfTKxIFDdzkyiwhJmi_x0Ch3B4SUQm05qxeQf5lthIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yEmaL_HQKHcHg==%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAnG7lSsJWMaZxIFDQszjw4SBQ0C98dkITPU2URTJ1tA%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSJwlCk4KehlEj9hIFDVNVgbUSBQ3OQUx6EgUNXRqesCEYmxmYI8m4SA==%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSUQm05qxeQf5lthIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yG48gYc95InUA==%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSXwkabyUAPl9nJBIFDTQ30ysSBQ3c5MosEgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_ISZov8dAodweEiAJbpxO9YafN7gSBQ00N9MrEgUN3OTKLCEmaL_HQKHcHhJRCbTmrF5B_mW2EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_ISZov8dAodwe%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSZgnYIaX42wFMzxIFDTQ30ysSBQ3c5MosEgUNlJCS-hIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yFDaEBxrvFHNRIgCW6cTvWGnze4EgUNNDfTKxIFDdzkyiwhQ2hAca7xRzUSWAlL-34b-Hr0GRIFDZSQkvoSBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8hQ2hAca7xRzU=%3Falt=proto
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696267841&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223763&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223793&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742310213&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2
  * Método: `GET`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://beacons.gcp.gvt2.com/domainreliability/upload
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://chromewebstore.googleapis.com/v2/items/-/storeMetadata:batchGet
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://clientservices.googleapis.com/uma/v2
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/v1:GetModels%3Fkey=AIzaSyA2KlwBX3mkFo30om9LUFYQhpqLoa_BNhE
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://update.googleapis.com/service/update2/json
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://update.googleapis.com/service/update2/json%3Fcup2key=14:QGaznP5Aw9UByEcoUbMr8Wa2J1dMc7Moei4Wsa6DFK0&cup2hreq=c44669b37047a9b9b9ba99eb089245e2eccd99d13b4f92c7aa929c227a454926
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``
* URL: https://www.googleapis.com/chromewebstore/v1.1/items/verify
  * Método: `POST`
  * Parámetros: ``
  * Ataque: ``
  * Evidencia: ``
  * Otra información: ``

Instancia: 25

### Solución

Asegúrese de que su servidor web, servidor de aplicaciones, balanceador de carga, etc. está configurado para aplicar Strict-Transport-Security.

### Referencia


* [ https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)
* [ https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security ](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
* [ https://caniuse.com/stricttransportsecurity ](https://caniuse.com/stricttransportsecurity)
* [ https://datatracker.ietf.org/doc/html/rfc6797 ](https://datatracker.ietf.org/doc/html/rfc6797)


#### CWE Id: [ 319 ](https://cwe.mitre.org/data/definitions/319.html)


#### WASC Id: 15

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
referer=http://localhost:8000/login
csrfToken=csrf_token`
* URL: http://localhost:8000/login
  * Método: `POST`
  * Parámetros: `username`
  * Ataque: ``
  * Evidencia: `password`
  * Otra información: `userParam=username
userValue=mc@gmail.com
passwordParam=password
referer=https://localhost:8000/login
csrfToken=csrf_token`
* URL: http://localhost:8000/login
  * Método: `POST`
  * Parámetros: `username`
  * Ataque: ``
  * Evidencia: `password`
  * Otra información: `userParam=username
userValue=sp@gmail.com
passwordParam=password
referer=https://localhost:8000/login
csrfToken=csrf_token`

Instancia: 3

### Solución

Se trata de una alerta informativa y no de una vulnerabilidad, por lo que no hay nada que corregir.

### Referencia


* [ https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/ ](https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/)



#### ID de la Fuente: 3

### [ Reexaminar las Directivas de Control de Caché ](https://www.zaproxy.org/docs/alerts/10015/)



##### Informativo (Baja)

### Descripción

La cabecera cache-control no se ha configurado correctamente o falta, lo que permite al navegador y a los proxies almacenar contenido en caché. Para activos estáticos como css, js, o archivos de imagen esto puede ser intencionado, sin embargo, los recursos deben ser revisados para asegurar que ningún contenido sensible será cacheado.

* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAl1ApdiiMzY3hIFDVNVgbUSBQ3OQUx6IScM3bmNkBbw%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAlunE71hp83uBIFDTQ30ysSBQ3c5MosIdCkzK_phCFy%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAmiwikU8viQKRIFDTQ30ysSBQ3c5MosIWbmUHs3fhtBEiAJbpxO9YafN7gSBQ00N9MrEgUN3OTKLCFm5lB7N34bQQ==%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAmq2TcViyKTQRIFDWaQe0sSBQ3MSQIEIUHtElSPfbg2%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAmq2TcViyKTQRIFDWaQe0sSBQ3MSQIEIUHtElSPfbg2El8JGm8lAD5fZyQSBQ00N9MrEgUN3OTKLBIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yEmaL_HQKHcHhIgCW6cTvWGnze4EgUNNDfTKxIFDdzkyiwhJmi_x0Ch3B4SUQm05qxeQf5lthIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yEmaL_HQKHcHg==%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSIAnG7lSsJWMaZxIFDQszjw4SBQ0C98dkITPU2URTJ1tA%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSJwlCk4KehlEj9hIFDVNVgbUSBQ3OQUx6EgUNXRqesCEYmxmYI8m4SA==%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSUQm05qxeQf5lthIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yG48gYc95InUA==%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSXwkabyUAPl9nJBIFDTQ30ysSBQ3c5MosEgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_ISZov8dAodweEiAJbpxO9YafN7gSBQ00N9MrEgUN3OTKLCEmaL_HQKHcHhJRCbTmrF5B_mW2EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_ISZov8dAodwe%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://content-autofill.googleapis.com/v1/pages/ChVDaHJvbWUvMTM0LjAuNjk5OC4xNzgSZgnYIaX42wFMzxIFDTQ30ysSBQ3c5MosEgUNlJCS-hIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_yFDaEBxrvFHNRIgCW6cTvWGnze4EgUNNDfTKxIFDdzkyiwhQ2hAca7xRzUSWAlL-34b-Hr0GRIFDZSQkvoSBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8SBQ0G7bv_EgUNBu27_xIFDQbtu_8hQ2hAca7xRzU=%3Falt=proto
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `private,max-age=604800`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1673999601&target=OPTIMIZATION_TARGET_PAGE_VISIBILITY
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1679317318&target=OPTIMIZATION_TARGET_LANGUAGE_DETECTION
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1696267841&target=OPTIMIZATION_TARGET_OMNIBOX_URL_SCORING
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223763&target=OPTIMIZATION_TARGET_GEOLOCATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742223793&target=OPTIMIZATION_TARGET_NOTIFICATION_PERMISSION_PREDICTIONS
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=1742310213&target=OPTIMIZATION_TARGET_CLIENT_SIDE_PHISHING
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=240731042075&target=OPTIMIZATION_TARGET_SEGMENTATION_COMPOSE_PROMOTION
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``
* URL: https://optimizationguide-pa.googleapis.com/downloads%3Fname=5&target=OPTIMIZATION_TARGET_PAGE_TOPICS_V2
  * Método: `GET`
  * Parámetros: `cache-control`
  * Ataque: ``
  * Evidencia: `public, max-age=86400`
  * Otra información: ``

Instancia: 18

### Solución

Para contenido seguro, asegúrese de que la cabecera HTTP cache-control está configurada con «no-cache, no-store, must-revalidate». Si un activo debe almacenarse en caché, considere establecer las directivas «public, max-age, immutable».

### Referencia


* [ https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching ](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching)
* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control)
* [ https://grayduck.mn/2021/09/13/cache-control-recommendations/ ](https://grayduck.mn/2021/09/13/cache-control-recommendations/)


#### CWE Id: [ 525 ](https://cwe.mitre.org/data/definitions/525.html)


#### WASC Id: 13

#### ID de la Fuente: 3

### [ Respuesta de Gestión de Sesión Identificada ](https://www.zaproxy.org/docs/alerts/10112/)



##### Informativo (Media)

### Descripción

Se ha identificado que la respuesta dada contiene un token de gestión de sesión. El campo 'Other Info' contiene un conjunto de tokens de cabecera que pueden utilizarse en el método Header Based Session Management (gestión de sesión basado en cabecera). Si la petición se encuentra en un contexto que tiene un método Session Management establecido en "Auto-Detect", esta regla cambiará la gestión de sesión para utilizar los tokens identificados.

* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `05efc1ce-177f-46dd-98ed-4308224f4733`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `14bd1037-a5e3-4da9-98c1-9a219200f486`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `1614abe5-95e7-4465-a6f4-c557daeb9cd3`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `2a79dcc6-c107-4c8e-b785-e6ed304fa3cc`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `3a3e9ba3-e737-421c-836a-04029507acb2`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `495d9b2b-1aea-4cb0-b897-58fe17b11329`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `4a7a084c-c88a-4a5f-a396-952f07d03a0d`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `4c571fd6-b5ec-4cd6-81e7-a7811c53eb19`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `77bdd344-9ee2-4450-aa98-5c6633a5c063`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `7c8353b1-5a76-42d6-a8aa-01a3f2641785`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `81e1cdc2-29a3-4cc8-a08a-0322b8e5d86b`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `8469e4c0-02df-4517-953d-3e3d6f22ffa6`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `8b5fe4c7-0036-4e29-8bc8-336e331129fe`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `90aef872-476a-43e1-8e2d-37e175ec08e2`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `968010a8-f9a2-4e10-98cb-2fbce6caa872`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `96912c34-2c98-49df-9be5-50d186e07c12`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `96d5d34f-5a83-46c1-885f-88b69abfe290`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `990c727a-86fc-434a-b95a-c9ecd40803f8`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `9c64c359-da8b-4f1a-9830-01fc1a76bd6d`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `a22060ed-9e9d-459b-9830-04b40b958fe2`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `a70ce355-0c22-491d-a374-510fed4fb5ac`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `b79469e8-34de-473a-9964-c09b0f33e34c`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `ba89ea21-165d-4bb4-97a6-1a1bde29c527`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `bfa78801-832f-4758-8386-568604a832e0`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `c0e06edf-c067-4885-aac9-a16bb65e4907`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `d105c249-3dd9-4ed9-b399-df090176c81f`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `de04e30d-4e1e-4eef-9277-05b0e22b7dc8`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `ea306929-7616-40ce-bcfd-0f5f75f24b6f`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `f98f37b3-1cfc-4150-97df-1188aa7097a7`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `0ce23ddc-29de-4f28-b25c-d8e1a4256c7c`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `0f1acabc-deed-46fc-93c8-ffaafe088d41`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `1a24452a-63c4-49ab-b025-0dc5d4fefa62`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `20cb69a5-d163-4668-b579-2f1010d936c8`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `4d518a3c-6315-4867-9e03-181956b29280`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `4db88c36-fa55-4241-96f8-7464835c17f3`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `66a25255-b08f-4e6c-8bc4-8040cda1a1c1`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `6ada7e66-e1b3-46ab-b8c4-77cde05cdd93`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `70b1e677-26c4-4a25-a322-d7c3d6fc6044`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `7363b0ef-49aa-4f07-be46-2253e53b1629`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `861e539d-a80d-4c1c-bbd0-e8955240845c`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `87f026b1-8f87-4a3d-834e-e95bc713fee1`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `8859be13-edb2-47d7-b32c-e579573d9991`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `dccfdf17-9d06-45fa-851b-cd17be02bf63`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `e2736510-d2b0-4b75-8a02-78b1d8fbd617`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `e8fa68af-35df-46d7-a375-e0a2b4b93907`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `f8818693-807e-400b-bdda-7ea5ff02d91a`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/register
  * Método: `GET`
  * Parámetros: `csrf_token`
  * Ataque: ``
  * Evidencia: `fe0f6b15-8068-45d1-9b9c-b346c020c042`
  * Otra información: `
cookie:csrf_token`
* URL: http://localhost:8000/login
  * Método: `POST`
  * Parámetros: `session_id`
  * Ataque: ``
  * Evidencia: `08f07fe2-3ba0-4c8d-8fe5-f1d0230b520b`
  * Otra información: `
cookie:session_id`
* URL: http://localhost:8000/login
  * Método: `POST`
  * Parámetros: `session_id`
  * Ataque: ``
  * Evidencia: `53bda413-5abe-4db9-8085-d06923fc9b81`
  * Otra información: `
cookie:session_id`
* URL: http://localhost:8000/register
  * Método: `POST`
  * Parámetros: `session_id`
  * Ataque: ``
  * Evidencia: `584c56e5-f071-4ba5-96fe-3004e0a9292b`
  * Otra información: `
cookie:session_id`
* URL: http://localhost:8000/register
  * Método: `POST`
  * Parámetros: `session_id`
  * Ataque: ``
  * Evidencia: `eaa54961-70cc-4003-bcdf-7b9fd3b59f3f`
  * Otra información: `
cookie:session_id`

Instancia: 51

### Solución

Se trata de una alerta informativa y no de una vulnerabilidad, por lo que no hay nada que corregir.

### Referencia


* [ https://www.zaproxy.org/docs/desktop/addons/authentication-helper/session-mgmt-id ](https://www.zaproxy.org/docs/desktop/addons/authentication-helper/session-mgmt-id)



#### ID de la Fuente: 3


