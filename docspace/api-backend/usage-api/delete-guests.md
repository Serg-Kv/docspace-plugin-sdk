# Delete guests

`DELETE /api/2.0/people/guests`

Deletes guests from the list and excludes them from rooms to which they were invited.

Operation ID: `deleteGuests`

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
| `userIds` | string[] (uuid), nullable | No | The list of user IDs. |
| `resendAll` | boolean | No | Specifies whether to resend invitation letters to all the users or not. Example: `true`. |

Example:

```json
{
  "userIds": [
    "75a5f745-f697-4418-b38d-0fe0d277e258"
  ],
  "resendAll": true
}
```

## Responses

### 200 — Request parameters for deleting guests

### 401 — Unauthorized

### 403 — No permissions to perform this action

