---
layout: default
---
# record-match Response Message Example: XML

This example contains the minimum set of elements and attributes for a response to a record-match request.

~~~xml
 <Bundle xmlns="http://hl7.org/fhir">
  <id value="3a0707d3-549e-4467-b8b8-5a2ab3800efe"/>
  <type value="message"/>
  <entry>
    <fullUrl value="urn:uuid:d9d296d8-5afd-42e1-a0ce-3344e0e003ed"/>
    <resource>
      <MessageHeader>
        <id value="caf609cf-c3a7-4be3-a3aa-356b9bb69d4f"/>
        <timestamp value="2015-12-08T11:17:33+10:00"/>
        <event>
          <system value="https://github.com/pophealth/fhir/message-events"/>
          <code value="record-match"/>
        </event>
        <response>
          <identifier value="efdd254b-0e09-4164-883e-35cf3871715f"/>
          <code value="ok"/>
          <details>
            <reference value="OperationOutcome/03f9aa7d-b395-47b9-84e0-053678b6e4e3"/>
          </details>
        </response>
        <source>
          <endpoint value="http://acme.com/record-matcher"/>
        </source>
        <destination>
          <endpoint value="https://acme.com/pophealth"/>
        </destination>
        <data>
          <reference value="urn:uuid:04121321-4af5-424c-a0e1-ed3aab1c349d"/>
        </data>
        <data>
          <reference value="urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e"/>
        </data>
      </MessageHeader>
    </resource>
  </entry>

  <entry>
    <fullUrl value="urn:uuid:03f9aa7d-b395-47b9-84e0-053678b6e4e3"/>
    <resource>
      <OperationOutcome>
        <id value="03f9aa7d-b395-47b9-84e0-053678b6e4e3"/>
        <issue>
          <severity value="information"/>
          <code value="informational"/>
          <details>
            <text value="Match Complete"/>
          </details>
        </issue>
      </OperationOutcome>
    </resource>  
  </entry>

   <!-- The search expressions from the match request are repeated in response -->
   <entry>
    <fullUrl value="urn:uuid:04121321-4af5-424c-a0e1-ed3aab1c349d"/>
    <request>
    <!-- get a list of patient resources -->
      <method value="GET"/>
      <url value="http://acme.com/popHealth/fhir/Patient?name=John"/>
    </request>
  </entry>

  <entry>
    <fullUrl value="urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e"/>
    <request>
    <!-- get a list of patient resources -->
      <method value="GET"/>
      <url value="http://acme.com/popHealth/fhir/Patient?name=Jon"/>
    </request>
  </entry>

  <!-- Entries that report match results -->
  <entry>
    <!-- Record on source fhir server -->
    <fullUrl>http://acme.com/popHealth/Patient/5</fullUrl>
    <!-- reference to URI that defines resource type -->
    <link>
      <relation value=“type”/>
      <url value=“http://hl7.org/fhir/Patient”/>
    </link>
    <!--links to one records considered as a match to the source record -->
    <!-- if multiple links, each pairing w/ source has the same match score -->
    <link>
      <relation value=“related”/>
      <url value=“http://acme.com/popHealth/Patient/55”/>
    </link>
    <search>
      <extension url="http://hl7.org/fhir/StructureDefinition/patient-mpi-match">
        <valueCode value="probable"/>
      </extension>
      <!-- standard search score provides way to return match score -->
      <score value="0.80"/>
    </search>
  </entry>
...
</Bundle>
~~~
