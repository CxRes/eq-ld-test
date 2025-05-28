## Activity Mapping ## {#activity-mapping}

When a resource hosted on a [[SOLID-PROTOCOL#Server|Solid server]] is modified by virtue of an HTTP request, the activity type ought to be set as follows:

1. When an event notification is triggered by a request on the resource with one of the following HTTP methods:

  <table class="numbered">
    <caption> Activity Mapping for Resources
    <thead>
      <tr>
        <th> Request Method
        <th> Activity Type
    <tbody>
      <tr>
        <td>
          <code>[[RFC9110#POST|POST]]</code> <br>
          <code>([[SOLID-PROTOCOL#resource-containment|Containers]])</code>
        <td>
          <code>[[ACTIVITYSTREAMS-VOCABULARY#dfn-add|as:Add]]</code>
      <tr>
        <td>
          <code>[[RFC9110#PUT|PUT]]</code>
        <td rowspan="3">
          <code>[[ACTIVITYSTREAMS-VOCABULARY#dfn-update|as:Update]]</code>
      <tr>
        <td>
          <code>[[RFC5789#section-2|PATCH]]</code>
      <tr>
        <td>
          <code>[[RFC9110#POST|POST]]</code> <br>
          <code>(Not [[SOLID-PROTOCOL#resource-containment|Containers]])</code>
      <tr>
        <td>
          <code>[[RFC9110#DELETE|DELETE]]</code>
        <td>
          <code>[[ACTIVITYSTREAMS-VOCABULARY#dfn-delete|as:Delete]]</code>
  </table>
  <br/>

2. When an event notification is triggered on a container, by a request on a contained resource with one of the following HTTP methods:

  <table class="numbered">
    <caption> Activity Mapping for LDP Containers when contained resources change
    <thead>
      <tr>
        <th> Request Method
        <th> Activity Type
    <tbody>
      <tr>
        <td>
          <code>[[RFC9110#PUT|PUT]]</code>
        <td rowspan="2">
          <code>[[ACTIVITYSTREAMS-VOCABULARY#dfn-update|as:Update]]</code>
      <tr>
        <td>
          <code>[[RFC5789#section-2|PATCH]]</code>
      <tr>
        <td>
          <code>[[RFC9110#DELETE|DELETE]]</code>
        <td>
          <code>[[ACTIVITYSTREAMS-VOCABULARY#dfn-remove|as:Remove]]</code>
  </table>
  <br/>

3. When an event notification is triggered on a container, by a request to create a new resource inside that container (resource) with one of the following HTTP methods:

  <table class="numbered">
    <caption> Activity Mapping for LDP Containers when contained resources are created
    <thead>
      <tr>
        <th> Request Method
        <th> Activity Type
    <tbody>
      <tr>
        <td>
          <code>[[RFC9110#PUT|PUT]]</code>
        <td rowspan="2">
          <code>[[ACTIVITYSTREAMS-VOCABULARY#dfn-add|as:Add]]</code>
      <tr>
        <td>
          <code>[[RFC5789#section-2|PATCH]]</code>
  </table>
