# Get status of room template creation

`GET /api/2.0/files/roomtemplate/status`

Returns the progress status of the room template creation process.

Operation ID: `getRoomTemplateCreatingStatus`

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
| `response` | object | No | The room template status. |
| `response.templateId` | integer (int32) | Yes | The room template ID. Example: `1234`. |
| `response.progress` | number (double) | Yes | The progress of the room template creation process. Example: `-8.5`. |
| `response.error` | string, nullable | No | The error message that is sent when the room template is not created successfully. Example: `some text`. |
| `response.isCompleted` | boolean | Yes | Specifies whether the process of creating the room template is completed. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

