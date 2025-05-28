# Response # {#response}

## Preconditions ## {#response-preconditions}

A [[SOLID-PROTOCOL#Server|Solid server]] ought not to send a response with event notifications unless a `GET` request to the resource would have resulted in one of the following status codes:

+ <code>[[RFC9110#status.200|200 (OK)]]</code> ([[RFC9110]] [[RFC9110#status.200|§ 15.3.1]]),
+ <code>[[RFC9110#status.204|204 (No Content)]]</code> ([[RFC9110]] [[RFC9110#status.204|§ 15.3.5]]),
+ <code>[[RFC9110#status.206|206 (Partial Content)]]</code> ([[RFC9110]] [[RFC9110#status.206|§ 15.3.7]]), and
+ <code>[[RFC3229#section-10.4.1|226 (IM Used)]]</code> ([[RFC3229]] [[RFC3229#section-10.4.1|§ 10.4.1]]).

A [[SOLID-PROTOCOL#Server|Solid server]] unable to serve event notifications for failing to meet the above-mentioned conditions ought to send an error response with the status code set to <code>[[RFC9110#status.412|412 (Precondition Failed)]]</code> ([[RFC9110]] [[RFC9110#status.412|§ 15.5.13]]).
