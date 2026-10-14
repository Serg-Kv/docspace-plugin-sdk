# Enable the administrator message settings

`POST /api/2.0/settings/messagesettings`

Displays the contact form on the "Sign In" page, allowing users to send a message to the DocSpace administrator in case they encounter any issues while accessing DocSpace.

Operation ID: `enableAdminMessageSettings`

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
| `turnOn` | boolean | No | The global switch for the administrator messaging functionality. Example: `true`. |

Example:

```json
{
  "turnOn": true
}
```

## Responses

### 200 — Message about the result of saving new settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

