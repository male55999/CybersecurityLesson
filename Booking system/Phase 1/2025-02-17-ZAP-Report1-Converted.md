




Checkmarx ZAP report 1






# Checkmarx ZAP report 1



Generated with [![The ZAP logo](2025-02-17-ZAP-Report1-/zap32x32.png)ZAP](https://zaproxy.org)
on lun 17 feb 2025, at 13:44:43



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
	2. [Risk=Medio, Confidence=Media (1)](#alerts--risk-2-confidence-2)
	3. [Risk=Bajo, Confidence=Media (2)](#alerts--risk-1-confidence-2)

- [Appendix](#appendix)
	1. [Alert types](#alert-types)






## About this report



### Report parameters



#### Contexts


No contexts were selected, so all contexts were included by default.


#### Sites


The following sites were included:


* http://localhost:8000


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
| Medio | 0 (0,0 %) | 1 (25,0 %) | 1 (25,0 %) | 0 (0,0 %) | 2 (50,0 %) |
| Bajo | 0 (0,0 %) | 0 (0,0 %) | 2 (50,0 %) | 0 (0,0 %) | 2 (50,0 %) |
| Informativo | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) | 0 (0,0 %) |
| Total | 0 (0,0 %) | 1 (25,0 %) | 3 (75,0 %) | 0 (0,0 %) | 4 (100%) |




### Alert counts by site and risk





This table shows, for each site for which one or more alerts were raised, the number of alerts raised at each risk level.


Alerts with a confidence level of "False Positive" have been excluded from these counts.


(The numbers in brackets are the number of alerts raised for the site at or above that risk level.)









|  | Risk |
| Alto (= Alto) | Medio (>= Medio) | Bajo (>= Bajo) | Informativo (>= Informativo) |
| Site | http://localhost:8000 | 0 (0) | 2 (2) | 2 (4) | 0 (4) |




### Alert counts by alert type





This table shows the number of alerts of each alert type, together with the alert type's risk level.


(The percentages in brackets represent each count as a percentage, rounded to one decimal place, of the total number of alerts included in this report.)


| Alert type | Risk | Count |
| --- | --- | --- |
| [Cabecera Content Security Policy (CSP) no configurada](#alert-type-0) | Medio | 1 (25,0 %) |
| [Falta de cabecera Anti-Clickjacking](#alert-type-1) | Medio | 1 (25,0 %) |
| [Divulgación de error de aplicación](#alert-type-2) | Bajo | 1 (25,0 %) |
| [Falta encabezado X-Content-Type-Options](#alert-type-3) | Bajo | 2 (50,0 %) |
| Total |  | 4 |





## Alerts


1. ### 
Risk=Medio, Confidence=Alta (1)


	1. #### 
	http://localhost:8000 (1)
	
	
		1. ##### 
		[Cabecera Content Security Policy (CSP) no configurada](#alert-type-0) (1)
		
		
			1. 
			
			GET http://localhost:8000/register
			
			
			
			|  |  |
			| --- | --- |
			| Alert tags | 
				* [CWE-693](https://cwe.mitre.org/data/definitions/693.html)
				* [OWASP\_2021\_A05](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
				* [OWASP\_2017\_A06](https://owasp.org/www-project-top-ten/2017/A6_2017-Security_Misconfiguration.html) |
			| Alert description | La Política de seguridad de contenido (CSP) es una capa adicional de seguridad que ayuda a detectar y mitigar ciertos tipos de ataques, incluidos Cross Site Scripting (XSS) y ataques de inyección de datos. Estos ataques se utilizan para todo, desde el robo de datos hasta la desfiguración del sitio o la distribución de malware. CSP proporciona un conjunto de encabezados HTTP estándar que permiten a los propietarios de sitios web declarar fuentes de contenido aprobadas que los navegadores deberían poder cargar en esa página; los tipos cubiertos son JavaScript, CSS, marcos HTML, fuentes, imágenes y objetos incrustados como applets de Java, ActiveX, archivos de audio y video. |
			| Request | 
			Request line and header section (237 bytes)
			
			```
			GET http://localhost:8000/register HTTP/1.1
			host: localhost:8000
			user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
			pragma: no-cache
			cache-control: no-cache
			
			
			```
			
			 
			Request body (0 bytes)
			
			 |
			| Response | 
			Status line and header section (141 bytes)
			
			```
			HTTP/1.1 200 OK
			content-type: text/html; charset=UTF-8
			vary: Accept-Encoding
			content-length: 1145
			date: Mon, 17 Feb 2025 11:22:09 GMT
			
			
			```
			
			 
			Response body (1145 bytes)
			
			```
			<!DOCTYPE html>
			<html lang="en">
			
			<head>
			    <meta charset="UTF-8">
			    <meta name="viewport" content="width=device-width, initial-scale=1.0">
			    <title>User Registration</title>
			    <link rel="stylesheet" href="/static/styles.css"> <!-- Link to external CSS -->
			</head>
			
			<body>
			    <div class="container">
			        <h1>Register</h1>
			        <form action="/register" method="POST">
			            <label for="username">Username:</label>
			            <input type="text" id="username" name="username" required><br><br>
			            <label for="password">Password:</label>
			            <input type="password" id="password" name="password" required><br><br>
			            <label for="birthdate">Birthdate:</label>
			            <input type="date" id="birthdate" name="birthdate" required><br><br>
			            <label for="role">Role:</label>
			            <select id="role" name="role">
			                <option value="reserver">Reserver</option>
			                <option value="admin">Administrator</option>
			            </select><br><br>
			            <button type="submit">Register</button>
			        </form>
			    </div>
			</body>
			
			</html>
			```
			
			 |
			| Solution | Asegúrese de que su servidor web, servidor de aplicaciones, balanceador de carga, etc. esté configurado para establecer la cabecera Content-Security-Policy. |
2. ### 
Risk=Medio, Confidence=Media (1)


	1. #### 
	http://localhost:8000 (1)
	
	
		1. ##### 
		[Falta de cabecera Anti-Clickjacking](#alert-type-1) (1)
		
		
			1. 
			
			GET http://localhost:8000/register
			
			
			
			|  |  |
			| --- | --- |
			| Alert tags | 
				* [WSTG-v42-CLNT-09](https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/11-Client-side_Testing/09-Testing_for_Clickjacking)
				* [OWASP\_2021\_A05](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
				* [OWASP\_2017\_A06](https://owasp.org/www-project-top-ten/2017/A6_2017-Security_Misconfiguration.html)
				* [CWE-1021](https://cwe.mitre.org/data/definitions/1021.html) |
			| Alert description | La respuesta no protege contra ataques de "ClickJacking". Debes incluir Content-Security-Policy con la directiva "frame-ancestors" o X-Frame-Options. |
			| Request | 
			Request line and header section (237 bytes)
			
			```
			GET http://localhost:8000/register HTTP/1.1
			host: localhost:8000
			user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
			pragma: no-cache
			cache-control: no-cache
			
			
			```
			
			 
			Request body (0 bytes)
			
			 |
			| Response | 
			Status line and header section (141 bytes)
			
			```
			HTTP/1.1 200 OK
			content-type: text/html; charset=UTF-8
			vary: Accept-Encoding
			content-length: 1145
			date: Mon, 17 Feb 2025 11:22:09 GMT
			
			
			```
			
			 
			Response body (1145 bytes)
			
			```
			<!DOCTYPE html>
			<html lang="en">
			
			<head>
			    <meta charset="UTF-8">
			    <meta name="viewport" content="width=device-width, initial-scale=1.0">
			    <title>User Registration</title>
			    <link rel="stylesheet" href="/static/styles.css"> <!-- Link to external CSS -->
			</head>
			
			<body>
			    <div class="container">
			        <h1>Register</h1>
			        <form action="/register" method="POST">
			            <label for="username">Username:</label>
			            <input type="text" id="username" name="username" required><br><br>
			            <label for="password">Password:</label>
			            <input type="password" id="password" name="password" required><br><br>
			            <label for="birthdate">Birthdate:</label>
			            <input type="date" id="birthdate" name="birthdate" required><br><br>
			            <label for="role">Role:</label>
			            <select id="role" name="role">
			                <option value="reserver">Reserver</option>
			                <option value="admin">Administrator</option>
			            </select><br><br>
			            <button type="submit">Register</button>
			        </form>
			    </div>
			</body>
			
			</html>
			```
			
			 |
			| Parameter | 
			```
			x-frame-options
			```
			 |
			| Solution | Los navegadores web modernos admiten las cabeceras HTTP Content-Security-Policy y X-Frame-Options. Asegúrese de que una de ellas está configurada en todas las páginas web devueltas por su sitio/aplicación.
			Si espera que la página esté enmarcada solo por páginas en su servidor (por ejemplo, si forma parte de un FRAMESET), utilice SAMEORIGIN; de lo contrario, si no espera que la página esté enmarcada, utilice DENY. Alternativamente, considere implementar la directiva "frame-ancestors" de la Política de Seguridad de Contenidos. |
3. ### 
Risk=Bajo, Confidence=Media (2)


	1. #### 
	http://localhost:8000 (2)
	
	
		1. ##### 
		[Divulgación de error de aplicación](#alert-type-2) (1)
		
		
			1. 
			
			POST http://localhost:8000/register
			
			
			
			|  |  |
			| --- | --- |
			| Alert tags | 
				* [WSTG-v42-ERRH-02](https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/08-Testing_for_Error_Handling/02-Testing_for_Stack_Traces)
				* [WSTG-v42-ERRH-01](https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/08-Testing_for_Error_Handling/01-Testing_For_Improper_Error_Handling)
				* [OWASP\_2021\_A05](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
				* [OWASP\_2017\_A06](https://owasp.org/www-project-top-ten/2017/A6_2017-Security_Misconfiguration.html)
				* [CWE-200](https://cwe.mitre.org/data/definitions/200.html) |
			| Alert description | Esta página contiene un mensaje de error/advertencia que podría revelar información sensible como la ubicación del archivo que produjo la excepción no controlada. Esta información puede ser usada para lanzas futuros ataques contra la aplicación web. La alerta podría ser una falso positivo si el mensaje de error es encontrado dentro de una página de documentación. |
			| Request | 
			Request line and header section (348 bytes)
			
			```
			POST http://localhost:8000/register HTTP/1.1
			host: localhost:8000
			user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
			pragma: no-cache
			cache-control: no-cache
			content-type: application/x-www-form-urlencoded
			referer: http://localhost:8000/register
			content-length: 57
			
			
			```
			
			 
			Request body (57 bytes)
			
			```
			username=ZAP&password=ZAP&birthdate=2025-02-17&role=admin
			```
			
			 |
			| Response | 
			Status line and header section (159 bytes)
			
			```
			HTTP/1.1 500 Internal Server Error
			content-type: text/plain; charset=UTF-8
			vary: Accept-Encoding
			content-length: 25
			date: Mon, 17 Feb 2025 11:22:09 GMT
			
			
			```
			
			 
			Response body (25 bytes)
			
			```
			Error during registration
			```
			
			 |
			| Evidence | 
			```
			HTTP/1.1 500 Internal Server Error
			```
			 |
			| Solution | Revisar el código de fuente de esta página. Implementación de páginas de error personalizadas. Considerar implementar un mecanismos para proveer una única referencia/identificación de error para el cliente (navegador) mientras insertando los detalles en el sitio del navegador y no exponiéndolos al usuario. |
		2. ##### 
		[Falta encabezado X-Content-Type-Options](#alert-type-3) (1)
		
		
			1. 
			
			GET http://localhost:8000/static/styles.css
			
			
			
			|  |  |
			| --- | --- |
			| Alert tags | 
				* [CWE-693](https://cwe.mitre.org/data/definitions/693.html)
				* [OWASP\_2021\_A05](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
				* [OWASP\_2017\_A06](https://owasp.org/www-project-top-ten/2017/A6_2017-Security_Misconfiguration.html) |
			| Alert description | La cabecera Anti-MIME-Sniffing X-Content-Type-Options no se ha establecido en 'nosniff'. Esto permite que las versiones anteriores de Internet Explorer y Chrome realicen MIME-sniffing en el cuerpo de la respuesta, lo que puede provocar que el cuerpo dé la respuesta se interprete y se muestre como un tipo de contenido distinto del tipo de contenido declarado. Las versiones actuales (principios de 2014) y heredadas de Firefox utilizarán el tipo de contenido declarado (si se establece uno), en lugar de realizar MIME-sniffing. |
			| Other info | Este problema aún se aplica a las páginas de tipo error (401, 403, 500, etc.), ya que esas páginas a menudo se ven afectadas por problemas de inyección, en cuyo caso aún existe la preocupación de que los navegadores husmeen las páginas lejos de su tipo de contenido real.
			En el umbral «Alto» esta regla de análisis no alertará sobre respuestas de error del cliente o servidor. |
			| Request | 
			Request line and header section (287 bytes)
			
			```
			GET http://localhost:8000/static/styles.css HTTP/1.1
			host: localhost:8000
			user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
			pragma: no-cache
			cache-control: no-cache
			referer: http://localhost:8000/register
			
			
			```
			
			 
			Request body (0 bytes)
			
			 |
			| Response | 
			Status line and header section (140 bytes)
			
			```
			HTTP/1.1 200 OK
			content-type: text/css; charset=utf-8
			vary: Accept-Encoding
			date: Mon, 17 Feb 2025 11:22:09 GMT
			content-length: 1239
			
			
			```
			
			 
			Response body (1239 bytes)
			
			```
			body {
			    font-family: Arial, sans-serif;
			    background-color: #f4f4f9;
			    display: flex;
			    justify-content: center;
			    align-items: center;
			    height: 100vh;
			    margin: 0;
			}
			
			.container {
			    background-color: white;
			    padding: 2rem;
			    border-radius: 8px;
			    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
			    width: 100%;
			    max-width: 400px;
			}
			
			h1 {
			    text-align: center;
			    color: #333;
			}
			
			label {
			    font-weight: bold;
			    color: #555;
			    display: block;
			    margin-bottom: 0.5rem;
			}
			
			input,
			select {
			    width: 100%;
			    padding: 0.8rem;
			    margin-bottom: 1rem;
			    border: 1px solid #ccc;
			    border-radius: 4px;
			    box-sizing: border-box;
			    font-size: 1rem;
			}
			
			button {
			    width: 100%;
			    background-color: #007bff;
			    color: white;
			    padding: 0.8rem;
			    border: none;
			    border-radius: 4px;
			    font-size: 1rem;
			    cursor: pointer;
			}
			
			button:hover {
			    background-color: #0056b3;
			}
			
			.error {
			    color: red;
			    font-size: 0.9rem;
			}
			
			.success {
			    color: green;
			    font-size: 0.9rem;
			}
			
			/* Responsive design for mobile screens */
			@media (max-width: 600px) {
			    .container {
			        padding: 1.5rem;
			        width: 100%;
			    }
			}
			```
			
			 |
			| Parameter | 
			```
			x-content-type-options
			```
			 |
			| Solution | Asegúrese de que la aplicación/servidor web establece el encabezado Content-Type adecuadamente, y que establece el encabezado X-Content-Type-Options a 'nosniff' para todas las páginas web.
			Si es posible, asegúrese de que el usuario final utiliza un navegador web moderno y compatible con los estándares que no realiza MIME-sniffing en absoluto, o que puede ser dirigido por la aplicación web/servidor web para que no realice MIME-sniffing. |




## Appendix



### Alert types


This section contains additional information on the types of alerts in the report.


1. #### Cabecera Content Security Policy (CSP) no configurada



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([Cabecera Content Security Policy (CSP) no configurada](https://www.zaproxy.org/docs/alerts/10038/))
  |
| CWE ID | [693](https://cwe.mitre.org/data/definitions/693.html) |
| WASC ID | 15 |
| Reference | 
	1. <https://developer.mozilla.org/en-US/docs/Web/Security/CSP/Introducing_Content_Security_Policy>
	2. <https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html>
	3. <https://www.w3.org/TR/CSP/>
	4. <https://w3c.github.io/webappsec-csp/>
	5. <https://web.dev/articles/csp>
	6. <https://caniuse.com/#feat=contentsecuritypolicy>
	7. <https://content-security-policy.com/> |


2. #### Falta de cabecera Anti-Clickjacking



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([Cabecera Anti-Clickjacking](https://www.zaproxy.org/docs/alerts/10020/))
  |
| CWE ID | [1021](https://cwe.mitre.org/data/definitions/1021.html) |
| WASC ID | 15 |
| Reference | 
	1. <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options> |


3. #### Divulgación de error de aplicación



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([Divulgación de error de aplicación](https://www.zaproxy.org/docs/alerts/90022/))
  |
| CWE ID | [200](https://cwe.mitre.org/data/definitions/200.html) |
| WASC ID | 13 |


4. #### Falta encabezado X-Content-Type-Options



|  |  |
| --- | --- |
| Source | raised by a passive scanner ([Falta encabezado X-Content-Type-Options](https://www.zaproxy.org/docs/alerts/10021/))
  |
| CWE ID | [693](https://cwe.mitre.org/data/definitions/693.html) |
| WASC ID | 15 |
| Reference | 
	1. <https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85)>
	2. <https://owasp.org/www-community/Security_Headers> |









