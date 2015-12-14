---
layout: default
---
# record-match Message Example: XML

This example contains the minimum set of elements expected in a record-match message.

~~~xml
<Bundle xmlns="http://hl7.org/fhir">
  <id value="10bb101f-a121-4264-a920-67be9cb82c74"/>
  <type value="message"/>
  <entry>
    <fullUrl value="urn:uuid:267b18ce-3d37-4581-9baa-6fada338038b"/>
    <resource>
      <MessageHeader>
        <id value="efdd254b-0e09-4164-883e-35cf3871715f"/>
        <timestamp value="2015-12-08T11:15:33-05:00"/>
        <event>
          <system value="https://github.com/pophealth/fhir/message-events"/>
          <code value="record-match"/>
        </event>
        <source>
          <endpoint value="https://acme.com/pophealth"/>
        </source>
        <destination>
          <endpoint value="http://acme.com/record-matcher"/>
        </destination>
        <author>
          <endpoint value="urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c350a"/>
        </author>
        <data>
          <reference value="urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e"/>
        </data>
        <data>
          <reference value="urn:uuid:04121321-4af5-424c-a0e1-ed3aab1c349d"/>
        </data>
      </MessageHeader>
    </resource>
  </entry>

  <entry>
     <fullUrl value="urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e"/>
     <resource>
      <Parameters>
        <parameter>
          <name value="type"/>
          <valueString value="master"/>
        </parameter>
        <parameter>
          <name value="resourceType"/>
          <valueString value="Patient"/>
        </parameter>
        <parameter>
          <name value="searchExpression" />
          <resource>
            <Parameters>
              <parameter>
                <name value="resourceUrl"/>
                <valueUri value="http://acme.com/popHealth/fhir/Patient"/>
              </parameter>
              <parameter>
                <name value="name"/>
                <valueString value="jon"/>
              </parameter>
            </Parameters>
          </resource>
        </parameter>
      </Parameters>
    </resource>
  </entry>

  <entry>
    <fullUrl value="urn:uuid:04121321-4af5-424c-a0e1-ed3aab1c349d"/>
    <resource>
      <Parameters>
        <parameter>
          <name value="type"/>
          <valueString value="query"/>
        </parameter>
        <parameter>
          <name value="resourceType"/>
          <valueString value="Patient"/>
        </parameter>
        <parameter>
          <name value="searchExpression" />
          <resource>
            <Parameters>
              <parameter>
                <name value="resourceUrl"/>
                <valueUri value="http://acme.com/popHealth/fhir/Patient"/>
              </parameter>
              <parameter>
                <name value="name"/>
                <valueString value="john"/>
              </parameter>
            </Parameters>
          </resource>
        </parameter>
      </Parameters>
    </resource>
  </entry>

  <entry>
    <fullUrl value="urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c350a"/>
    <resource>
      <Practitioner>
        <identifier>
          <use value="usual"/>
          <system value="https://github.com/pophealth/users" />
          <value value="user1" />
        </identifier>
      </Practitioner>
    </resource>
  </entry>  

</Bundle>
~~~
