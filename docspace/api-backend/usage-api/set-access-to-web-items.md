# Set the security settings to modules

`PUT /api/2.0/settings/security/access`

Sets the security settings to the modules with the IDs specified in the request.

Operation ID: `setAccessToWebItems`

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
| `items` | object[], nullable | No | The list of module security configurations. |
| `items.key` | string, nullable | No | Example: `some text`. |
| `items.value` | boolean | No | Example: `true`. |

Example:

```json
{
  "items": [
    {
      "key": "some text",
      "value": true
    }
  ]
}
```

## Responses

### 200 — Security settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.webItemId` | string, nullable | No | The module ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.users` | object[], nullable | No | The list of users with the access to the module. |
| `response.users.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.users.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.users.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.users.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.users.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.users.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.users.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.users.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.users.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.users.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.users.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.groups` | object[], nullable | No | The list of groups with the access to the module. |
| `response.groups.id` | string (uuid) | Yes | The group ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.groups.name` | string, nullable | Yes | The group name. Example: `Group Name`. |
| `response.groups.manager` | string, nullable | No | The group manager. Example: `Jake.Zazhitski`. |
| `response.groups.isSystem` | boolean, nullable | No | Indicates whether the group is a system group. Example: `true`. |
| `response.enabled` | boolean | No | Specifies if the security settings are enabled or not. Example: `true`. |
| `response.isSubItem` | boolean | No | Specifies if the module is a subitem or not. Example: `false`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — Security settings are disabled for an open portal

