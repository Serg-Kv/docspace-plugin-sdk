# Create a webhook

`POST /api/2.0/settings/webhook`

Creates a new tenant webhook with the parameters specified in the request.

Operation ID: `createWebhook`

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
| `name` | string | Yes | The human-readable name of the webhook configuration. Example: `Winfield Upton`. |
| `uri` | string | Yes | The destination URL where the webhook events will be sent. Example: `some text`. |
| `secretKey` | string, nullable | No | The webhook secret key used to sign the webhook payloads for the security verification. Example: `some text`. |
| `enabled` | boolean | No | Specifies whether the webhook configuration is active or not. Example: `true`. |
| `ssl` | boolean | No | Specifies whether the SSL certificate verification is required or not. Example: `true`. |
| `triggers` | string | No | The webhook trigger type. One of: `All`, `UserCreated`, `UserInvited`, `UserUpdated`, `UserDeleted`, `GroupCreated`, `GroupUpdated`, `GroupDeleted`, `FileCreated`, `FileUploaded`, `FileUpdated`, `FileTrashed`, `FileDeleted`, `FileRestored`, `FileCopied`, and 14 more. Example: `All`. |
| `targetId` | string, nullable | No | Target ID Example: `some text`. |

Example:

```json
{
  "name": "Winfield Upton",
  "uri": "some text",
  "secretKey": "some text",
  "enabled": true,
  "ssl": true,
  "triggers": "All",
  "targetId": "some text"
}
```

## Responses

### 200 — Tenant webhook with its config parameters

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The webhook configuration parameters. |
| `response.id` | integer (int32) | Yes | The webhook ID. Example: `9846`. |
| `response.name` | string, nullable | No | The webhook name. Example: `Winfield Upton`. |
| `response.uri` | string, nullable | No | The webhook URI. Example: `some text`. |
| `response.enabled` | boolean | No | Specifies if the webhooks are enabled or not. Example: `true`. |
| `response.ssl` | boolean | No | The webhook SSL verification (enabled or not). Example: `true`. |
| `response.triggers` | string | No | The webhook trigger type. One of: `All`, `UserCreated`, `UserInvited`, `UserUpdated`, `UserDeleted`, `GroupCreated`, `GroupUpdated`, `GroupDeleted`, `FileCreated`, `FileUploaded`, `FileUpdated`, `FileTrashed`, `FileDeleted`, `FileRestored`, `FileCopied`, and 14 more. Example: `All`. |
| `response.targetId` | string, nullable | No | The webhook target ID. Example: `some text`. |
| `response.createdBy` | object | No | The user parameters. |
| `response.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.createdOn` | string (date-time), nullable | No | The date and time when the webhook was created. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.modifiedBy` | object | No | The user parameters. |
| `response.modifiedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.modifiedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.modifiedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.modifiedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.modifiedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.modifiedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.modifiedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.modifiedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.modifiedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.modifiedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.modifiedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.modifiedOn` | string (date-time), nullable | No | The date and time when the webhook was modified. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.lastFailureOn` | string (date-time), nullable | No | The date and time of the webhook last failure. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.lastFailureContent` | string, nullable | No | The webhook last failure content. Example: `some text`. |
| `response.lastSuccessOn` | string (date-time), nullable | No | The date and time of the webhook last success. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

