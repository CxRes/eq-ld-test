<h2 id="considerations" class="no-num">
  Considerations
</h2>

*This section is non-normative.*

<pre class="include">
  path: boilerplate/considerations.md
</pre>

## Security Considerations ## {#security-considerations}

*This section is non-normative.*

Since [PROTOCOL] uses [SUPER] to transmit notifications, it follows that the [PROTOCOL] inherits security considerations from [SUPER], as discussed in [[EVENTS-QUERY]] [[EVENTS-QUERY#name-security-considerations|§ Security Considerations]].

[=Servers=] are strongly discouraged from exposing information beyond the minimum amount necessary in a notification. [=Clients=] are strongly discouraged from exposing information beyond the minimum amount necessary to receive notifications from particular resources.

[=Clients=] are discouraged from sending requests for notifications to untrusted [=servers=], including localhost or any other loopback IP address, in order to avoid making arbitrary requests.
