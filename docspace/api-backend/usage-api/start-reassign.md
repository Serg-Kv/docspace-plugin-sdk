# Start the data reassignment

`POST /api/2.0/people/reassign/start`

Starts the data reassignment for the user with the ID specified in the request.

Operation ID: `startReassign`

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
| `fromUserId` | string (uuid) | Yes | The user ID whose data will be reassigned to another user. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `toUserId` | string (uuid) | Yes | The user ID to whom all the data will be reassigned. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `deleteProfile` | boolean | No | Specifies whether to delete a profile when the data reassignment will be finished or not. Example: `true`. |

Example:

```json
{
  "fromUserId": "75a5f745-f697-4418-b38d-0fe0d277e258",
  "toUserId": "75a5f745-f697-4418-b38d-0fe0d277e258",
  "deleteProfile": true
}
```

## Responses

### 200 — Reassignment progress

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

### 400 — Can not reassign data to user or from user

### 401 — Unauthorized

