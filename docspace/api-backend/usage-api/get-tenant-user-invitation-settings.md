# Get the user invitation settings

`GET /api/2.0/settings/invitationsettings`

Returns the portal user invitation settings.

Operation ID: `getTenantUserInvitationSettings`

## Responses

### 200 — portal user invitation settings

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

