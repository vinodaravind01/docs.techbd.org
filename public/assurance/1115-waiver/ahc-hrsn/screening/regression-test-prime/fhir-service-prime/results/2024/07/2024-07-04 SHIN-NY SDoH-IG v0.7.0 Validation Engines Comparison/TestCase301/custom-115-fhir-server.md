# File evaluation against Custom 1115 FHIR Server

## Files tested

- [TestCase301.json](TestCase301.json)

## NYeC expectations

```json
{
  "testcase": 301,
  "csvoutputS3Bucket": "certification-engine-output",
  "testcasetype": "POSITIVE",
  "expectedResult": "Test Case 301 should succcessfully be processed by the QE and forwarded to NYeC.  The MPI for the patient should be added to the Patient resource."
}
```

## Results

```json
{
    "OperationOutcome": {
      "validationResults": [
        {
          "issues": [
            {
              "location": {
                "line": null,
                "column": null,
                "diagnostics": "ca.uhn.fhir.parser.DataFormatException"
              },
              "message": "HAPI-1821: [element=\"gender\"] Invalid attribute value \"UN\": Unknown AdministrativeGender code 'UN'",
              "severity": "FATAL"
            }
          ],
          "initiatedAt": 1720067041.6496751,
          "profileUrl": "https://djq7jdt8kb490.cloudfront.net/1115/StructureDefinition-SHINNYBundleProfile.json",
          "observability": {
            "identity": "org.techbd.orchestrate.fhir.OrchestrationEngine$HapiValidationEngine",
            "name": "HAPI version 7.2.0 (TODO:get from API instead of hard coding) (FHIR version 4.0.1)",
            "initAt": 1720065312.4929638,
            "constructedAt": 1720065312.5307271
          },
          "operationOutcome": null,
          "completedAt": 1720067041.6509244,
          "valid": false
        }
      ],
      "device": {
        "deviceId": "127.0.1.1",
        "deviceName": "vinod-OptiPlex"
      },
      "resourceType": "OperationOutcome"
    }
  }  
```