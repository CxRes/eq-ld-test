# Introduction # {#introduction}

*This section is non-normative.*

[SUPER] [[EVENTS-QUERY]] is a minimal event notifications protocol built on top of HTTP. [PROTOCOL] ([SHORTNAME]) defines representation and semantics for using linked data to request and transmit event notifications directly from HTTP resources with the [SUPER] protocol.

## Audience ## {#intended-audience}

*This section is non-normative.*

This specification is for:

<pre class="include">
  path: boilerplate/audience.md
</pre>

## Namespaces ## {#namespaces}

This specification uses the following RDF vocabularies and corresponding namespace prefix bindings:

<table class="auto">
  <caption> Prefixes and Namespaces
  <thead>
    <tr>
      <th> Prefix
      <th> Namespace
      <th> Description
  <tbody>
    <tr>
      <td> <code>eq-ld</code>
      <td> <samp>http://cxres.github.io/eq-ld/ns/eq.ttl#</samp>
      <td> [PROTOCOL]
    <tr>
      <td> <code>as</code>
      <td> <samp>https://www.w3.org/ns/activitystreams#</samp>
      <td> [[!ACTIVITYSTREAMS-VOCABULARY]]
    <tr>
      <td> <code>http</code>
      <td> <samp>http://www.w3.org/2011/http#</samp>
      <td> [[!HTTP-in-RDF10]]
    <tr>
      <td> <code>xs</code>
      <td> <samp>http://www.w3.org/2001/XMLSchema#</samp>
      <td> [[!XMLSCHEMA11-1]]
</table>
