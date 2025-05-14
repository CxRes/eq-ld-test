# Protocol # {#protocol}

## Discovery ## {#discovery}

A [=client=] can discover support for event notifications using [PROTOCOL] by examining if a [=server=] is able to accept a query request on a resource using a suitable RDF serialization with content consistent with the [[#request-data-model]].

A [=server=] that provides event notifications using [PROTOCOL] on a resource MUST advertize on the [[HTTP-QUERY#name-accept-query|Accept-Query]]</code> ([[HTTP-QUERY]] [[HTTP-QUERY#name-accept-query|§ 3]]) header field of a response:
+ `application/ld+json` [[JSON-LD11]] as an acceptable representation for a request using the <code>[[HTTP-QUERY#name-query|QUERY]]</code> method ([[HTTP-QUERY]] [[HTTP-QUERY#name-query|§ 2]]), and
  + further set the value of the `profile` parameter to indicate a preferred JSON-LD context `http://www.w3.org/ns/json-ld#context` with `https://cxres.github.io/eq-ld/ns/context/v1` as the URI.

<div class="example">
  <span class="marker">Discovery Request and Response</span>
  <div class="sub-example">
  <em>Request</em>
  <pre class="include-code">
    path: protocol/discovery/request.http
  </pre>
  </div>
  <div class="sub-example">
  <em>Response</em>
  <pre class="include-code">
    path: protocol/discovery/response.http
    line-highlight: 2-3
  </pre>
  </div>
</div>

## Request ## {#request}

A [=server=] implementing [PROTOCOL] MUST accept a request using the <code>[[HTTP-QUERY#name-query|QUERY]]</code> method ([[HTTP-QUERY]] [[HTTP-QUERY#name-query|§ 2]]) when:
+ the content-type of the request is `application/ld+json` [[JSON-LD11]],
+ the request includes `https://cxres.github.io/eq-ld/ns/context/v1` as a URI for the JSON-LD context, and
+ the content conforms to the [[#request-data-model inline]].

A [=server=] MAY support additional RDF representations for an [SUPER] provided their content conforms to the [[#request-data-model]].

<div class="example">
  <span class="marker">Request for Event Notifications</span>
  <pre class="include-code">
    path: protocol/request.http
  </pre>
</div>

## Response ## {#response}

A [=server=] implementing [PROTOCOL] on a resource MUST be able to transmit event notifications using:
+ the `application/ld+json` [[JSON-LD11]] media-type, and
+ the data model described in [[#notification-data-model]].

A [=server=] MAY additionally support other RDF serializations to transmit event notifications.

<div class="example">
  <span class="marker">Response with Event Notifications</span>
  <pre class="include-code">
    path: protocol/response.http
  </pre>
</div>
