# Set public settings

`PUT /api/2.0/files/roomtemplate/public`

Sets the public settings for the room template with the ID specified in the request.

Operation ID: `setPublicSettings`

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
| `id` | integer (int32) | Yes | The room template ID. Example: `9846`. |
| `public` | boolean | No | Specifies whether the room template is public or not. Example: `true`. |

Example:

```json
{
  "id": 9846,
  "public": true
}
```

## Responses

### 200 — Ok

### 401 — Unauthorized

