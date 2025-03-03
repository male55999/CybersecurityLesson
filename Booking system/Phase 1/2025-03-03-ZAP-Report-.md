<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Checkmarx ZAP report 1</title>
<link
	href="2025-03-03-ZAP-Report-/normalize/normalize.css" rel="stylesheet">
<link
	href="2025-03-03-ZAP-Report-/themes//main.css" rel="stylesheet">
<link
	href="2025-03-03-ZAP-Report-/themes//colors.css" rel="stylesheet">
</head>
<body>
	<header>
		<h1>Checkmarx ZAP report 1</h1>
		<p>
			<span>Generated with</span> <a href="https://zaproxy.org"><img
				src="2025-03-03-ZAP-Report-/zap32x32.png" alt="The ZAP logo" class="zap-logo">ZAP</a>
			<span>on lun 3 mar 2025, at 17:37:46</span>
		</p>
		<p>ZAP Versión: 2.16.0</p>
		<p>
			ZAP by <a href="https://checkmarx.com/">Checkmarx</a>
		</p>
	</header>

	<main>

		<section id="contents" class="contents">
			<h2>Contents</h2>
			<nav>
				<ol>
					<li><a
						href="#about-this-report">About this report</a>
						<ol>
							
							<li><a
								href="#report-parameters">Report parameters</a></li>
						</ol></li>
					<data-th-block>
					<li><a
						href="#summaries">Summaries</a>
						<ol>
							<li><a
								href="#risk-confidence-counts">Alert counts by risk and confidence</a></li>
							<li><a
								href="#site-risk-counts">Alert counts by site and risk</a></li>
							<li><a
								href="#alert-type-counts">Alert counts by alert type</a></li>
						</ol></li>
					<li><a
						href="#alerts">Alerts</a>
						<ol>
							
							 
							
							
							
							
							<li><a
								href="#alerts--risk-2-confidence-3"><span>Risk</span>=<span
									class="risk-level">Medio</span>, <span>Confidence</span>=<span
									class="confidence-level">Alta</span> <span>(1)</span></a></li>
							
							
							
							
							  
							 
							
							
							
							
							
							
							<li><a
								href="#alerts--risk-0-confidence-2"><span>Risk</span>=<span
									class="risk-level">Informativo</span>, <span>Confidence</span>=<span
									class="confidence-level">Media</span> <span>(1)</span></a></li>
							
							<li><a
								href="#alerts--risk-0-confidence-1"><span>Risk</span>=<span
									class="risk-level">Informativo</span>, <span>Confidence</span>=<span
									class="confidence-level">Baja</span> <span>(2)</span></a></li>
							  
						</ol></li>
					<li><a
						href="#appendix">Appendix</a>
						<ol>
							<li><a
								href="#alert-types">Alert types</a></li>
						</ol></li>
					</data-th-block>
				</ol>
			</nav>
		</section>

		<section
			id="about-this-report" class="about-this-report">
			<h2>About this report</h2>

			

			<section
				id="report-parameters">
				<h3>Report parameters</h3>
				<div class="report-parameters--container">
					<h4>Contexts</h4>
					
					
					<p>No contexts were selected, so all contexts were included by default.</p>
					  

					<h4>Sites</h4>
					
					<p>The following sites were included:</p>
					<ul class="sites-list">
						<li><span class="site">http://alibaba.zaproxy.org</span></li>
						<li><span class="site">http://100.100.100.200</span></li>
						<li><span class="site">http://metadata.oraclecloud.com</span></li>
						<li><span class="site">http://metadata.google.internal</span></li>
						<li><span class="site">http://aws.zaproxy.org</span></li>
						<li><span class="site">http://169.254.169.254</span></li>
						<li><span class="site">http://localhost:8080</span></li>
					</ul>
					
					<p>(If no sites were selected, all sites were included by default.)</p>
					<p>An included site must also be within one of the included contexts for its data to be included in the report.</p>

					<h4>Risk levels</h4>
					<p>
						<span>Included</span>:
						 
						<span class="included-risk-codes"><span class="risk-level">Alto</span>, <span class="risk-level">Medio</span>, <span class="risk-level">Bajo</span>, <span class="risk-level">Informativo</span></span>
					</p>
					<p>
						<span>Excluded</span>:
						 <span>None</span>
						
					</p>

					<h4>Confidence levels</h4>
					<p>
						<span>Included</span>:
						
						
						<span class="included-confidence-codes"><span class="confidence-level">Confirmado por Usuario</span>, <span class="confidence-level">Alta</span>, <span class="confidence-level">Media</span>, <span class="confidence-level">Baja</span></span>
					</p>
					<p>
						<span>Excluded</span>:
						
						
						<span class="included-confidence-codes"> <span class="confidence-level">Confirmado por Usuario</span>, <span class="confidence-level">Alta</span>, <span class="confidence-level">Media</span>, <span class="confidence-level">Baja</span>, <span class="confidence-level">Falso positivo</span></span>
					</p>
				</div>
			</section>
		</section>

		
		<section>
			
		</section>
		
		<section id="summaries" class="summaries">
			<h2>Summaries</h2>

			<section
				id="risk-confidence-counts">
				<h3>Alert counts by risk and confidence</h3>
				<table class="risk-confidence-counts-table">
					<caption>
						<p>This table shows the number of alerts for each level of risk and confidence included in the report.</p>
						<p>(The percentages in brackets represent the count as a percentage of the total number of alerts included in the report, rounded to one decimal place.)</p>
					</caption>
					<colgroup>
						<col>
						<col>
					</colgroup>
					<colgroup>
						<col
							style="width: 14.0%"><col
							style="width: 14.0%"><col
							style="width: 14.0%"><col
							style="width: 14.0%">
						<col style="width: 14.0%">
					</colgroup>
					<thead>
						<tr>
							<td colspan="2" rowspan="2"></td>
							<th scope="colgroup"
								colspan="5">Confidence</th>
						</tr>
						<tr>
							<th scope="col">Confirmado por Usuario</th>
							<th scope="col">Alta</th>
							<th scope="col">Media</th>
							<th scope="col">Baja</th>
							<th scope="col">Total</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<th scope="rowgroup"
								rowspan="5">Risk</th>
							<th scope="row">Alto</th>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span class="additional-info-percentages">(0,0 %)</span></td>
						</tr>
						<tr>
							
							<th scope="row">Medio</th>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>1</span><br> <span
								class="additional-info-percentages">(25,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>1</span><br> <span class="additional-info-percentages">(25,0 %)</span></td>
						</tr>
						<tr>
							
							<th scope="row">Bajo</th>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span class="additional-info-percentages">(0,0 %)</span></td>
						</tr>
						<tr>
							
							<th scope="row">Informativo</th>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>1</span><br> <span
								class="additional-info-percentages">(25,0 %)</span></td>
							<td><span>2</span><br> <span
								class="additional-info-percentages">(50,0 %)</span></td>
							<td><span>3</span><br> <span class="additional-info-percentages">(75,0 %)</span></td>
						</tr>
						<tr>
							<th scope="row">Total</th>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0,0 %)</span></td>
							<td><span>1</span><br> <span
								class="additional-info-percentages">(25,0 %)</span></td>
							<td><span>1</span><br> <span
								class="additional-info-percentages">(25,0 %)</span></td>
							<td><span>2</span><br> <span
								class="additional-info-percentages">(50,0 %)</span></td>
							<td><span>4</span><br> <span
								class="additional-info-percentages">(100%)</span></td>
						</tr>
					</tbody>
				</table>
			</section>

			<section
				id="site-risk-counts">
				<h3>Alert counts by site and risk</h3>
				<table class="site-risk-counts-table">
					<caption>
						<p>This table shows, for each site for which one or more alerts were raised, the number of alerts raised at each risk level.</p>
						<p>Alerts with a confidence level of &quot;False Positive&quot; have been excluded from these counts.</p>
						<p>(The numbers in brackets are the number of alerts raised for the site at or above that risk level.)</p>
					</caption>
					<colgroup>
						<col>
						<col>
					</colgroup>
					<colgroup>
						<col
							style="width: 16.25%"><col
							style="width: 16.25%"><col
							style="width: 16.25%"><col
							style="width: 16.25%">
					</colgroup>
					<thead>
						<tr>
							<td colspan="2" rowspan="2"></td>
							<th scope="colgroup" colspan="4">Risk</th>
						</tr>
						<tr>
							<th scope="col">
								<span>Alto</span><br>  <span
									class="additional-info-percentages">(= Alto)</span>  
							</th>
							<th scope="col">
								<span>Medio</span><br>   <span
									class="additional-info-percentages">(&gt;= Medio)</span> 
							</th>
							<th scope="col">
								<span>Bajo</span><br>   <span
									class="additional-info-percentages">(&gt;= Bajo)</span> 
							</th>
							<th scope="col">
								<span>Informativo</span><br>   <span
									class="additional-info-percentages">(&gt;= Informativo)</span> 
							</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<th scope="rowgroup"
								rowspan="1">Site</th>
							<th scope="row">http://localhost:8080</th>
							
							<td><span>0</span><br> <span
								class="additional-info-percentages">(0)</span></td>
							<td><span>1</span><br> <span
								class="additional-info-percentages">(1)</span></td>
							<td><span>0</span><br> <span
								class="additional-info-percentages">(1)</span></td>
							<td><span>3</span><br> <span
								class="additional-info-percentages">(4)</span></td>
							
						</tr>
					</tbody>
				</table>
			</section>

			<section
				id="alert-type-counts">
				<h3>Alert counts by alert type</h3>
				<table class="alert-type-counts-table">
					<caption>
						<p>This table shows the number of alerts of each alert type, together with the alert type&#39;s risk level.</p>
						<p>(The percentages in brackets represent each count as a percentage, rounded to one decimal place, of the total number of alerts included in this report.)</p>
					</caption>
					<thead>
						<tr>
							<th scope="col">Alert type</th>
							<th scope="col">Risk</th>
							<th scope="col">Count</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<th scope="row"><a
								href="#alert-type-0">CSP: Directiva Wildcard</a></th>
							<td class="risk-level">Medio</td>
							<td><span>1474</span><br> <span
								class="additional-info-percentages">(36.850,0 %)</span></td>
						</tr>
						<tr>
							<th scope="row"><a
								href="#alert-type-1">Atributo de elemento HTML controlable por el usuario (XSS potencial)</a></th>
							<td class="risk-level">Informativo</td>
							<td><span>4333</span><br> <span
								class="additional-info-percentages">(108.325,0 %)</span></td>
						</tr>
						<tr>
							<th scope="row"><a
								href="#alert-type-2">Divulgación de Información - Información sensible en URL</a></th>
							<td class="risk-level">Informativo</td>
							<td><span>47</span><br> <span
								class="additional-info-percentages">(1.175,0 %)</span></td>
						</tr>
						<tr>
							<th scope="row"><a
								href="#alert-type-3">Petición de Autenticación Identificada</a></th>
							<td class="risk-level">Informativo</td>
							<td><span>2</span><br> <span
								class="additional-info-percentages">(50,0 %)</span></td>
						</tr>
					</tbody>
					<tfoot>
						<tr>
							<th scope="row">Total</th>
							<td></td>
							<td>4</td>
						</tr>
					</tfoot>
				</table>
			</section>
		</section>

		<section id="alerts" class="alerts">
			<h2>Alerts</h2>
			<ol>
				
				 
				 
				
				
				<li id="alerts--risk-2-confidence-3">
					<h3>
						<span>Risk</span>=<span
							class="risk-level">Medio</span>, <span>Confidence</span>=<span
							class="confidence-level">Alta</span> <span>(1)</span>
					</h3>
					<ol>
						
						<li class="alerts--site-li">
							<h4>
								<span class="site">http://localhost:8080</span> <span>(1)</span>
							</h4>
							<ol>
								
								<li>
									<h5>
										<a
											href="#alert-type-0">CSP: Directiva Wildcard</a> <span>(1)</span>
									</h5>
									<ol>
										<li><details>
												<summary>
													<span class="request-method-n-url">GET http://localhost:8080/OTHER/network/other/proxy.pac/?apinonce=50335d569bd1959a</span>
												</summary>
												
<table class="alerts-table">
	<tr>
		<th scope="row">Alert tags</th>
		<td>
			<ul class="alert-tags-list">
				<li>
					<span><a href="https://cwe.mitre.org/data/definitions/693.html">CWE-693</a></span> 
				</li>
				<li>
					<span><a href="https://owasp.org/Top10/A05_2021-Security_Misconfiguration/">OWASP_2021_A05</a></span> 
				</li>
				<li>
					<span><a href="https://owasp.org/www-project-top-ten/2017/A6_2017-Security_Misconfiguration.html">OWASP_2017_A06</a></span> 
				</li>
			</ul>
		</td>
	</tr>
	<tr>
		<th scope="row">Alert description</th>
		<td> 
<p>Content Security Policy (CSP) es una capa de seguridad añadida que ayuda a detectar y mitigar ciertos tipos de ataques. Incluyendo (pero no limitado a) Cross Site Scripting (XSS), y ataques de inyección de datos. Estos ataques se utilizan, para todo, desde el robo de datos a la desfiguración de sitios o la distribución de malware. CSP proporciona un conjunto de cabeceras HTTP estándar que permiten a los propietarios de sitios web declarar las fuentes de contenido aprobadas que los navegadores deberían poder cargar en esa página. Los tipos cubiertos son JavaScript, CSS, marcos HTML, fuentes, imágenes y objetos incrustables como applets Java, ActiveX y archivos de audio y vídeo.</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Other info</th>
		<td> 
<p>Las siguientes directivas permiten fuentes comodín (o ancestros), no están definidas, o están definidas de forma demasiado amplia:</p>

<p>frame-ancestors, form-action</p>

<p>La(s) directiva(s): frame-ancestors, form-action está(n) entre las directivas que no retroceden a default-src, omitirlas/excluirlas es lo mismo que permitir cualquier cosa.</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Request</th>
		<td><details open="open">
				<summary>Request line and header section (317 bytes)</summary>
				
				<pre><code>GET http://localhost:8080/OTHER/network/other/proxy.pac/?apinonce=50335d569bd1959a HTTP/1.1
host: localhost:8080
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
pragma: no-cache
cache-control: no-cache
referer: http://localhost:8080

</code></pre>
				
				
			</details> <details class="request-body" open="open">
				<summary>Request body (0 bytes)</summary>
				
				<pre><code></code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Response</th>
		<td><details open="open">
				<summary>Status line and header section (548 bytes)</summary>
				
				<pre><code>HTTP/1.1 200 OK
Pragma: no-cache
Cache-Control: no-cache, no-store, must-revalidate
Content-Security-Policy: default-src &#39;none&#39;; script-src &#39;self&#39;; connect-src &#39;self&#39;; child-src &#39;self&#39;; img-src &#39;self&#39; data:; font-src &#39;self&#39; data:; style-src &#39;self&#39;
Referrer-Policy: no-referrer
Access-Control-Allow-Methods: GET,POST,OPTIONS
Access-Control-Allow-Headers: ZAP-Header
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Clacks-Overhead: GNU Terry Pratchett
Content-Length: 92
Content-Type: text/html

</code></pre>
				
				
			</details> <details class="response-body" open="open">
				<summary>Response body (92 bytes)</summary>
				
				<pre><code>function FindProxyForURL(url, host) {
  return &quot;PROXY localhost:8080&quot;;
} // End of function
</code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Parameter</th>
		<td><pre><code>Content-Security-Policy</code></pre></td>
	</tr>
	
	<tr>
		<th scope="row">Evidence</th>
		<td><pre><code>default-src &#39;none&#39;; script-src &#39;self&#39;; connect-src &#39;self&#39;; child-src &#39;self&#39;; img-src &#39;self&#39; data:; font-src &#39;self&#39; data:; style-src &#39;self&#39;</code></pre></td>
	</tr>
	<tr>
		<th scope="row">Solution</th>
		<td> 
<p>Asegúrese de que su servidor web, servidor de aplicación, balanceador de carga, etc. está configurado apropiadamente para establecer la cabecera de Política de Seguridad de Contenido.</p>
 </td>
	</tr>
</table>

											</details></li>
									</ol>
								</li>
								
							</ol>
						</li>
						
					</ol>
				</li>
				
				
				
				
				  
				 
				 
				
				
				
				
				<li id="alerts--risk-0-confidence-2">
					<h3>
						<span>Risk</span>=<span
							class="risk-level">Informativo</span>, <span>Confidence</span>=<span
							class="confidence-level">Media</span> <span>(1)</span>
					</h3>
					<ol>
						
						<li class="alerts--site-li">
							<h4>
								<span class="site">http://localhost:8080</span> <span>(1)</span>
							</h4>
							<ol>
								
								<li>
									<h5>
										<a
											href="#alert-type-2">Divulgación de Información - Información sensible en URL</a> <span>(1)</span>
									</h5>
									<ol>
										<li><details>
												<summary>
													<span class="request-method-n-url">GET http://localhost:8080/UI/forcedUser/action/setForcedUser/override?apikey=ZAP&amp;contextId=ZAP&amp;userId=ZAP</span>
												</summary>
												
<table class="alerts-table">
	<tr>
		<th scope="row">Alert tags</th>
		<td>
			<ul class="alert-tags-list">
				<li>
					<span><a href="https://owasp.org/Top10/A01_2021-Broken_Access_Control/">OWASP_2021_A01</a></span> 
				</li>
				<li>
					<span><a href="https://owasp.org/www-project-top-ten/2017/A3_2017-Sensitive_Data_Exposure.html">OWASP_2017_A03</a></span> 
				</li>
				<li>
					<span><a href="https://cwe.mitre.org/data/definitions/200.html">CWE-200</a></span> 
				</li>
			</ul>
		</td>
	</tr>
	<tr>
		<th scope="row">Alert description</th>
		<td> 
<p>La solicitud parecía contener información sensible filtrada en la URL. Esto puede violar las políticas de cumplimiento de PCI y de la mayoría de las organizaciones. Puede configurar la lista de cadenas de esta comprobación para añadir o eliminar valores específicos de su entorno.</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Other info</th>
		<td> 
<p>La URL contiene información potencialmente sensible. La siguiente cadena fue encontrada a través del patrón: user</p>

<p>userId</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Request</th>
		<td><details open="open">
				<summary>Request line and header section (376 bytes)</summary>
				
				<pre><code>GET http://localhost:8080/UI/forcedUser/action/setForcedUser/override?apikey=ZAP&amp;contextId=ZAP&amp;userId=ZAP HTTP/1.1
host: localhost:8080
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
pragma: no-cache
cache-control: no-cache
referer: http://localhost:8080/UI/forcedUser/action/setForcedUser/

</code></pre>
				
				
			</details> <details class="request-body" open="open">
				<summary>Request body (0 bytes)</summary>
				
				<pre><code></code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Response</th>
		<td><details open="open">
				<summary>Status line and header section (565 bytes)</summary>
				
				<pre><code>HTTP/1.1 200 OK
Pragma: no-cache
Cache-Control: no-cache, no-store, must-revalidate
Content-Security-Policy: default-src &#39;none&#39;; script-src &#39;self&#39;; connect-src &#39;self&#39;; child-src &#39;self&#39;; img-src &#39;self&#39; data:; font-src &#39;self&#39; data:; style-src &#39;self&#39;
Referrer-Policy: no-referrer
Access-Control-Allow-Methods: GET,POST,OPTIONS
Access-Control-Allow-Headers: ZAP-Header
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Clacks-Overhead: GNU Terry Pratchett
content-length: 1348
Content-Type: text/html; charset=UTF-8

</code></pre>
				
				
			</details> <details class="response-body" open="open">
				<summary>Response body (1348 bytes)</summary>
				
				<pre><code>&lt;!DOCTYPE html&gt;
&lt;head&gt;
&lt;title&gt;ZAP API UI&lt;/title&gt;
&lt;script src=&quot;/script.js/?v=2&amp;apinonce=762ee573fb28da63&quot; type=&quot;text/javascript&quot;&gt;&lt;/script&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;h1&gt;&lt;a href=&quot;/UI/&quot;&gt;ZAP API UI&lt;/a&gt;&lt;/h1&gt;
&lt;h2&gt;&lt;a href=&quot;/UI/forcedUser/&quot;&gt;Componente: forcedUser&lt;/a&gt;&lt;/h2&gt;
&lt;h3&gt;Acción: setForcedUser&lt;/h3&gt;
Establece el usuario (ID) que se debe utilizar en el modo &#39;usuario forzado&#39; para el contexto que fue proporcionado (ID)
&lt;form id=&quot;zapform&quot; name=&quot;zapform&quot; action=&quot;override&quot;&gt;&lt;table&gt;
&lt;tr&gt;&lt;td&gt;Formato de Salida&lt;/td&gt;&lt;td&gt;
&lt;select id=&quot;zapapiformat&quot;&gt;
&lt;option value=&quot;JSON&quot;&gt;JSON&lt;/option&gt;
&lt;option value=&quot;JSONP&quot; disabled&gt;JSONP&lt;/option&gt;
&lt;option value=&quot;HTML&quot;&gt;HTML&lt;/option&gt;
&lt;option value=&quot;XML&quot;&gt;XML&lt;/option&gt;
&lt;/select&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;apikey*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;apikey&quot; name=&quot;apikey&quot; value=&quot;&quot;/&gt;&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;Método de Formulario&lt;/td&gt;&lt;td&gt;&lt;select id=&quot;formMethod&quot;&gt;
&lt;option value=&quot;GET&quot; selected&gt;GET&lt;/option&gt;
&lt;option value=&quot;POST&quot;&gt;POST&lt;/option&gt;
&lt;/select&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;contextId*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;contextId&quot; name=&quot;contextId&quot;/&gt;&lt;/td&gt;&lt;td&gt;[cadena vacía]&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;userId*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;userId&quot; name=&quot;userId&quot;/&gt;&lt;/td&gt;&lt;td&gt;[cadena vacía]&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;button&quot; value=&quot;setForcedUser&quot; type=&quot;submit&quot; zap-component=&quot;forcedUser&quot; zap-type=&quot;action&quot; zap-name=&quot;setForcedUser&quot;/&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;/table&gt;
&lt;/form&gt;
&lt;/body&gt;
</code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Parameter</th>
		<td><pre><code>userId</code></pre></td>
	</tr>
	
	<tr>
		<th scope="row">Evidence</th>
		<td><pre><code>userId</code></pre></td>
	</tr>
	<tr>
		<th scope="row">Solution</th>
		<td> 
<p>No pase información sensible en URIs.</p>
 </td>
	</tr>
</table>

											</details></li>
									</ol>
								</li>
								
							</ol>
						</li>
						
					</ol>
				</li>
				
				<li id="alerts--risk-0-confidence-1">
					<h3>
						<span>Risk</span>=<span
							class="risk-level">Informativo</span>, <span>Confidence</span>=<span
							class="confidence-level">Baja</span> <span>(2)</span>
					</h3>
					<ol>
						
						<li class="alerts--site-li">
							<h4>
								<span class="site">http://localhost:8080</span> <span>(2)</span>
							</h4>
							<ol>
								
								<li>
									<h5>
										<a
											href="#alert-type-1">Atributo de elemento HTML controlable por el usuario (XSS potencial)</a> <span>(1)</span>
									</h5>
									<ol>
										<li><details>
												<summary>
													<span class="request-method-n-url">GET http://localhost:8080/UI/automation/view/planProgress/override?apikey=ZAP&amp;planId=ZAP</span>
												</summary>
												
<table class="alerts-table">
	<tr>
		<th scope="row">Alert tags</th>
		<td>
			<ul class="alert-tags-list">
				<li>
					<span><a href="https://owasp.org/www-project-top-ten/2017/A1_2017-Injection.html">OWASP_2017_A01</a></span> 
				</li>
				<li>
					<span><a href="https://cwe.mitre.org/data/definitions/20.html">CWE-20</a></span> 
				</li>
				<li>
					<span><a href="https://owasp.org/Top10/A03_2021-Injection/">OWASP_2021_A03</a></span> 
				</li>
			</ul>
		</td>
	</tr>
	<tr>
		<th scope="row">Alert description</th>
		<td> 
<p>Esta comprobación examina la entrada proporcionada por el usuario en parámetros de cadenas de consulta y datos POST para identificar dónde podrían estar controlados ciertos valores de atributos HTML. Esto proporciona detección de puntos calientes para XSS (cross-site scripting) que requerirán una revisión adicional por parte de un analista de seguridad para determinar la explotabilidad.</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Other info</th>
		<td> 
<p>Se han encontrado valores de atributos HTML controlados por el usuario. Intente inyectar caracteres especiales para ver si es posible XSS. La página en la siguiente URL parece incluir una entrada de usuario en una etiqueta [form] atributo [id] La entrada de usuario encontrada era:apikey=ZAP El valor controlado por el usuario era:zapform.</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Request</th>
		<td><details open="open">
				<summary>Request line and header section (356 bytes)</summary>
				
				<pre><code>GET http://localhost:8080/UI/automation/view/planProgress/override?apikey=ZAP&amp;planId=ZAP HTTP/1.1
host: localhost:8080
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
pragma: no-cache
cache-control: no-cache
referer: http://localhost:8080/UI/automation/view/planProgress/

</code></pre>
				
				
			</details> <details class="request-body" open="open">
				<summary>Request body (0 bytes)</summary>
				
				<pre><code></code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Response</th>
		<td><details open="open">
				<summary>Status line and header section (565 bytes)</summary>
				
				<pre><code>HTTP/1.1 200 OK
Pragma: no-cache
Cache-Control: no-cache, no-store, must-revalidate
Content-Security-Policy: default-src &#39;none&#39;; script-src &#39;self&#39;; connect-src &#39;self&#39;; child-src &#39;self&#39;; img-src &#39;self&#39; data:; font-src &#39;self&#39; data:; style-src &#39;self&#39;
Referrer-Policy: no-referrer
Access-Control-Allow-Methods: GET,POST,OPTIONS
Access-Control-Allow-Headers: ZAP-Header
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Clacks-Overhead: GNU Terry Pratchett
content-length: 1104
Content-Type: text/html; charset=UTF-8

</code></pre>
				
				
			</details> <details class="response-body" open="open">
				<summary>Response body (1104 bytes)</summary>
				
				<pre><code>&lt;!DOCTYPE html&gt;
&lt;head&gt;
&lt;title&gt;ZAP API UI&lt;/title&gt;
&lt;script src=&quot;/script.js/?v=2&amp;apinonce=cabba01554ef81cf&quot; type=&quot;text/javascript&quot;&gt;&lt;/script&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;h1&gt;&lt;a href=&quot;/UI/&quot;&gt;ZAP API UI&lt;/a&gt;&lt;/h1&gt;
&lt;h2&gt;&lt;a href=&quot;/UI/automation/&quot;&gt;Componente: automation&lt;/a&gt;&lt;/h2&gt;
&lt;h3&gt;Vista:planProgress&lt;/h3&gt;

&lt;form id=&quot;zapform&quot; name=&quot;zapform&quot; action=&quot;override&quot;&gt;&lt;table&gt;
&lt;tr&gt;&lt;td&gt;Formato de Salida&lt;/td&gt;&lt;td&gt;
&lt;select id=&quot;zapapiformat&quot;&gt;
&lt;option value=&quot;JSON&quot;&gt;JSON&lt;/option&gt;
&lt;option value=&quot;JSONP&quot; disabled&gt;JSONP&lt;/option&gt;
&lt;option value=&quot;HTML&quot;&gt;HTML&lt;/option&gt;
&lt;option value=&quot;XML&quot;&gt;XML&lt;/option&gt;
&lt;/select&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;apikey*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;apikey&quot; name=&quot;apikey&quot; value=&quot;&quot;/&gt;&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;Método de Formulario&lt;/td&gt;&lt;td&gt;&lt;select id=&quot;formMethod&quot;&gt;
&lt;option value=&quot;GET&quot; selected&gt;GET&lt;/option&gt;
&lt;option value=&quot;POST&quot;&gt;POST&lt;/option&gt;
&lt;/select&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;planId*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;planId&quot; name=&quot;planId&quot;/&gt;&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;button&quot; value=&quot;planProgress&quot; type=&quot;submit&quot; zap-component=&quot;automation&quot; zap-type=&quot;view&quot; zap-name=&quot;planProgress&quot;/&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;/table&gt;
&lt;/form&gt;
&lt;/body&gt;
</code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Parameter</th>
		<td><pre><code>apikey</code></pre></td>
	</tr>
	
	
	<tr>
		<th scope="row">Solution</th>
		<td> 
<p>Válida la entrada y sanea la salida antes de escribirla en cualquier atributo HTML.</p>
 </td>
	</tr>
</table>

											</details></li>
									</ol>
								</li>
								
								<li>
									<h5>
										<a
											href="#alert-type-3">Petición de Autenticación Identificada</a> <span>(1)</span>
									</h5>
									<ol>
										<li><details>
												<summary>
													<span class="request-method-n-url">GET http://localhost:8080/UI/network/action/setHttpProxy/override?apikey=ZAP&amp;host=ZAP&amp;password=ZAP&amp;port=ZAP&amp;realm=ZAP&amp;username=ZAP</span>
												</summary>
												
<table class="alerts-table">
	<tr>
		<th scope="row">Alert tags</th>
		<td>
			<ul class="alert-tags-list">
				
			</ul>
		</td>
	</tr>
	<tr>
		<th scope="row">Alert description</th>
		<td> 
<p>La petición en cuestión se ha identificado como una petición de autenticación. El campo &quot;Otra información&quot; contiene un conjunto de líneas key=vvalue que identifican cualquier campo relevante. Si la solicitud está en un contexto que tiene un método de autenticación configurado como &quot;Detección automática&quot;, esta regla cambiará la autenticación para que coincida con la petición identificada.</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Other info</th>
		<td> 
<p>userParam=username</p>

<p>userValue=ZAP</p>

<p>passwordParam=password</p>

<p>referer=http://localhost:8080/UI/network/action/setHttpProxy/</p>
 </td>
	</tr>
	<tr>
		<th scope="row">Request</th>
		<td><details open="open">
				<summary>Request line and header section (397 bytes)</summary>
				
				<pre><code>GET http://localhost:8080/UI/network/action/setHttpProxy/override?apikey=ZAP&amp;host=ZAP&amp;password=ZAP&amp;port=ZAP&amp;realm=ZAP&amp;username=ZAP HTTP/1.1
host: localhost:8080
user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36
pragma: no-cache
cache-control: no-cache
referer: http://localhost:8080/UI/network/action/setHttpProxy/

</code></pre>
				
				
			</details> <details class="request-body" open="open">
				<summary>Request body (0 bytes)</summary>
				
				<pre><code></code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Response</th>
		<td><details open="open">
				<summary>Status line and header section (565 bytes)</summary>
				
				<pre><code>HTTP/1.1 200 OK
Pragma: no-cache
Cache-Control: no-cache, no-store, must-revalidate
Content-Security-Policy: default-src &#39;none&#39;; script-src &#39;self&#39;; connect-src &#39;self&#39;; child-src &#39;self&#39;; img-src &#39;self&#39; data:; font-src &#39;self&#39; data:; style-src &#39;self&#39;
Referrer-Policy: no-referrer
Access-Control-Allow-Methods: GET,POST,OPTIONS
Access-Control-Allow-Headers: ZAP-Header
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Clacks-Overhead: GNU Terry Pratchett
content-length: 1551
Content-Type: text/html; charset=UTF-8

</code></pre>
				
				
			</details> <details class="response-body" open="open">
				<summary>Response body (1551 bytes)</summary>
				
				<pre><code>&lt;!DOCTYPE html&gt;
&lt;head&gt;
&lt;title&gt;ZAP API UI&lt;/title&gt;
&lt;script src=&quot;/script.js/?v=2&amp;apinonce=7f8b879e364d4135&quot; type=&quot;text/javascript&quot;&gt;&lt;/script&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;h1&gt;&lt;a href=&quot;/UI/&quot;&gt;ZAP API UI&lt;/a&gt;&lt;/h1&gt;
&lt;h2&gt;&lt;a href=&quot;/UI/network/&quot;&gt;Componente: network&lt;/a&gt;&lt;/h2&gt;
&lt;h3&gt;Acción: setHttpProxy&lt;/h3&gt;
Establece la configuración del proxy HTTP.
&lt;form id=&quot;zapform&quot; name=&quot;zapform&quot; action=&quot;override&quot;&gt;&lt;table&gt;
&lt;tr&gt;&lt;td&gt;Formato de Salida&lt;/td&gt;&lt;td&gt;
&lt;select id=&quot;zapapiformat&quot;&gt;
&lt;option value=&quot;JSON&quot;&gt;JSON&lt;/option&gt;
&lt;option value=&quot;JSONP&quot; disabled&gt;JSONP&lt;/option&gt;
&lt;option value=&quot;HTML&quot;&gt;HTML&lt;/option&gt;
&lt;option value=&quot;XML&quot;&gt;XML&lt;/option&gt;
&lt;/select&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;apikey*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;apikey&quot; name=&quot;apikey&quot; value=&quot;&quot;/&gt;&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;Método de Formulario&lt;/td&gt;&lt;td&gt;&lt;select id=&quot;formMethod&quot;&gt;
&lt;option value=&quot;GET&quot; selected&gt;GET&lt;/option&gt;
&lt;option value=&quot;POST&quot;&gt;POST&lt;/option&gt;
&lt;/select&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;host*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;host&quot; name=&quot;host&quot;/&gt;&lt;/td&gt;&lt;td&gt;El host, nombre o dirección.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;port*&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;port&quot; name=&quot;port&quot;/&gt;&lt;/td&gt;&lt;td&gt;El puerto.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;realm&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;realm&quot; name=&quot;realm&quot;/&gt;&lt;/td&gt;&lt;td&gt;El reino de autenticación.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;username&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;username&quot; name=&quot;username&quot;/&gt;&lt;/td&gt;&lt;td&gt;El nombre de usuario.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;password&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;password&quot; name=&quot;password&quot;/&gt;&lt;/td&gt;&lt;td&gt;La contraseña.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td&gt;&lt;/td&gt;&lt;td&gt;&lt;input id=&quot;button&quot; value=&quot;setHttpProxy&quot; type=&quot;submit&quot; zap-component=&quot;network&quot; zap-type=&quot;action&quot; zap-name=&quot;setHttpProxy&quot;/&gt;
&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;/table&gt;
&lt;/form&gt;
&lt;/body&gt;
</code></pre>
				
				
			</details></td>
	</tr>
	<tr>
		<th scope="row">Parameter</th>
		<td><pre><code>username</code></pre></td>
	</tr>
	
	<tr>
		<th scope="row">Evidence</th>
		<td><pre><code>password</code></pre></td>
	</tr>
	<tr>
		<th scope="row">Solution</th>
		<td> 
<p>Se trata de una alerta informativa y no de una vulnerabilidad, por lo que no hay nada que corregir.</p>
 </td>
	</tr>
</table>

											</details></li>
									</ol>
								</li>
								
							</ol>
						</li>
						
					</ol>
				</li>
				  
			</ol>
		</section>

		<section id="appendix" class="appendix">
			<h2>Appendix</h2>

			<section id="alert-types" class="alert-types">
				<h3>Alert types</h3>
				<p class="alert-types-intro">This section contains additional information on the types of alerts in the report.</p>
				<ol>
					<li
						id="alert-type-0">
						<h4>CSP: Directiva Wildcard</h4>
						<table class="alert-types-table">
							<tr>
								<th scope="row">Source</th>
								<td>
									
									   <span>raised by a passive scanner</span> <span>(<a
										href="https://www.zaproxy.org/docs/alerts/10055/">CSP</a>)
									</span>   
								</td>
							</tr>
							<tr>
								<th scope="row">CWE ID</th>
								<td><a
									href="https://cwe.mitre.org/data/definitions/693.html">693</a></td>
							</tr>
							<tr>
								<th scope="row">WASC ID</th>
								<td>15</td>
							</tr>
							<tr>
								<th scope="row">Reference</th>
								<td>
									<ol>
										<li><a
											href="https://www.w3.org/TR/CSP/">https://www.w3.org/TR/CSP/</a></li>
										<li><a
											href="https://caniuse.com/#search=content+security+policy">https://caniuse.com/#search=content+security+policy</a></li>
										<li><a
											href="https://content-security-policy.com/">https://content-security-policy.com/</a></li>
										<li><a
											href="https://github.com/HtmlUnit/htmlunit-csp">https://github.com/HtmlUnit/htmlunit-csp</a></li>
										<li><a
											href="https://developers.google.com/web/fundamentals/security/csp#policy_applies_to_a_wide_variety_of_resources">https://developers.google.com/web/fundamentals/security/csp#policy_applies_to_a_wide_variety_of_resources</a></li>
									</ol>
								</td>
							</tr>
						</table>
					</li>
					<li
						id="alert-type-1">
						<h4>Atributo de elemento HTML controlable por el usuario (XSS potencial)</h4>
						<table class="alert-types-table">
							<tr>
								<th scope="row">Source</th>
								<td>
									
									   <span>raised by a passive scanner</span> <span>(<a
										href="https://www.zaproxy.org/docs/alerts/10031/">Atributo de elemento HTML controlable por el usuario (XSS potencial)</a>)
									</span>   
								</td>
							</tr>
							<tr>
								<th scope="row">CWE ID</th>
								<td><a
									href="https://cwe.mitre.org/data/definitions/20.html">20</a></td>
							</tr>
							<tr>
								<th scope="row">WASC ID</th>
								<td>20</td>
							</tr>
							<tr>
								<th scope="row">Reference</th>
								<td>
									<ol>
										<li><a
											href="https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html">https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html</a></li>
									</ol>
								</td>
							</tr>
						</table>
					</li>
					<li
						id="alert-type-2">
						<h4>Divulgación de Información - Información sensible en URL</h4>
						<table class="alert-types-table">
							<tr>
								<th scope="row">Source</th>
								<td>
									
									   <span>raised by a passive scanner</span> <span>(<a
										href="https://www.zaproxy.org/docs/alerts/10024/">Divulgación de Información - Información sensible en URL</a>)
									</span>   
								</td>
							</tr>
							<tr>
								<th scope="row">CWE ID</th>
								<td><a
									href="https://cwe.mitre.org/data/definitions/200.html">200</a></td>
							</tr>
							<tr>
								<th scope="row">WASC ID</th>
								<td>13</td>
							</tr>
							
						</table>
					</li>
					<li
						id="alert-type-3">
						<h4>Petición de Autenticación Identificada</h4>
						<table class="alert-types-table">
							<tr>
								<th scope="row">Source</th>
								<td>
									
									   <span>raised by a passive scanner</span> <span>(<a
										href="https://www.zaproxy.org/docs/alerts/10111/">Petición de Autenticación Identificada</a>)
									</span>   
								</td>
							</tr>
							
							
							<tr>
								<th scope="row">Reference</th>
								<td>
									<ol>
										<li><a
											href="https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/">https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/</a></li>
									</ol>
								</td>
							</tr>
						</table>
					</li>
				</ol>
			</section>
		</section>
		 
	</main>
</body>
</html>



