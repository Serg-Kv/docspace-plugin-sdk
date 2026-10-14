# Get the login settings

`GET /api/2.0/settings/security/loginsettings`

Returns the portal login settings.

Operation ID: `getLoginSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Login settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The login settings parameters. |
| `response.attemptCount` | integer (int32) | Yes | The maximum number of consecutive failed login attempts allowed before triggering account suspension. Example: `1234`. |
| `response.blockTime` | integer (int32) | Yes | The duration (in minutes) for which an account remains suspended after exceeding maximum login attempts. Example: `1234`. |
| `response.checkPeriod` | integer (int32) | Yes | The maximum time (in seconds) allowed for server to process and respond to login requests. Example: `1234`. |
| `response.isDefault` | boolean | Yes | Specifies if these settings are default or not Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

