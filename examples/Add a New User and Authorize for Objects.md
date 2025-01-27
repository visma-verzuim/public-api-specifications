# Add a New User and Authorize for Objects

## Use Case

This example demonstrates how to create a new user in the system and authorize them for specific objects, specifically two Organizational Units.

### Steps to Follow

1. **Retrieve the User Role:**
   - Identify the user role you wish to assign to the new user.
   - *Example role in this case: Arbo role.*
2. **Create the User and Assign the User Role:**
   - Execute the process to create a new user in the system.
   - Assign the previously retrieved user role to the new user.
3. **Determine Objects for Authorization:**
   - Identify the specific objects (e.g., Organizational Units) that the new user should be authorized for.
4. **Add Authorization to the Created User:**
   - Assign the necessary authorizations for the identified objects to the new user.

---

## Sample Requests

### 1. Retrieve the User role

**Sample Request**

```json
GET /api/public/arbo-role?filter[active]=true
Authorization: Bearer [Your Access Token]
Body: [empty]
```

**Sample Response**

```json
{
    "data": [
        {
            "id": "abcdef12-3456-7890-abcd-ef1234567890",
            "name": "Casemanager",
            "code": null,
            "externalKey": null,
            "migrationKey": null,
            "active": true
        },
        ... // More results
    ],
    "links": {
        "self": "{{API_HOST}}/public/arbo-role?filter[active]=true&page[number]=1&page[size]=25",
        "first": "{{API_HOST}}/public/arbo-role?filter[active]=true&page[number]=1&page[size]=25",
        "last": "{{API_HOST}}/public/arbo-role?filter[active]=true&page[number]=1&page[size]=25",
        "prev": null,
        "next": null
    },
    "meta": {
        "total": 4,
        "perPage": 25,
        "totalPages": 1
    }
}
```

### 2. Create the user

**Sample Request**

```json
POST /api/pubic/user/internal
Authorization: Bearer [Your Access Token]
Body:
{
  "type": "internal",
  "roleId": "abcdef12-3456-7890-abcd-ef1234567890",
  "username": "ExampleUser",
  "active": true,
  "hasSystemAccess": true,
  "dateStart": "2024-01-01T00:00:00Z",
  "person": {
    "mail": "exampleuser@demo.local",
    "phone": "06123456789",
    "initials": "E.",
    "surname": "User",
    "nickname": "Example",
    "gender": "X"
  }
}
```

**Sample Response**

```json
{
    "message": "success",
    "status": 201,
    "errors": [],
    "data": {
        "id": "0a2454c8-5b11-45c4-b49f-2c0fe548b468",
        "externalKey": null,
        "username": "ExampleUser",
        "userTypeId": 1,
        "type": "internal",
        "arboRole": {
            "id": "abcdef12-3456-7890-abcd-ef1234567890",
            "name": "Casemanager",
            "code": null,
            "externalKey": null,
            "migrationKey": null,
            "active": true
        },
        "employerRole": null,
        "person": {
            "id": null,
            "name": "User, E.",
            "surname": "User",
            "initials": "E.",
            "nickname": "Example",
            "primaryEmail": "exampleuser@demo.local"
        },
        "isActive": true,
        "dossiersCount": 0,
        "tasksCount": 0
    },
    "traceId": "411eb645-acc3-46b7-ab1d-929c12750a32"
}
```

### 3. Determine Objects for Authorization

**Sample Request**

```json
GET /api/public/organizational-unit
Authorization: Bearer [Your Access Token]
Body: [empty]
```

**Sample Response**

```json
{
    "data": [
        {
            "id": "098967f9-1946-438a-af25-4684ddfaf94f",
            "externalKey": null,
            "migrationKey": null,
            "name": "Catering",
            "code": null,
            "organizationalUnitType": {
                "id": "aea2428e-f58d-4943-9c04-0c8e3734c48f",
                "externalKey": "|type:department|",
                "name": "Afdeling",
                "color": "#990000",
                "legalEntity": false,
                "active": true,
                "dateCreated": "2025-01-07 15:17:55",
                "dateUpdated": "2025-01-07 15:17:55"
            },
            "company": {
                "legalName": null,
                "legalForm": null,
                "relationNumber": null,
                "normHours": null,
                "kvkNumber": null,
                "vatNumber": null,
                "uwv": {
                    "registrationNumber": null,
                    "riskCode": null,
                    "sectorId": null,
                    "payrollTaxIdentificationNumber": null
                }
            },
            "dateStart": null,
            "dateEnd": null,
            "dateCreated": "2025-01-07 15:18:30",
            "dateUpdated": "2025-01-07 15:18:30"
        },
        ... // More results
    ],
    "links": {
        "self": "{{API_HOST}}/public/organizational-unit?page[number]=1&page[size]=25",
        "first": "{{API_HOST}}/public/organizational-unit?page[number]=1&page[size]=25",
        "last": "{{API_HOST}}/public/organizational-unit?page[number]=1&page[size]=25",
        "prev": null,
        "next": null
    },
    "meta": {
        "total": 3,
        "perPage": 25,
        "totalPages": 1
    }
}
```

### 4. Add Authorization to the Created User

**Sample Request**

```json
POST /api/public/user/authorization
Authorization: Bearer [Your Access Token]
Body: 
{
  "id": "0a2454c8-5b11-45c4-b49f-2c0fe548b468", // ID of the newly created user
  "authorizations": {
    "cleaning": "clean-all", // Clean all authorizations, if not present, the authorizations will be extended
    "organizationalUnits": [
      {
        "id": "098967f9-1946-438a-af25-4684ddfaf94f", 
        "authLevel": "authorized",
        "childLevel": "authorized"
      },
    ]
  }
}
```

**Sample Response**

```json
{
    "message": "success",
    "status": 201,
    "errors": [],
    "data": {
        "id": "5779553a-f4ff-4fdb-be3b-e749bb92d629",
        "externalKey": null,
        "username": "deleted_10004565",
        "type": "internal",
        "authorizations": [
            {
                "organizationalUnit": {
                    "id": "098967f9-1946-438a-af25-4684ddfaf94f",
                    "externalKey": null,
                    "migrationKey": null,
                    "name": "Catering",
                    "code": null,
                    "organizationalUnitType": {
                        "id": "aea2428e-f58d-4943-9c04-0c8e3734c48f",
                        "externalKey": "|type:department|",
                        "name": "Afdeling",
                        "color": "#990000",
                        "legalEntity": false,
                        "active": true,
                        "dateCreated": "2025-01-07 15:17:55",
                        "dateUpdated": "2025-01-07 15:17:55"
                    },
                    "company": {
                        "legalName": null,
                        "legalForm": null,
                        "relationNumber": null,
                        "normHours": null,
                        "kvkNumber": null,
                        "vatNumber": null,
                        "uwv": {
                            "registrationNumber": null,
                            "riskCode": null,
                            "sectorId": null,
                            "payrollTaxIdentificationNumber": null
                        }
                    },
                    "dateStart": null,
                    "dateEnd": null,
                    "dateCreated": "2025-01-07 15:18:30",
                    "dateUpdated": "2025-01-07 15:18:30"
                },
                "level": "authorized"
            }
        ]
    },
    "traceId": "6445b8e6-a3bc-48b6-ab40-1ea7a0bbac19"
}
```
