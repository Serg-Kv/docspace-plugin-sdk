# Update the email activation settings

`PUT /api/2.0/settings/emailactivation`

Updates the email activation settings.

Operation ID: `updateEmailActivationSettings`

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
| `show` | boolean | No | Specifies whether the email activation settings are shown or hidden. Example: `true`. |
| `lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |

Example:

```json
{
  "show": true,
  "lastModified": "2008-04-10T06:30:00.0000000+04:00"
}
```

## Responses

### 200 — Updated email activation settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The email activation settings. |
| `response.show` | boolean | No | Specifies whether the email activation settings are shown or hidden. Example: `true`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

