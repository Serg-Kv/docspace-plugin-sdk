# Get the progress of updating user type

`GET /api/2.0/people/type/progress/{userid}`

Returns the progress of updating the user type.

Operation ID: `getUserTypeUpdateProgress`

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
| `userid` | path | string (uuid) | Yes | The user ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

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

### 401 — Unauthorized

