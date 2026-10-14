# Sends an invitation email

`POST /api/2.0/settings/sendjoininvite`

Sends an invitation email with a link to the DocSpace.

Operation ID: `sendJoinInviteMail`

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `email` | string (email), nullable | Yes | The email address used for sending administrator messages. Example: `Sydney_Roberts4@hotmail.com`. |
| `culture` | string, nullable | No | The locale identifier for message localization. Example: `some text`. |

Example:

```json
{
  "email": "Sydney_Roberts4@hotmail.com",
  "culture": "some text"
}
```

## Responses

### 200 — Message about sending a link to confirm joining the DocSpace

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Incorrect email or email already exists

### 403 — No permissions to perform this action

### 429 — Request limit is exceeded

