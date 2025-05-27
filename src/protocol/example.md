<h2 class="no-num" id="example">
  Example
</h2>

*This section is non-normative.*

The following uses the example of a resource with a missing persons' report to illustrate the request and response for representation and event notifications using [PROTOCOL].

<div class="example">
  <span class="marker">[PROTOCOL]: A Complete Example</span>
  <p>The [=client=] specifies headers in both the `eq-ld:state` and `eq-ld:events` property of the [SUPER] request:</p>
  <pre class="include-code">
    path: examples/state/request.http
  </pre>
  <p>The [=server=] immediately returns headers  indicating that the response shall transmit a stream of event notifications:</p>
  <pre class="include-code">
    path: examples/events/response-header.http
  </pre>
  <p>Following this, the [=server=] returns the missing persons' report as the representation of the resource:</p>
  <pre class="include-code">
    path: examples/state/representation.http
    line-start: 7
  </pre>
  <p>Subsequently, when status of the person is updated, the [=server=] transmits an event notification:</p>
  <pre class="include-code">
    path: examples/events/update.http
    line-start: 17
  </pre>
  <p>Finally, the person is found, so the resource is deleted, the [=server=] emits an event notification and the stream closes:</p>
  <pre class="include-code">
    path: examples/events/delete.http
    line-start: 28
  </pre>
</div>
