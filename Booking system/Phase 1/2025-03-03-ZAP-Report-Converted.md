




Checkmarx ZAP report 1






# Checkmarx ZAP report 1



Generated with [![The ZAP logo](2025-03-03-ZAP-Report-/zap32x32.png)ZAP](https://zaproxy.org)
on lun 3 mar 2025, at 17:37:46



ZAP Versión: 2.16.0



 ZAP by [Checkmarx](https://checkmarx.com/)






## Contents



1. [About this report](#about-this-report)
	1. [Report parameters](#report-parameters)

- [Summaries](#summaries)
	1. [Alert counts by risk and confidence](#risk-confidence-counts)
	2. [Alert counts by site and risk](#site-risk-counts)
	3. [Alert counts by alert type](#alert-type-counts)

- [Alerts](#alerts)
	1. [Risk=Medio, Confidence=Alta (1)](#alerts--risk-2-confidence-3)
	2. [Risk=Informativo, Confidence=Media (1)](#alerts--risk-0-confidence-2)
	3. [Risk=Informativo, Confidence=Baja (2)](#alerts--risk-0-confidence-1)

- [Appendix](#appendix)
	1. [Alert types](#alert-types)






## About this report



### Report parameters



#### Contexts


No contexts were selected, so all contexts were included by default.


#### Sites


The following sites were included:


* http://alibaba.zaproxy.org
* http://100.100.100.200
* http://metadata.oraclecloud.com
* http://metadata.google.internal
* http://aws.zaproxy.org
* http://169.254.169.254
* http://localhost:8080


(If no sites were selected, all sites were included by default.)


An included site must also be within one of the included contexts for its data to be included in the report.


#### Risk levels



Included:
 
 Alto, Medio, Bajo, Informativo




Excluded:
 None



#### Confidence levels



Included:
 
 
 Confirmado por Usuario, Alta, Media, Baja




Excluded:
 
 
  Confirmado por Usuario, Alta, Media, Baja, Falso positivo









## Summaries



### Alert counts by risk and confidence





This table shows the number of alerts for each level of risk and confidence included in the report.


(The percentages in brackets represent the count as a percentage of the total number of alerts included in the report, rounded to one decimal place.)










|  | Confidence |
| Confirmado por Usuario | Alta | Media | Baja | Total |
| Risk | Alto | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) |
| Medio | 0 (0,0 %) | 1 (25,0 %) | 0 (0,0 %) | 0 (0,0 %) | 1 (25,0 %) |
| Bajo | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) |
| Informativo | 0 (0,0 %) | 0 (0,0 %) | 1 (25,0 %) | 2 (50,0 %) | 3 (75,0 %) |
| Total | 0 (0,0 %) | 1 (25,0 %) | 1 (25,0 %) | 2 (50,0 %) | 4 (100%) |




### Alert counts by site and risk





This table shows, for each site for which one or more alerts were raised, the number of alerts raised at each risk level.


Alerts with a confidence level of "False Positive" have been excluded from these counts.


(The numbers in brackets are the number of alerts raised for the site at or above that risk level.)









|  | Risk |
| Alto (= Alto) | Medio (>= Medio) | Bajo (>= Bajo) | Informativo (>= Informativo) |
| Site | http://localhost:8080 | 0 (0) | 1 (1) | 0 (1) | 3 (4) |




### Alert counts by alert type





This table shows the number of alerts of each alert type, together with the alert type's risk level.


(The percentages in brackets represent each count as a percentage, rounded to one decimal place, of the total number of alerts included in this report.)


| Alert type | Risk | Count |
| --- | --- | --- |
| [CSP: Directiva Wildcard](#alert-type-0) | Medio | 1474 (36.850,0 %) |
| [Atributo de elemento HTML controlable por el usuario (XSS potencial)](#alert-type-1) | Informativo | 4333 (108.325,0 %) |
| [Divulgación de Información - Información sensible en URL](#alert-type-2) | Informativo | 47 (1.175,0 %) |
| [Petición de Autenticación Identificada](#alert-type-3) | Informativo | 2 (50,0 %) |
| Total |  | 4 |





## Alerts


1. ### 
Risk=Medio, Confidence=Alta (1)


1. #### 
http://localhost:8080 (1)
	
	
		1. ##### 
		[CSP: Directiva Wildcard](#alert-type-0) (1)
		
		
			1. 
			
			GET http://localhost:8080/OTHER/network/other/proxy.pac/?apinonce=50335d569bd1959a
			
			
			
			|  |  |
			| --- | --- |
			| Alert tags | 
				* [CWE-693](https://cwe.mitre.org/data/definitions/693.html)
				* [OWASP\_2021\_A05](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
				* [OWASP\_2017\_A06](https://owasp.org/www-project-top-ten/2017/A6_2017-Security_Misconfiguration.html) |
			| Alert description | Content Security Policy (CSP) es una capa de seguridad añadida que ayuda a detectar y mitigar ciertos tipos de ataques. Incluyendo (pero no limitado a) Cross Site Scripting (XSS), y ataques de inyección de datos. Estos ataques se utilizan, para todo, desde el robo de datos a la desfiguración de sitios o la distribución de malware. CSP proporciona un conjunto de cabeceras HTTP estándar que permiten a los propietarios de sitios web declarar las fuentes de contenido aprobadas que los navegadores deberían poder cargar en esa página. Los tipos cubiertos son JavaScript, CSS, marcos HTML, fuentes, imágenes y objetos incrustables como applets Java, ActiveX y archivos de audio y vídeo. |
			| Other info | Las siguientes directivas permiten fuentes comodín (o ancestros), no están definidas, o están definidas de forma demasiado amplia:
			frame-ancestors, form-action
			La(s) directiva(s): frame-ancestors, form-action está(n) entre las directivas que no retroceden a default-src, omitirlas/excluirlas es lo mismo que permitir cualquier cosa. |
			| Request | 
			Request line and header section (317 bytes)
			
			```
			GET http://localhost:8080/OTHER/network/other/proxy.pac/?apinonce=50335d569bd1959a HTTP/1.1
			host: localhost:8080
			user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
			pragma: no-cache
			cache-control: no-cache
			referer: http://localhost:8080
			
			
			```
			
			 
			Request body (0 bytes)
			
			 |
			| Response | 
			Status line and header section (548 bytes)
			
			```
			HTTP/1.1 200 OK
			Pragma: no-cache
			Cache-Control: no-cache, no-store, must-revalidate
			Content-Security-Policy: default-src 'none'; script-src 'self'; connect-src 'self'; child-src 'self'; img-src 'self' data:; font-src 'self' data:; style-src 'self'
			Referrer-Policy: no-referrer
			Access-Control-Allow-Methods: GET,POST,OPTIONS
			Access-Control-Allow-Headers: ZAP-Header
			X-Frame-Options: DENY
			X-XSS-Protection: 1; mode=block
			X-Content-Type-Options: nosniff
			X-Clacks-Overhead: GNU Terry Pratchett
			Content-Length: 92
			Content-Type: text/html
			
			
			```
			
			 
			Response body (92 bytes)
			
			```
			function FindProxyForURL(url, host) {
			  return "PROXY localhost:8080";
			} // End of function
			
			```
			
			 |
			| Parameter | 
			```
			Content-Security-Policy
			```
			 |
			| Evidence | 
			```
			default-src 'none'; script-src 'self'; connect-src 'self'; child-src 'self'; img-src 'self' data:; font-src 'self' data:; style-src 'self'
			```
			 |
			| Solution | Asegúrese de que su servidor web, servidor de aplicación, balanceador de carga, etc. está configurado apropiadamente para establecer la cabecera de Política de Seguridad de Contenido. |
2. ### 
Risk=Informativo, Confidence=Media (1)


	1. #### 
	http://localhost:8080 (1)
	
	
		1. ##### 
		[Divulgación de Información - Información sensible en URL](#alert-type-2) (1)
		
		
			1. 
			
			GET http://localhost:8080/UI/forcedUser/action/setForcedUser/override?apikey=ZAP&contextId=ZAP&userId=ZAP
			
			
			
			|  |  |
			| --- | --- |
			| Alert tags | 
				* [OWASP\_2021\_A01](https://owasp.org/Top10/A01_2021-Broken_Access_Control/)
				* [OWASP\_2017\_A03](https://owasp.org/www-project-top-ten/2017/A3_2017-Sensitive_Data_Exposure.html)
				* [CWE-200](https://cwe.mitre.org/data/definitions/200.html) |
			| Alert description | La solicitud parecía contener información sensible filtrada en la URL. Esto puede violar las políticas de cumplimiento de PCI y de la mayoría de las organizaciones. Puede configurar la lista de cadenas de esta comprobación para añadir o eliminar valores específicos de su entorno. |
			| Other info | La URL contiene información potencialmente sensible. La siguiente cadena fue encontrada a través del patrón: user
			userId |
			| Request | 
			Request line and header section (376 bytes)
			
			```
			GET http://localhost:8080/UI/forcedUser/action/setForcedUser/override?apikey=ZAP&contextId=ZAP&userId=ZAP HTTP/1.1
			host: localhost:8080
			user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
			pragma: no-cache
			cache-control: no-cache
			referer: http://localhost:8080/UI/forcedUser/action/setForcedUser/
			
			
			```
			
			 
			Request body (0 bytes)
			
			 |
			| Response | 
			Status line and header section (565 bytes)
			
			```
			HTTP/1.1 200 OK
			Pragma: no-cache
			Cache-Control: no-cache, no-store, must-revalidate
			Content-Security-Policy: default-src 'none'; script-src 'self'; connect-src 'self'; child-src 'self'; img-src 'self' data:; font-src 'self' data:; style-src 'self'
			Referrer-Policy: no-referrer
			Access-Control-Allow-Methods: GET,POST,OPTIONS
			Access-Control-Allow-Headers: ZAP-Header
			X-Frame-Options: DENY
			X-XSS-Protection: 1; mode=block
			X-Content-Type-Options: nosniff
			X-Clacks-Overhead: GNU Terry Pratchett
			content-length: 1348
			Content-Type: text/html; charset=UTF-8
			
			
			```
			
			 
			Response body (1348 bytes)
			
			```
			<!DOCTYPE html>
			<head>
			<title>ZAP API UI</title>
			<script src="/script.js/?v=2&apinonce=762ee573fb28da63" type="text/javascript"></script>
			</head>
			<body>
			<h1><a href="/UI/">ZAP API UI</a></h1>
			<h2><a href="/UI/forcedUser/">Componente: forcedUser</a></h2>
			<h3>Acción: setForcedUser</h3>
			Establece el usuario (ID) que se debe utilizar en el modo 'usuario forzado' para el contexto que fue proporcionado (ID)
			<form id="zapform" name="zapform" action="override"><table>
			<tr><td>Formato de Salida</td><td>
			<select id="zapapiformat">
			<option value="JSON">JSON</option>
			<option value="JSONP" disabled>JSONP</option>
			<option value="HTML">HTML</option>
			<option value="XML">XML</option>
			</select>
			</td><td></td></tr>
			<tr><td>apikey*</td><td><input id="apikey" name="apikey" value=""/></td><td></td></tr>
			<tr><td>Método de Formulario</td><td><select id="formMethod">
			<option value="GET" selected>GET</option>
			<option value="POST">POST</option>
			</select>
			</td><td></td></tr>
			<tr><td>contextId*</td><td><input id="contextId" name="contextId"/></td><td>[cadena vacía]</td></tr>
			<tr><td>userId*</td><td><input id="userId" name="userId"/></td><td>[cadena vacía]</td></tr>
			<tr><td></td><td><input id="button" value="setForcedUser" type="submit" zap-component="forcedUser" zap-type="action" zap-name="setForcedUser"/>
			</td><td></td></tr>
			</table>
			</form>
			</body>
			
			```
			
			 |
			| Parameter | 
			```
			userId
			```
			 |
			| Evidence | 
			```
			userId
			```
			 |
			| Solution | No pase información sensible en URIs. |
3. ### 
Risk=Informativo, Confidence=Baja (2)


1. #### 
http://localhost:8080 (2)
	
	
1. ##### 
[Atributo de elemento HTML controlable por el usuario (XSS potencial)](#alert-type-1) (1)
		
		
1. 
			
GET http://localhost:8080/UI/automation/view/planProgress/override?apikey=ZAP&planId=ZAP
			
			
			
|  |  |
			| --- | --- |
			| Alert tags | 
				* [OWASP\_2017\_A01](https://owasp.org/www-project-top-ten/2017/A1_2017-Injection.html)
				* [CWE-20](https://cwe.mitre.org/data/definitions/20.html)
				* [OWASP\_2021\_A03](https://owasp.org/Top10/A03_2021-Injection/) |
			| Alert description | Esta comprobación examina la entrada proporcionada por el usuario en parámetros de cadenas de consulta y datos POST para identificar dónde podrían estar controlados ciertos valores de atributos HTML. Esto proporciona detección de puntos calientes para XSS (cross-site scripting) que requerirán una revisión adicional por parte de un analista de seguridad para determinar la explotabilidad. |
			| Other info | Se han encontrado valores de atributos HTML controlados por el usuario. Intente inyectar caracteres especiales para ver si es posible XSS. La página en la siguiente URL parece incluir una entrada de usuario en una etiqueta [form] atributo [id] La entrada de usuario encontrada era:apikey=ZAP El valor controlado por el usuario era:zapform. |
			| Request | 
			Request line and header section (356 bytes)
			
```
GET http://localhost:8080/UI/automation/view/planProgress/override?apikey=ZAP&planId=ZAP HTTP/1.1
host: localhost:8080
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
pragma: no-cache
cache-control: no-cache
referer: http://localhost:8080/UI/automation/view/planProgress/
			
			
```
			
			 
Request body (0 bytes)
			
|
| Response | 
Status line and header section (565 bytes)
			
```
HTTP/1.1 200 OK
Pragma: no-cache
Cache-Control: no-cache, no-store, must-revalidate
Content-Security-Policy: default-src 'none'; script-src 'self'; connect-src 'self'; child-src 'self'; img-src 'self' data:; font-src 'self' data:; style-src 'self'
Referrer-Policy: no-referrer
Access-Control-Allow-Methods: GET,POST,OPTIONS
Access-Control-Allow-Headers: ZAP-Header
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Clacks-Overhead: GNU Terry Pratchett
content-length: 1104
Content-Type: text/html; charset=UTF-8
			
			
```
			
			 
Response body (1104 bytes)
			
```
<!DOCTYPE html>
<head>
<title>ZAP API UI</title>
<script src="/script.js/?v=2&apinonce=cabba01554ef81cf" type="text/javascript"></script>
</head>
<body>
<h1><a href="/UI/">ZAP API UI</a></h1>
<h2><a href="/UI/automation/">Componente: automation</a></h2>
<h3>Vista:planProgress</h3>
	
<form id="zapform" name="zapform" action="override"><table>
<tr><td>Formato de Salida</td><td>
<select id="zapapiformat">
<option value="JSON">JSON</option>
<option value="JSONP" disabled>JSONP</option>
<option value="HTML">HTML</option>
<option value="XML">XML</option>
</select>
</td><td></td></tr>
<tr><td>apikey*</td><td><input id="apikey" name="apikey" value=""/></td><td></td></tr>
<tr><td>Método de Formulario</td><td><select id="formMethod">
<option value="GET" selected>GET</option>
<option value="POST">POST</option>
</select>
</td><td></td></tr>
<tr><td>planId*</td><td><input id="planId" name="planId"/></td><td></td></tr>
<tr><td></td><td><input id="button" value="planProgress" type="submit" zap-component="automation" zap-type="view" zap-name="planProgress"/>
</td><td></td></tr>
</table>
</form>
</body>
			
```
			
|
| Parameter | 
```
apikey
```
|
| Solution | Válida la entrada y sanea la salida antes de escribirla en cualquier atributo HTML. |
2. ##### 
[Petición de Autenticación Identificada](#alert-type-3) (1)
		
		
1. 
			
GET http://localhost:8080/UI/network/action/setHttpProxy/override?apikey=ZAP&host=ZAP&password=ZAP&port=ZAP&realm=ZAP&username=ZAP
		
			
			
|  |  |
| --- | --- |
| Alert tags | 
|
| Alert description | La petición en cuestión se ha identificado como una petición de autenticación. El campo "Otra información" contiene un conjunto de líneas key=vvalue que identifican cualquier campo relevante. Si la solicitud está en un contexto que tiene un método de autenticación configurado como "Detección automática", esta regla cambiará la autenticación para que coincida con la petición identificada. |
| Other info | userParam=username
userValue=ZAP
passwordParam=password
referer=http://localhost:8080/UI/network/action/setHttpProxy/ |
| Request | 
Request line and header section (397 bytes)
			
```
GET http://localhost:8080/UI/network/action/setHttpProxy/override?apikey=ZAP&host=ZAP&password=ZAP&port=ZAP&realm=ZAP&username=ZAP HTTP/1.1
host: localhost:8080
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
pragma: no-cache
cache-control: no-cache
referer: http://localhost:8080/UI/network/action/setHttpProxy/
			
			
```
			
			 
Request body (0 bytes)
			
|
| Response | 
Status line and header section (565 bytes)
	
```
HTTP/1.1 200 OK
Pragma: no-cache
			Cache-Control: no-cache, no-store, must-revalidate
			Content-Security-Policy: default-src 'none'; script-src 'self'; connect-src 'self'; child-src 'self'; img-src 'self' data:; font-src 'self' data:; style-src 'self'
			Referrer-Policy: no-referrer
			Access-Control-Allow-Methods: GET,POST,OPTIONS
			Access-Control-Allow-Headers: ZAP-Header
			X-Frame-Options: DENY
			X-XSS-Protection: 1; mode=block
			X-Content-Type-Options: nosniff
			X-Clacks-Overhead: GNU Terry Pratchett
			content-length: 1551
			Content-Type: text/html; charset=UTF-8
			
			
			```
			
			 
			Response body (1551 bytes)
			
			```
			<!DOCTYPE html>
			<head>
			<title>ZAP API UI</title>
			<script src="/script.js/?v=2&apinonce=7f8b879e364d4135" type="text/javascript"></script>
			</head>
			<body>
			<h1><a href="/UI/">ZAP API UI</a></h1>
			<h2><a href="/UI/network/">Componente: network</a></h2>
			<h3>Acción: setHttpProxy</h3>
			Establece la configuración del proxy HTTP.
			<form id="zapform" name="zapform" action="override"><table>
			<tr><td>Formato de Salida</td><td>
			<select id="zapapiformat">
			<option value="JSON">JSON</option>
			<option value="JSONP" disabled>JSONP</option>
			<option value="HTML">HTML</option>
			<option value="XML">XML</option>
			</select>
			</td><td></td></tr>
			<tr><td>apikey*</td><td><input id="apikey" name="apikey" value=""/></td><td></td></tr>
			<tr><td>Método de Formulario</td><td><select id="formMethod">
			<option value="GET" selected>GET</option>
			<option value="POST">POST</option>
			</select>
			</td><td></td></tr>
			<tr><td>host*</td><td><input id="host" name="host"/></td><td>El host, nombre o dirección.</td></tr>
			<tr><td>port*</td><td><input id="port" name="port"/></td><td>El puerto.</td></tr>
			<tr><td>realm</td><td><input id="realm" name="realm"/></td><td>El reino de autenticación.</td></tr>
<tr><td>username</td><td><input id="username" name="username"/></td><td>El nombre de usuario.</td></tr>
<tr><td>password</td><td><input id="password" name="password"/></td><td>La contraseña.</td></tr>
<tr><td></td><td><input id="button" value="setHttpProxy" type="submit" zap-component="network" zap-type="action" zap-name="setHttpProxy"/>
</td><td></td></tr>
</table>
</form>
</body>
			
```
			
|
| Parameter | 
```
username
```
|
| Evidence | 
```
password
```
|
| Solution | Se trata de una alerta informativa y no de una vulnerabilidad, por lo que no hay nada que corregir. |




## Appendix



### Alert types


This section contains additional information on the types of alerts in the report.


1. #### CSP: Directiva Wildcard



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([CSP](https://www.zaproxy.org/docs/alerts/10055/))
  |
| CWE ID | [693](https://cwe.mitre.org/data/definitions/693.html) |
| WASC ID | 15 |
| Reference | 
	1. <https://www.w3.org/TR/CSP/>
	2. <https://caniuse.com/#search=content+security+policy>
	3. <https://content-security-policy.com/>
	4. <https://github.com/HtmlUnit/htmlunit-csp>
	5. <https://developers.google.com/web/fundamentals/security/csp#policy_applies_to_a_wide_variety_of_resources> |


2. #### Atributo de elemento HTML controlable por el usuario (XSS potencial)



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([Atributo de elemento HTML controlable por el usuario (XSS potencial)](https://www.zaproxy.org/docs/alerts/10031/))
  |
| CWE ID | [20](https://cwe.mitre.org/data/definitions/20.html) |
| WASC ID | 20 |
| Reference | 
	1. <https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html> |


3. #### Divulgación de Información - Información sensible en URL



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([Divulgación de Información - Información sensible en URL](https://www.zaproxy.org/docs/alerts/10024/))
  |
| CWE ID | [200](https://cwe.mitre.org/data/definitions/200.html) |
| WASC ID | 13 |


4. #### Petición de Autenticación Identificada



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([Petición de Autenticación Identificada](https://www.zaproxy.org/docs/alerts/10111/))
  |
| Reference | 
	1. <https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/> |









