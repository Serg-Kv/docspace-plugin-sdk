# Resend the room invitations

`POST /api/2.0/files/rooms/{id}/resend`

Resends the email invitations to a room with the ID specified in the request to the selected users.

Operation ID: `resendEmailInvitations`

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
| `id` | path | integer (int32) | Yes | The room ID. Example: `9846`. |

## Request body

The user invitation parameters.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `usersIds` | string[] (uuid), nullable | No | The list of user IDs. |
| `resendAll` | boolean | No | Specifies whether to resend all user invitations or not. Example: `true`. |

Example:

```json
{
  "usersIds": [
    "75a5f745-f697-4418-b38d-0fe0d277e258"
  ],
  "resendAll": true
}
```

## Responses

### 200 — Ok

### 401 — Unauthorized

