# Get the TFA codes

`GET /api/2.0/settings/tfaappcodes`

Returns the two-factor authentication application codes.

Operation ID: `getTfaAppCodes`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of TFA application codes

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 405 — TFA application settings are not available

