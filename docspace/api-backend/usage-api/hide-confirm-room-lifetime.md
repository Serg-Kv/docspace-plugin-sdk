# Hide confirmation dialog when changing room lifetime settings

`PUT /api/2.0/files/hideconfirmroomlifetime`

Hides the confirmation dialog when changing the room lifetime settings.

Operation ID: `hideConfirmRoomLifetime`

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
| `set` | boolean | No | Specifies whether to set the specified settings or not. Example: `true`. |

Example:

```json
{
  "set": true
}
```

## Responses

### 200 — Boolean value: true if the parameter is enabled

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

