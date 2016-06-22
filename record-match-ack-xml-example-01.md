---
layout: default
---
# record-match Acknowledgement Response Message Accept Example: XML


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
          <system value="http://github.com/mitre/ptmatch/fhir/message-events"/>
          <code value="record-match"/>
        </event>
        <response>
          <identifier value="efdd254b-0e09-4164-883e-35cf3871715f"/>
          <code value="ok"/>
        </response>
        <source>
          <endpoint value="http://acme.com/record-matcher"/>
        </source>
        <destination>
          <endpoint value="https://acme.com/pophealth"/>
        </destination>
      </MessageHeader>
    </resource>
  </entry>

</Bundle>
~~~
