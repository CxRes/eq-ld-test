# Protocol # {#protocol}

## Discovery ## {#discovery}

A [=client=] can discover support for event notifications using [PROTOCOL] by examining if a [=server=] is able to accept a query request on a resource using a suitable RDF serialization with content consistent with the [[#request-data-model]].

A [=server=] that provides event notifications using [PROTOCOL] on a resource MUST advertize on the <code>[[HTTP-QUERY#name-accept-query|Accept-Query]]</code> ([[HTTP-QUERY]] [[HTTP-QUERY#name-accept-query|§ 3]]) header field of a response:
+ `application/ld+json` [[JSON-LD11]] as an acceptable representation for a request using the <code>[[HTTP-QUERY#name-query|QUERY]]</code> method ([[HTTP-QUERY]] [[HTTP-QUERY#name-query|§ 2]]), and
  + further set the value of the `profile` parameter to indicate a preferred JSON-LD context `http://www.w3.org/ns/json-ld#context` with `http://cxres.github.io/eq-ld/ns/context.jsonld` as the URI.

<div class="example">
  <span class="marker">Discovery Request and Response</span>
  <div class="sub-example">
  <em>Request</em>
  <pre class="include-code">
    path: examples/discovery/request.http
  </pre>
  </div>
  <div class="sub-example">
  <em>Response</em>
  <pre class="include-code">
    path: examples/discovery/response.http
  </pre>
  </div>
</div>
<!-- line-highlight: 2-3 -->

## Request ## {#request}

A [=server=] implementing [PROTOCOL] MUST accept a request using the <code>[[HTTP-QUERY#name-query|QUERY]]</code> method ([[HTTP-QUERY]] [[HTTP-QUERY#name-query|§ 2]]) when:
+ the content-type of the request is `application/ld+json` [[JSON-LD11]],
+ the request includes `http://cxres.github.io/eq-ld/ns/context.jsonld` as a URI for the JSON-LD context, and
+ the content conforms to the [[#request-data-model]].

A [=server=] MAY support additional RDF representations for an [SUPER] provided their content conforms to the [[#request-data-model]].

<div class="example">
  <span class="marker">Request for Event Notifications</span>
  <pre class="include-code">
    path: examples/events/request.http
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
    path: examples/events/response.http
  </pre>
</div>
