---
layout: default
---
# record-match Response Message Example: JSON

This example contains the minimum set of elements and attributes for a response to a record-match request.

~~~json
{
  "resourceType": "Bundle",
  "id": "3a0707d3-549e-4467-b8b8-5a2ab3800efe",
  "type": "message",
  "entry": [
    {
      "fullUrl": "urn:uuid:d9d296d8-5afe-42e1-a0ce-3344e0e003ed",
      "resource": {
        "resourceType": "MessageHeader",
        "id": "caf609cf-c3a7-4be4-a3aa-356b9bb69d4f",
        "timestamp": "2015-12-08T11:17:50-05:00",
        "event": {
          "system": "http://github.com/mitre/ptmatch/fhir/message-events",
          "code": "record-match"
        },
        "response": {
          "identifier": "efdd254b-0e09-4164-883e-35cf3871715f",
          "code": "ok",
          "details": {
            "reference": "OperationOutcome/03f9aa7d-b395-47b9-84e0-053678b6e4e3"
          }
        },
        "source": {
          "endpoint": "http://acme.com/record-matcher"
        },
        "destination": [
          {
            "endpoint": "https://acme.com/pophealth"
          }
        ],
        "data" : [
          {
            "reference": "urn:uuid:04121321-4af5-424c-a0e1-ed3aab1c349d"
          },
          {
            "reference": "urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e"
          }
        ]
      }
    },
    {
      "fullUrl": "urn:uuid:03f9aa7d-b395-47b9-84e0-053678b6e4e3",
      "resource": {
        "resourceType": "OperationOutcome",
        "id": "03f9aa7d-b395-47b9-84e0-053678b6e4e3",
        "issue": {
          "severity": "information",
          "code": "informational",
          "details": {
            "text": "Match Complete"
          }
        }

      }
    },
    {
      "fullUrl": "urn:uuid:15121321-4af5-424c-a0e1-ed3aab1c348e",
      "request": {
        "method": "GET",
        "url": "http://acme.com/popHealth/fhir/Patient?name=Jon"
      }
    },
    {
      "fullUrl": "http://acme.com/popHealth/Patient/5",
      "link": [
        {
          "relation": "type",
          "url": "http://hl7.org/fhir/Patient"
        },
        {
          "relation": "related",
          "url": "http://acme.com/popHealth/Patient/55"
        }
      ],
      "search": {
        "extension": {
          "url": "http://hl7.org/fhir/StructureDefinition/patient-mpi-match",
          "valueCode": "probable"
        },
        "score": 0.80
      }
    }
  ]
}
~~~
