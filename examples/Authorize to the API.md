# Authorize to the API

## Retrieve Bearer Token

- 

### Request Details

- To retrieve the token, provide the client ID and client secret as part of the request headers or body as specified by the API.

### Sample Request

```json
POST /api/auth/partner/token
Authorization: Basic
Body:
{
    "grant_type": "client_credentials",
    "client_id": "{{Client_ID}}",
    "client_secret": "{{Client_Secret}}",
    "scope": {
        "employer": ["create", "update", "read", "delete"],
        "organizationalunit": ["create", "update", "read", "delete"],
        "employee": ["create", "update", "read", "delete"],
        "user": ["create", "update"],
        "absencecourse": ["create", "update", "read", "delete"],
        "employment": ["create", "update", "read", "delete"],
        "user_roles": ["read"],
        "employmenttype": ["read"],
        "employercontract": ["read"],
        "absencereason": ["read"]
    }
}
```

### Sample Response

```json
{
    "token_type": "Bearer",
    "expires_in": 10800,
    "access_token": "eyJ0**********WarqQ"
}
```