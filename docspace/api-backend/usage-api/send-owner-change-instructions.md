# Send the owner change instructions

`POST /api/2.0/settings/owner`

Sends the instructions to change the DocSpace owner.

Operation ID: `sendOwnerChangeInstructions`

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
| `ownerId` | string (uuid) | Yes | The ID of the owner whose settings are being managed. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |

Example:

```json
{
  "ownerId": "75a5f745-f697-4418-b38d-0fe0d277e258"
}
```

## Responses

### 200 — Message about changing the portal owner

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The owner change instructions parameters. |
| `response.status` | integer (int32) | No | The owner change instructions status. Example: `1234`. |
| `response.message` | string, nullable | No | The owner change instructions message. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Owner's email is not activated

### 401 — Unauthorized

### 403 — Collaborator can not be an owner

