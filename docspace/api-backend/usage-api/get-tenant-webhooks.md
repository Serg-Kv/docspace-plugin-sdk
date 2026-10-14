# Get webhooks

`GET /api/2.0/settings/webhook`

Returns a list of the tenant webhooks.

Operation ID: `getTenantWebhooks`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of tenant webhooks with their config parameters

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.configs` | object | No | The webhook configuration parameters. |
| `response.configs.id` | integer (int32) | Yes | The webhook ID. Example: `9846`. |
| `response.configs.name` | string, nullable | No | The webhook name. Example: `Winfield Upton`. |
| `response.configs.uri` | string, nullable | No | The webhook URI. Example: `some text`. |
| `response.configs.enabled` | boolean | No | Specifies if the webhooks are enabled or not. Example: `true`. |
| `response.configs.ssl` | boolean | No | The webhook SSL verification (enabled or not). Example: `true`. |
| `response.configs.triggers` | string | No | The webhook trigger type. One of: `All`, `UserCreated`, `UserInvited`, `UserUpdated`, `UserDeleted`, `GroupCreated`, `GroupUpdated`, `GroupDeleted`, `FileCreated`, `FileUploaded`, `FileUpdated`, `FileTrashed`, `FileDeleted`, `FileRestored`, `FileCopied`, and 14 more. Example: `All`. |
| `response.configs.targetId` | string, nullable | No | The webhook target ID. Example: `some text`. |
| `response.configs.createdBy` | object | No | The user parameters. |
| `response.configs.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.configs.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.configs.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.configs.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.configs.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.configs.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.configs.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.configs.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.configs.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.configs.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.configs.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.configs.createdOn` | string (date-time), nullable | No | The date and time when the webhook was created. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.configs.modifiedBy` | object | No | The user parameters. |
| `response.configs.modifiedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.configs.modifiedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.configs.modifiedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.configs.modifiedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.configs.modifiedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.configs.modifiedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.configs.modifiedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.configs.modifiedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.configs.modifiedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.configs.modifiedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.configs.modifiedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.configs.modifiedOn` | string (date-time), nullable | No | The date and time when the webhook was modified. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.configs.lastFailureOn` | string (date-time), nullable | No | The date and time of the webhook last failure. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.configs.lastFailureContent` | string, nullable | No | The webhook last failure content. Example: `some text`. |
| `response.configs.lastSuccessOn` | string (date-time), nullable | No | The date and time of the webhook last success. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.status` | integer (int32) | No | The webhook status. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

