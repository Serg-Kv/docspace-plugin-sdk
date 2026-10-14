# Configure the deep link settings

`POST /api/2.0/settings/deeplink`

Saves the deep link configuration settings for the portal.

Operation ID: `configureDeepLink`

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
| `deepLinkSettings` | object | No | The deep link settings. |
| `deepLinkSettings.handlingMode` | string | No | The deep link handling mode. One of: `ProvideChoice`, `Web`, `App`. Example: `ProvideChoice`. |
| `deepLinkSettings.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |

Example:

```json
{
  "deepLinkSettings": {
    "handlingMode": "ProvideChoice",
    "lastModified": "2008-04-10T06:30:00.0000000+04:00"
  }
}
```

## Responses

### 200 — Deep link configuration updated

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The deep link settings. |
| `response.handlingMode` | string | No | The deep link handling mode. One of: `ProvideChoice`, `Web`, `App`. Example: `ProvideChoice`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Invalid deep link configuration

### 401 — Unauthorized

