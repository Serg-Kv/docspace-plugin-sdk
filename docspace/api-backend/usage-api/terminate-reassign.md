# Terminate the data reassignment

`PUT /api/2.0/people/reassign/terminate`

Terminates the data reassignment for the user with the ID specified in the request.

Operation ID: `terminateReassign`

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
| `userId` | string (uuid) | Yes | The user ID whose data is reassigned/removed. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

Example:

```json
{
  "userId": "aae1e103-bca5-9fa1-ba8c-42058b4abf28"
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

### 401 — Unauthorized

