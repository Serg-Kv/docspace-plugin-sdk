# Save the white label logos from files

`POST /api/2.0/settings/whitelabel/logos/savefromfiles`

Saves the white label logos from files.

Operation ID: `saveWhiteLabelSettingsFromFiles`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `IsDark` | query | boolean | No | Specifies if the white label logo is for the dark theme or not. Example: `true`. |
| `IsDefault` | query | boolean | No | Specifies if the logo is for a default tenant or not. Example: `true`. |

## Responses

### 200 — Boolean value: true if the operation is sucessful

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

### 409 — No input files

