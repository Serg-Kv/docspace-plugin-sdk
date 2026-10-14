# Get web plugins

`GET /api/2.0/settings/webplugins`

Returns the portal web plugins.

Operation ID: `getWebPlugins`

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
| `enabled` | query | boolean | No | The optional filter for the plugin enabled state. Example: `true`. |

## Responses

### 200 — Web plugin

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.name` | string, nullable | Yes | The web plugin name. Example: `Winfield Upton`. |
| `response.version` | string, nullable | Yes | The web plugin version. Example: `some text`. |
| `response.minDocSpaceVersion` | string, nullable | No | The minimum version of DocSpace with which the plugin is guaranteed to work. Example: `some text`. |
| `response.description` | string, nullable | Yes | The web plugin description. Example: `some text`. |
| `response.license` | string, nullable | Yes | The web plugin license. Example: `some text`. |
| `response.author` | string, nullable | Yes | The web plugin author. Example: `some text`. |
| `response.homePage` | string, nullable | Yes | The web plugin home page URL. Example: `some text`. |
| `response.pluginName` | string, nullable | Yes | The name by which the web plugin is registered in the window object. Example: `some text`. |
| `response.scopes` | string, nullable | Yes | The web plugin scopes. Example: `some text`. |
| `response.image` | string, nullable | Yes | The web plugin image. Example: `some text`. |
| `response.createBy` | object | Yes | The user parameters. |
| `response.createBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.createBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.createBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.createBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.createBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.createBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.createBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.createBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.createBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.createBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.createBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.createOn` | string (date-time) | Yes | The date and time when the web plugin was created. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.enabled` | boolean | Yes | Specifies if the web plugin is enabled or not. Example: `true`. |
| `response.system` | boolean | Yes | Specifies if the web plugin is system or not. Example: `true`. |
| `response.url` | string, nullable | Yes | The web plugin URL. Example: `some text`. |
| `response.settings` | string, nullable | Yes | The web plugin settings. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — Plugins disabled

