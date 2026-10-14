# Get the third-party accounts

`GET /api/2.0/files/thirdparty`

Returns a list of all the connected third-party accounts.

Operation ID: `getThirdPartyAccounts`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of connected providers information

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.auth_data` | object | No | The authentication data. |
| `response.auth_data.login` | string, nullable | No | The authentication login. Example: `some text`. |
| `response.auth_data.password` | string, nullable | No | The authentication password. Example: `vfmf2vO1Kp`. |
| `response.auth_data.rawToken` | string, nullable | No | The authentication raw token. Example: `some text`. |
| `response.auth_data.url` | string (uri), nullable | No | The authentication URL. Example: `some text`. |
| `response.auth_data.provider` | string, nullable | No | The authentication provider. Example: `some text`. |
| `response.auth_data.token` | object | No |  |
| `response.auth_data.token.access_token` | string, nullable | No | Example: `some text`. |
| `response.auth_data.token.refresh_token` | string, nullable | No | Example: `some text`. |
| `response.auth_data.token.expires_in` | integer (int64) | No | Example: `1234`. |
| `response.auth_data.token.client_id` | string, nullable | No | Example: `some text`. |
| `response.auth_data.token.client_secret` | string, nullable | No | Example: `some text`. |
| `response.auth_data.token.redirect_uri` | string (uri), nullable | No | Example: `some text`. |
| `response.auth_data.token.timestamp` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.auth_data.token.isExpired` | boolean | No | Example: `true`. |
| `response.corporate` | boolean | No | Specifies if this is a corporate account or not. Example: `true`. |
| `response.roomsStorage` | boolean | No | Specifies if this is a room storage or not. Example: `true`. |
| `response.customer_title` | string, nullable | No | The customer title. Example: `some text`. |
| `response.provider_id` | integer (int32), nullable | No | The provider ID. Example: `1234`. |
| `response.provider_key` | string, nullable | No | The provider key. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

