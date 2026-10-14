# Get a confirmation email for updating TFA settings

`PUT /api/2.0/settings/tfaappwithlink`

Returns the confirmation email URL for updating TFA settings.

Operation ID: `updateTfaSettingsLink`

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
| `type` | string | No | The two-factor authentication type. One of: `None`, `Sms`, `App`. Example: `None`. |
| `id` | string (uuid) | No | The ID of the user for whom the TFA settings are being configured. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `trustedIps` | string[], nullable | No | The list of IP addresses that bypass TFA verification. |
| `mandatoryUsers` | string[] (uuid), nullable | No | The list of user IDs for whom TFA is mandatory. |
| `mandatoryGroups` | string[] (uuid), nullable | No | The list group IDs whose members must use TFA. |

Example:

```json
{
  "type": "None",
  "id": "aae1e103-bca5-9fa1-ba8c-42058b4abf28",
  "trustedIps": [
    "some text"
  ],
  "mandatoryUsers": [
    "75a5f745-f697-4418-b38d-0fe0d277e258"
  ],
  "mandatoryGroups": [
    "75a5f745-f697-4418-b38d-0fe0d277e258"
  ]
}
```

## Responses

### 200 — Confirmation email URL

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

### 403 — No permissions to perform this action

### 405 — SMS settings are not available/TFA application settings are not available

