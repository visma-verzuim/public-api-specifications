# Add a new absence dossier by adding a new absence course

## Use case

The objective is to add a new absence dossier by inserting a new absence course. The system should intelligently determine whether the added course should be associated with an existing dossier or initiate a new one.

## Steps to follow

- **Determine the employee** - Identify the employee for whom the absence dossier will be created or updated.

- **Determine the absence reason** - Specify the reason for the absence, which will be used to categorize the absence course.

- **Add a new absence-course** - Insert the new absence course into the system. The system will assess whether this course should be linked to an existing absence dossier or if a new dossier should be created.

---

## Sample Requests

### Determine the employee

**Sample Request**

```json
GET /api/public/employee?filter[externalKey]=HR1000123&include=employments
Authorization: Bearer [Your Access Token]
Body: [empty]
```

**Sample Response**

```json
{
  "data":[
    {
      "id":"f02e4546-23b2-4686-b109-521c448f6dc8",
      "externalKey":"HR1000123",
      "socialSecurityNumber":null,
      "noRisk":false,
      "sfb":false,
      "absenceFrequency":2,
      "employments": [
        {
          "id": "fa856783-c3f0-49e4-9662-70978389a6c7",
          "externalKey": null,
          "migrationKey": null,
          "employmentNumber": "1",
          "primary": true,
          "employeeNumber": null,
          "supervisorType": "internal",
          "uwvRiskCode": null,
          "waitingDays": null,
          "dateSeniority": null,
          "dateStartChainProvision": null,
          "dateCreated": "2025-01-07 15:24:31",
          "dateUpdated": "2025-01-07 15:25:47"
        }
      ],
      "dateCreated":"2025-01-07 15:24:31",
      "dateUpdated":"2025-01-07 15:24:31"
    }
  ],
  "links":{
    "self":"{{API_HOST}}/public/employee?filter[externalKey]=HR1000123&page[number]=1&page[size]=25",
    "first":"{{API_HOST}}/public/employee?filter[externalKey]=HR1000123&page[number]=1&page[size]=25",
    "last":"{{API_HOST}}/public/employee?filter[externalKey]=HR1000123&page[number]=1&page[size]=25",
    "prev":null,
    "next":null
  },
  "meta":{
    "total":2,
    "perPage":25,
    "totalPages":1
  }
}
```

### Determine the absence reason

**Sample Request**

```json
GET /api/public/absence-reason
Authorization: Bearer [Your Access Token]
Body: [empty]
```

**Sample Response**

```json
{
  "data": [
    {
      "id": "99461cb8-3957-4e01-a576-35c45aba1972",
      "externalKey": null,
      "migrationKey": null,
      "name": "Onbekend",
      "code": null,
      "isPrimary": false
    }
  ],
  "links": {
    "self": "{{API_HOST}}/api/public/absence-reason?page[number]=1&page[size]=25",
    "first": "{{API_HOST}}/api/public/absence-reason?page[number]=1&page[size]=25",
    "last": "{{API_HOST}}/api/public/absence-reason?page[number]=1&page[size]=25",
    "prev": null,
    "next": null
  },
  "meta": {
    "total": 1,
    "perPage": 25,
    "totalPages": 1
  }
}
```

### Add a new Absence Course

**Sample Request**

```json
POST /api/public/absence-reason
Authorization: Bearer [Your Access Token]
Body:
{
  "absenceReasonId": "99461cb8-3957-4e01-a576-35c45aba1972", // onbekend
  "employmentId": "fa856783-c3f0-49e4-9662-70978389a6c7",
  "dateReported": "2025-01-01",
  "dateStart": "2025-01-01",
  "workedHours": 0,
  "expectedDurationDays": 3,
  "recoveryPercentage": 0
}
```

**Sample Response**

```json
{
    "message": "success",
    "status": 201,
    "errors": [],
    "data": {
        "id": "423b0e27-7c14-4db7-a2e3-d894bfa650f9",
        "externalKey": null,
        "employeeExternalKey": null,
        "employmentExternalKey": null,
        "employmentId": "fa856783-c3f0-49e4-9662-70978389a6c7",
        "dateReported": "2025-01-01",
        "dateStart": "2025-01-01",
        "dateEnd": null,
        "absenceReason": {
            "id": "99461cb8-3957-4e01-a576-35c45aba1972",
            "externalKey": null,
            "migrationKey": null,
            "name": "Onbekend",
            "code": null,
            "isPrimary": false
        },
        "recoveryPercentage": 0,
        "recoveryReason": null,
        "wageValue": 0,
        "workedHours": 0,
        "safetyNet": null,
        "dossier": {
            "id": "650de2e4-435f-4a53-9249-173b7f37f285",
            "type": "illness",
            "externalKey": null,
            "protocol": "wvp",
            "safetyNet": null,
            "dateStart": "2025-01-01T14:50:48+01:00",
            "dateEnd": null,
            "dateCompleted": null,
            "dossierStatus": "open",
            "accidentType": null,
            "dateCreated": "2025-01-15 14:50:48",
            "dateUpdated": "2025-01-15 14:50:49"
        },
        "dateCreated": "2025-01-27 14:57:21",
        "dateUpdated": "2025-01-27 14:57:21"
    },
    "traceId": "74d3a755-e4f1-429b-8836-5a4f5159ffcb"
}
```


