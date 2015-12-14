# record-match Acknowledgement Response Message Example: JSON

The following message returns an error code denoting that a required element in the request message was missing.
```json
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
          "system": "https://github.com/pophealth/fhir/message-events",
          "code": "record-match"
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
            "reference": "urn:uuid:26121321-4af5-424c-a0e1-ed3aab1c3470"
          }
        ]
      }
    },
    {
      "fullUrl": "urn:uuid:25121321-4af5-424c-a0e1-ed3aab1c3560",
      "resource": {
        "resourceType": "OperationOutcome",
        "id": "urn:uuid:26121321-4af5-424c-a0e1-ed3aab1c3470",
        "issue": {
          "severity": "fatal-error",
          "code": "requierd"
        }
      }
    }
  ]
}
```