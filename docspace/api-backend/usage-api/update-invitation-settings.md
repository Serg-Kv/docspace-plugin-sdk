# Update user invitation settings

`PUT /api/2.0/settings/invitationsettings`

Updates the portal user invitation settings.

Operation ID: `updateInvitationSettings`

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
| `allowInvitingMembers` | boolean | No | Specifies whether to allow inviting new DocSpace members through the Contacts section. Example: `true`. |
| `allowInvitingGuests` | boolean | No | Specifies whether to allow all DocSpace members to invite external guests to the rooms. Example: `true`. |

Example:

```json
{
  "allowInvitingMembers": true,
  "allowInvitingGuests": true
}
```

## Responses

### 200 — Updated user invitation settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The user invitation settings. |
| `response.allowInvitingMembers` | boolean | Yes | Specifies whether to allow inviting new DocSpace members through the Contacts section. Example: `true`. |
| `response.allowInvitingGuests` | boolean | Yes | Specifies whether to allow all DocSpace members to invite external guests to the rooms. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

