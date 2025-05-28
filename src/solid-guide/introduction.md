# Introduction # {#introduction}

The Solid protocol [[!SOLID-PROTOCOL]] is a set of specifications to provide secure and permissioned access to externally stored data using Web communication protocols, global identifiers, authentication and authorization mechanisms, data formats and shapes, and query interfaces.

[PROTOCOL] [[!EQ-LD]] uses linked data to request and transmit event notifications from HTTP resources with the [SUPER] protocol [[!EVENTS-QUERY]]. This makes [PROTOCOL] particularly suitable for use with Solid, which uses linked data to interconnect data across decentralized data stores.

## Purpose ## {#intended-purpose}

This document provides guidance for Solid Protocol implementors interested in adopting [PROTOCOL] for event notifications specific to changes in resource state. This document accompanies the [EVENTS-QUERY inline] and the [EQ-LD inline] specifications and is meant to be read together with them.

## Audience ## {#intended-audience}

This document is for:

<pre class="include">
  path: boilerplate/audience.md
</pre>
