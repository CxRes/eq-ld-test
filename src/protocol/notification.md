# Notification # {#notification}

## Data Model ## {#notification-data-model}

An [PROTOCOL] notification message specializes the [[ACTIVITYSTREAMS-CORE#activities|Activity object]] defined by [[ACTIVITYSTREAMS-CORE inline]] [[ACTIVITYSTREAMS-CORE]].

## Vocabulary ## {#notification-vocabulary}

The core notification data is expressed with the Activity Streams [[ACTIVITYSTREAMS-VOCABULARY|vocabulary]] [[ACTIVITYSTREAMS-VOCABULARY]].

An event notification transmitted using the [PROTOCOL] protocol MUST have the following properties:

<dl>

  <dt id="notification-property-type"><code>*as:type* &lt;as:Activity></code>
  <dd> the [[ACTIVITYSTREAMS-VOCABULARY#activity-types|type of activity]] that triggered the notification.

  <dt id="notification-property-published"><code>*as:published* &lt;xs:dateTime></code>
  <dd> the date and time of the notification.

</dl>

## Activity Mapping ## {#activity-mapping}

A [=server=] sending an event notification with the [PROTOCOL] protocol as a result of some activity on a resource MUST set the [type](#notification-property-type) property as the [[ACTIVITYSTREAMS-VOCABULARY#activity-types|type of activity]] that triggered the notification as specified by the Activity Streams [[ACTIVITYSTREAMS-VOCABULARY|vocabulary]] [[ACTIVITYSTREAMS-VOCABULARY]].

## Extended Content ## {#extended-notification-content}

A [=server=] MAY augment the [[JSON-LD11#the-context|JSON-LD Context]] [[JSON-LD11]] definition and extend the content of an event notification.

NOTE: See examples of [[ACTIVITYSTREAMS-CORE#example-using-multiple-vocabularies|using multiple vocabularies]] in the Activity Streams [[ACTIVITYSTREAMS-CORE]] specification.

<div class="advisement">
  <div class="marker">Implementation Guidance</div>
  [=Clients=] are encouraged to be aware that anything can be included in an event notification. [=Clients=] are advised to take suitable precautions when ascertaining the veracity of the contents.
</div>

## Format ## {#notification-format}

A [=server=] implementing [PROTOCOL] on a resource MUST be able to transmit event notifications using the `application/ld+json` [[JSON-LD11]] media-type.

A [=server=] MAY additionally support other RDF serializations to transmit event notifications.

<div class="example">
  <span class="marker">An Event Notifications</span>
  <pre class="include-code">
    path: examples/events/update.http
  </pre>
</div>
