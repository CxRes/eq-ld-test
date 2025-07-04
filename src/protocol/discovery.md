# Discovery # {#discovery}

A [=client=] can discover support for event notifications using [PROTOCOL] by examining if a [=server=] is able to accept a query request on a resource using a suitable RDF serialization with content consistent with the [[#request-format|Request Format]].

A [=server=] that provides event notifications using [PROTOCOL] on a resource MUST advertize `application/ld+json` [[JSON-LD11]] as an acceptable representation for a request with the <code>[[HTTP-QUERY#name-query|QUERY]]</code> method ([[HTTP-QUERY]]), using the <code>[[HTTP-QUERY#name-accept-query|Accept-Query]]</code> ([[HTTP-QUERY]] [[HTTP-QUERY#name-accept-query|§ 3]]) header field of a response.
A [=server=] MUST further set the value of the `profile` parameter of the `application/ld+json` media type to indicate a preferred JSON-LD context `http://www.w3.org/ns/json-ld#context` with `http://cxres.github.io/eq-ld/ns/context.jsonld` as the URI.

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
    line-highlight: 2-3
  </pre>
  </div>
</div>
