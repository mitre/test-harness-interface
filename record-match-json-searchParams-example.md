# record-match Search Parameters Example: JSON


The following search is for patients who have a value in the gender field.

```json
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
                  "name" : "gender:missing",
                  "valueString" : "false"
                }
              ]
            }
          }
        ]
      }
    }
```

The following search is for patients whose name is contains "John" (case insensitive and accent-insensitive, partial match at start or end) and whose address.state value is one of the specified values.
```json
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
                  "name" : "name:contains",
                  "valueString" : "John"
                }
                {
                  "name" : "address-state",
                  "valueString" : "MA,CT,RI,NH,VT,ME"
                }
              ]
            }
          }
        ]
      }
    }
```

The following search is for patients whose name matches the string, maria, and has a birthdate on Jan 1, 2000 or later
```json
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
                  "valueString" : "maria"
                },
                {
                  "name" : "birthdate",
                  "valueString" : "ge2000-01-01"
                }
              ]
            }
          }
        ]
      }
    }
```
