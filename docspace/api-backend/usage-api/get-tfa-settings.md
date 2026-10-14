# Get the TFA settings

`GET /api/2.0/settings/tfaapp`

Returns the current two-factor authentication settings.

Operation ID: `getTfaSettings`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — TFA settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | string, nullable | Yes | The ID of the TFA configuration. Example: `9846`. |
| `response.title` | string, nullable | Yes | The display name or description of the TFA configuration. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.enabled` | boolean | Yes | Indicates whether the TFA configuration is currently active. Example: `true`. |
| `response.avaliable` | boolean | Yes | Indicates whether the TFA configuration can be used. Example: `true`. |
| `response.trustedIps` | string[], nullable | No | The list of IP addresses that are exempt from TFA requirements. |
| `response.mandatoryUsers` | string[] (uuid), nullable | No | The list of user IDs that are required to use TFA. |
| `response.mandatoryGroups` | string[] (uuid), nullable | No | The list of group IDs whose members are required to use TFA. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

