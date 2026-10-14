# Check the default white label logo text

`GET /api/2.0/settings/whitelabel/logotext/isdefault`

Specifies if the white label logo text is default or not.

Operation ID: `getIsDefaultWhiteLabelLogoText`

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

### 200 — Request properties of white label logos

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The default white label logo parameters. |
| `response.name` | string, nullable | Yes | The white label logo name. Example: `Winfield Upton`. |
| `response.default` | boolean | Yes | Specifies if the white label logo is default or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

