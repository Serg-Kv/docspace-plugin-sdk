# Invite users

`POST /api/2.0/people/invite`

Invites users specified in the request to the current portal.

Operation ID: `inviteUsers`

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
| `invitations` | object[] | Yes | The list of user invitations. |
| `invitations.type` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `invitations.email` | string (email), nullable | No | The user email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `culture` | string, nullable | No | The culture code of invitations. Example: `some text`. |

Example:

```json
{
  "invitations": [
    {
      "type": "All",
      "email": "Sydney_Roberts4@hotmail.com"
    }
  ],
  "culture": "some text"
}
```

## Responses

### 200 — List of users

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

