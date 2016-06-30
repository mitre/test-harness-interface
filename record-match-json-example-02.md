---
layout: default
---
# record-match Message Example: JSON

This example contains the minimum set of elements expected in a record-match message.

~~~json
{
  "resourceType": "Bundle",
  "id": "10bb101f-a121-4264-a920-67be9cb82c74",
  "type": "message",
  "entry": [
    {
      "fullUrl": "urn:uuid:267b18ce-3d37-4581-9baa-6fada338038b",
      "resource": {
        "resourceType": "MessageHeader",
        "id": "efdd254b-0e09-4164-883e-35cf3871715f",
        "timestamp": "2015-12-08T11:15:33-05:00",
        "event": {
          "system": "http://github.com/mitre/ptmatch/fhir/message-events",
          "code": "record-match"
        },
        "source": {
          "endpoint": "https://acme.com/pophealth"
        },
        "destination": [
          {
            "endpoint": "http://acme.com/record-matcher"
          }
        ],
        "author": {
          "reference": "urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c350a"
        },
        "data": [
          {
            "reference": "urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e"
          },
          {
            "reference": "urn:uuid:04121321-4af5-424c-a0e1-ed3aab1c349d"
          }
        ]
      }
    },

    {
      "fullUrl": "urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e",
      "resource": {
        "resourceType": "Parameters",
        "parameter": [
          {
            "name" : "type",
            "valueString" : "master"
          },
          {
            "name" : "resourceType",
            "valueString" : "Patient"
          },
          {
            "name" : "searchExpression",
            "resource" : {
              "resourceType": "Parameters",
              "parameter": [
                {
                  "name" : "resourceUrl",
                  "valueString" : "http://acme.com/popHealth/fhir/Patient"
                },
                {
                  "name" : "name",
                  "valueString" : "jon"
                }
              ]
            }
          }
        ]
      }
    },

    {
      "fullUrl": "urn:uuid:04121321-4af5-424c-a0e1-ed3aab1c349d",
      "resource": {
        "resourceType": "Parameters",
        "parameter": [
          {
            "name" : "type",
            "valueString" : "query"
          },
          {
            "name" : "resourceType",
            "valueString" : "Patient"
          },
          {
            "name" : "searchExpression",
            "resource" : {
              "resourceType": "Parameters",
              "parameter": [
                {
                  "name" : "resourceUrl",
                  "valueString" : "http://acme.com/popHealth/fhir/Patient"
                },
                {
                  "name" : "name",
                  "valueString" : "john"
                }
              ]
            }
          }
        ]
      }
    },

    {
      "fullUrl": "urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c350a",
      "resource": {
        "resourceType": "Practitioner",
        "identifier": {
          "use" : "usual",
          "system": "http://github.com/mitre/ptmatch/users",
          "value": "user1"
        }
      }
    }

  ]
}
~~~
