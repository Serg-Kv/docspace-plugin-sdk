# Log out for the user by ID

`PUT /api/2.0/security/activeconnections/logoutall/{userId}`

Logs out from all the active connections for the user with the ID specified in the request.

Operation ID: `logOutAllActiveConnectionsForUser`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `userId` | path | string (uuid) | Yes | The user ID extracted from the route parameters. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — Method not available

