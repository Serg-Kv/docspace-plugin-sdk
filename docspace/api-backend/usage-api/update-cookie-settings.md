# Update cookies lifetime

`PUT /api/2.0/settings/cookiesettings`

Updates the cookies lifetime value in minutes.

Operation ID: `updateCookieSettings`

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
| `lifeTime` | integer (int32) | No | The cookie lifetime in minutes. Example: `1234`. |
| `enabled` | boolean | No | Specifies whether the cookie settings are enabled or disabled. Example: `true`. |

Example:

```json
{
  "lifeTime": 1234,
  "enabled": true
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

### 402 — Your pricing plan does not support this option

