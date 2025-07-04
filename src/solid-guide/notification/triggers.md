## Triggers ## {#triggers}

The Solid Protocol [[SOLID-PROTOCOL]] requires the state of an LDP container is modified when a contained resource is acted upon by certain HTTP methods. Thus, an HTTP method acting on a resource can trigger a [[SOLID-PROTOCOL#Server|Solid server]] to transmit an event notification on that resource or its container or both.

It follows that a [[SOLID-PROTOCOL#Server|Solid server]] ought to send event notification(s) on a resource and/or its container, when a request with one of the following HTTP methods generates a response with any of the given HTTP status codes:

<table class="numbered auto">
  <caption> HTTP Notification Triggers
  <tr>
    <th rowspan=2> Request Method
    <th rowspan=2> Response Status
    <th colspan=2 class="center"> Notify
  <tr>
    <th class="center"> Resource
    <th class="center"> Container
  <tr>
    <td rowspan=2>
      <code>[[RFC9110#PUT|PUT]]</code> <br>
      <code>[[RFC5789#section-2|PATCH]]</code> <br>
    <td>
      <code>[[RFC9110#status.200|200 (OK)]]</code> <br>
      <code>[[RFC9110#status.204|204 (No Content)]]</code> <br>
      <code>[[RFC9110#status.205|205 (Reset Content)]]</code>
    <td class="tick">
      &check;
    <td class="tick">
      &check;
  <tr>
    <td>
      <code>[[RFC9110#status.201|201 (Created)]]</code> <br>
    <td>
    <td class="tick">
      &check;
  <tr>
    <td rowspan=2>
      <code>[[RFC9110#POST|POST]]</code>
    <td>
      <code>[[RFC9110#status.200|200 (OK)]]</code> <br>
      <code>[[RFC9110#status.204|204 (No Content)]]</code> <br>
      <code>[[RFC9110#status.205|205 (Reset Content)]]</code>
    <td class="tick">
      &check;
    <td class="tick">
      &check;
  <tr>
    <td>
      <code>[[RFC9110#status.201|201 (Created)]]</code>
    <td class="tick">
      &check;
    <td>
  <tr>
    <td>
      <code> [[RFC9110#DELETE|DELETE]]</code>
    <td>
      <code>[[RFC9110#status.200|200 (OK)]]</code> <br>
      <code>[[RFC9110#status.204|204 (No Content)]]</code> <br>
    <td class="tick">
      &check;
    <td class="tick">
      &check;
</table>
<br/>

Additionally, a [[SOLID-PROTOCOL#Server|Solid server]] ought to send event notification(s) on a resource and/or its container when modified at a later time as result of HTTP request that generates a <code>[[RFC9110#status.202|202 (Accepted)]]</code> status code.
