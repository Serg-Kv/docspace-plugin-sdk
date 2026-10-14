# Set a mobile phone

`POST /api/2.0/authentication/setphone`

Sets a mobile phone for the current user.

Operation ID: `saveMobilePhone`

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
| `mobilePhone` | string, nullable | No | The user's mobile phone number. Example: `some text`. |

Example:

```json
{
  "mobilePhone": "some text"
}
```

## Responses

### 200 — Authentication data

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The authentication token parameters. |
| `response.token` | string, nullable | No | The authentication token. Example: `abcde12345`. |
| `response.expires` | string (date-time) | No | The token expiration time. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.sms` | boolean | No | Specifies if the authentication code is sent by SMS or not. Example: `false`. |
| `response.phoneNoise` | string, nullable | No | The phone number. Example: ``. |
| `response.tfa` | boolean | No | Specifies if the two-factor application is used or not. Example: `false`. |
| `response.tfaKey` | string, nullable | No | The two-factor authentication key. Example: ``. |
| `response.confirmUrl` | string (uri), nullable | No | The confirmation email URL. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

