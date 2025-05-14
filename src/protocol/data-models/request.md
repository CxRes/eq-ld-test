# Request Query Data Model # {#request-data-model}

An [PROTOCOL] request uses the [[EVENTS-QUERY#data-model|Events Query Data Model]] defined by the [[EVENTS-QUERY inline]] protocol [[EVENTS-QUERY]].
The request data is expressed with the [[HTTP-in-RDF10 inline]] [[HTTP-in-RDF10]] and the [[PROTOCOL]][vocabulary](http://cxres.github.io/eq-ld/ns/v1).

## Properties ## {#request-properties}

A request for event notifications made using the [PROTOCOL] protocol MAY have the following properties:

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
