# Request # {#request}

## Data Model ## {#request-data-model}

A request for event notifications using the [PROTOCOL] builds on the abstract [[EVENTS-QUERY#data-model|data model]] defined by the [[EVENTS-QUERY inline]] protocol [[EVENTS-QUERY]].

## Vocabulary ## {#request-vocabulary}

The request data is expressed with the [[HTTP-in-RDF10 inline]] [[HTTP-in-RDF10]] and the [PROTOCOL] [vocabulary](http://cxres.github.io/eq-ld/ns/eq.ttl).

[PROTOCOL] defines the following RDF properties that a [=client=] MAY use in a request:

<dl>

  <dt id="request-property-events"><code>*eq-ld:events* &lt;http:headers></code>
  <dd>Header fields to negotiate event notifications in an [SUPER].

  <dt id="request-property-state"><code>*eq-ld:state* &lt;http:headers></code>
  <dd>Header fields to negotiate the representation of resource state in an [SUPER].

</dl>

## Extended Content ## {#extended-request-content}

A [=server=] MAY admit an extended request based on an augmented [[JSON-LD11#the-context|JSON-LD Context]] [[JSON-LD11]] definition.

<div class="advisement">
  <div class="marker">Implementation Guidance</div>
  [=Servers=] are encouraged to be aware that anything can be included in an [SUPER] request. [=Servers=] are advised to take suitable precautions when processing request queries.
</div>

## Format ## {#request-format}

A [=server=] implementing [PROTOCOL] MUST accept a request using the <code>[[HTTP-QUERY#name-query|QUERY]]</code> method ([[HTTP-QUERY]] [[HTTP-QUERY#name-query|§ 2]]) when the content-type of the request is `application/ld+json` [[JSON-LD11]], and
includes `http://cxres.github.io/eq-ld/ns/context.jsonld` as a URI for the JSON-LD context.

A [=server=] MAY support additional RDF representations for an [SUPER].

<div class="example">
  <span class="marker">Request for Event Notifications</span>
  <pre class="include-code">
    path: examples/events/request.http
  </pre>
</div>
