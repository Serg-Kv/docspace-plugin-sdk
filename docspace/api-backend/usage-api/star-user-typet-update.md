# Start updating user type

`POST /api/2.0/people/type`

Starts updating the type of the user or guest when reassigning rooms and shared files.

Operation ID: `starUserTypetUpdate`

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
| `type` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `userId` | string (uuid) | No | The user ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `reassignUserId` | string (uuid), nullable | No | The user ID to reassign. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |

Example:

```json
{
  "type": "All",
  "userId": "aae1e103-bca5-9fa1-ba8c-42058b4abf28",
  "reassignUserId": "75a5f745-f697-4418-b38d-0fe0d277e258"
}
```

## Responses

### 200 — Update type progress

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The task progress response parameters. |
| `response.id` | string, nullable | Yes | The task progress ID. Example: `9846`. |
| `response.error` | string, nullable | No | The task progress error message. Example: `some text`. |
| `response.percentage` | integer (int32) | Yes | The percentage of the task progress. Example: `1234`. |
| `response.isCompleted` | boolean | Yes | Specifies if the task peogress is completed or not. Example: `true`. |
| `response.status` | string | Yes | [Created - Created, Running - Running, Completed - Completed, Canceled - Canceled, Failted - Failted] One of: `Created`, `Running`, `Completed`, `Canceled`, `Failted`. Example: `Created`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Can not update user type

### 401 — Unauthorized

