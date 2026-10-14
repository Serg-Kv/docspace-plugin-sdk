# Terminate the data deletion

`PUT /api/2.0/people/remove/terminate`

Terminates the data deletion for the user with the ID specified in the request.

Operation ID: `terminateRemove`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `userId` | string (uuid) | Yes | The user ID whose data is reassigned/removed. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

Example:

```json
{
  "userId": "aae1e103-bca5-9fa1-ba8c-42058b4abf28"
}
```

## Responses

### 200 — OK

### 401 — Unauthorized

