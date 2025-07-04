## Vocabulary ## {#vocabulary}

To ensure that a notification message is consistent with the [[SOLID-NOTIFICATIONS#notification-message-data-model|data model]] described in [[SOLID-NOTIFICATIONS]], implementations can extend the notification data using the Solid Notifications [vocabulary](https://www.w3.org/ns/solid/notifications).

A [[SOLID-PROTOCOL#Server|Solid server]] is encouraged to augment an event notification with the following property:

<dl>

  <dt id="notification-property-state"><code>*notify:state* &lt;xs:string></code>
  <dd> an opaque identifier for the last known state of the resource.

</dl>

NOTE: By not mandating this property, we allow existing Solid implementations that might not keep track of state, to still adopt [PROTOCOL]. Newer implementations are encouraged to include this property unless operating in constrained environments.
