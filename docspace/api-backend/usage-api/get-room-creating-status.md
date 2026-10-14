# Get the room creation progress

`GET /api/2.0/files/rooms/fromtemplate/status`

Returns the progress of creating a room from the template.

Operation ID: `getRoomCreatingStatus`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Status

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The progress parameters of creating a room from the template. |
| `response.roomId` | integer (int32) | Yes | The room ID. Example: `9846`. |
| `response.progress` | number (double) | Yes | The progress of creating a room from the template. Example: `-8.5`. |
| `response.error` | string, nullable | Yes | The error message that is sent when a room is not created successfully from the template. Example: `some text`. |
| `response.isCompleted` | boolean | Yes | Specifies whether the process of creating a room from the template is completed. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

