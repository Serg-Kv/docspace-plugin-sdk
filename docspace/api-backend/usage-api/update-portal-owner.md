# Update the portal owner

`PUT /api/2.0/settings/owner`

Updates the current portal owner with a new one specified in the request.

Operation ID: `updatePortalOwner`

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
| `ownerId` | string (uuid) | Yes | The ID of the owner whose settings are being managed. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |

Example:

```json
{
  "ownerId": "75a5f745-f697-4418-b38d-0fe0d277e258"
}
```

## Responses

### 200 — Ok

### 400 — The user could not be found

### 401 — Unauthorized

### 409

