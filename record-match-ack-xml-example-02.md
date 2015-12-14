---
layout: default
---
# record-match Acknowledgement Response Message Example: XML

The following message returns an error code denoting that a required element in the request message was missing.

~~~xml
 <Bundle xmlns="http://hl7.org/fhir">
  <id value="3a0707d3-549e-4467-b8b8-5a2ab3800efe"/>
  <type value="message"/>
  <entry>
    <fullUrl value="urn:uuid:d9d296d8-5afe-42e1-a0ce-3344e0e003ed"/>
    <resource>
      <MessageHeader>
        <id value="caf609cf-c3a7-4be4-a3aa-356b9bb69d4f"/>
        <timestamp value="2015-12-08T11:17:50-05:00"/>
        <event>
          <system value="https://github.com/pophealth/fhir/message-events"/>
          <code value="record-match"/>
        </event>
        <response>
          <identifier value="efdd254b-0e09-4164-883e-35cf3871715f"/>
          <code value="fatal-error"/>
        </response>
        <source>
          <endpoint value="http://acme.com/record-matcher"/>
        </source>
        <destination>
          <endpoint value="https://acme.com/pophealth"/>
        </destination>
        <data>
          <reference value="urn:uuid:26121321-4af5-424c-a0e1-ed3aab1c3470"/>
        </data>
      </MessageHeader>
    </resource>
  </entry>

  <entry>
    <fullUrl value="urn:uuid:25121321-4af5-424c-a0e1-ed3aab1c3560"/>
    <resource>
      <OperationOutcome>
        <id value="urn:uuid:26121321-4af5-424c-a0e1-ed3aab1c3470"/>
        <issue>
          <severity value="fatal-error"/>
          <code value="required" />
        </issue>
      </OperationOutcome>
    </resource>
  </entry>  
</Bundle>
~~~
