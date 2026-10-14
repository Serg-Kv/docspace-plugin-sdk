# Get cookies lifetime

`GET /api/2.0/settings/cookiesettings`

Returns the cookies lifetime value in minutes.

Operation ID: `getCookieSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Lifetime value in minutes

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The cookie settings. |
| `response.lifeTime` | integer (int32) | Yes | The cookie lifetime value in minutes. Example: `1234`. |
| `response.enabled` | boolean | Yes | Specifies if the cookie settings are enabled or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

