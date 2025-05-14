## Conformance ## {#conformance}

<pre class="include">
  path: boilerplate/conformance.md
</pre>

### Specification Category ### {#specification-category}

The [PROTOCOL] identifies the following [[SPEC-VARIABILITY#spec-cat|Specification Categories]] [[SPEC-VARIABILITY]] to distinguish the types of conformance:
+ API,
+ Notation/syntax,
+ Set of events,
+ Protocol.

### Classes of Products ### {#classes-of-products}

The [PROTOCOL] identifies the following [[SPEC-VARIABILITY#cop|Classes of Products]] [[SPEC-VARIABILITY]] for conforming implementations. These products are referenced throughout this specification.

<dl>

  : <dfn>Server</dfn>
  :: A *server* that builds on HTTP server [[!RFC9110]] and [[!RFC9112]] by defining methods,media types and behaviour of resources.
  : <dfn>Client</dfn>
  :: A *client* that builds on a HTTP client [[!RFC9110]], [[!RFC9112]] and [[!FETCH]] by defining behaviour in terms of fetching across the platform.

</dl>

### Interoperability ### {#interoperability}

Interoperability occurs between [Client—Server](#client-server-interoperability) as defined by [PROTOCOL].

<dl>

  : <dfn id="client-server-interoperability">Client—Server Interoperability</dfn>
  :: Interoperability of implementations for [=clients=] and [=servers=] is tested by evaluating an implementation’s ability to transmit and receive event notifications that conform to [PROTOCOL].

</dl>
