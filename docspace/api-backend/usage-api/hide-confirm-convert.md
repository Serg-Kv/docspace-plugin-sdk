# Hide the confirmation dialog when converting

`PUT /api/2.0/files/hideconfirmconvert`

Hides the confirmation dialog for saving the file copy in the original format when converting a file.

Operation ID: `hideConfirmConvert`

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
| `save` | boolean | No | Specifies whether to set the specified settings or not. Example: `true`. |

Example:

```json
{
  "save": true
}
```

## Responses

### 200 — Boolean value: true if the operation is successful

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The module information. |
| `response.id` | string (uuid) | No | The module ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.appName` | string, nullable | No | The module product class name. Example: `some text`. |
| `response.title` | string, nullable | No | The module product class name. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.link` | string, nullable | No | The URL to the module start page. Example: `some text`. |
| `response.iconUrl` | string, nullable | No | The module icon URL. Example: `some text`. |
| `response.imageUrl` | string, nullable | No | The module large image URL. Example: `some text`. |
| `response.helpUrl` | string, nullable | No | The module help URL. Example: `some text`. |
| `response.description` | string, nullable | No | The module description. Example: `some text`. |
| `response.isPrimary` | boolean | No | Specifies if the module is primary or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

