# Get all providers

`GET /api/2.0/files/thirdparty/providers`

Returns a list of all providers.

 **Note**: Available provider keys: Dropbox, Box, WebDav, OneDrive, GoogleDrive, kDrive, ownCloud, Nextcloud.

Operation ID: `getAllProviders`

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
| `excludewebdav` | query | boolean | No | Specifies whether WebDAV resources should be excluded from the result.. Example: `true`. |

## Responses

### 200 — List of provider

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.name` | string, nullable | No | The provider name. Example: `Winfield Upton`. |
| `response.key` | string, nullable | No | The provider key. Example: `some text`. |
| `response.connected` | boolean | No | Specifies whether the provider is connected. Example: `true`. |
| `response.oauth` | boolean | No | Specifies if the provider is OAuth. Example: `true`. |
| `response.redirectUrl` | string, nullable | No | The provider redirect URL. Example: `some text`. |
| `response.requiredConnectionUrl` | boolean | No | The required connection URL flag. Example: `true`. |
| `response.clientId` | string, nullable | No | The provider OAuth client ID. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

