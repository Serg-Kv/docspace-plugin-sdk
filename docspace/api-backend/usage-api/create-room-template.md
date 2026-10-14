# Start creating room template

`POST /api/2.0/files/roomtemplate`

Starts creating the room template.

Operation ID: `createRoomTemplate`

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
| `roomId` | integer (int32) | Yes | The room template ID. Example: `9846`. |
| `title` | string, nullable | No | The room template title. Example: `legacy_1080p_small_wooden_mouse`. |
| `logo` | object | No | The logo request parameters. |
| `logo.tmpFile` | string, nullable | No | The path to the temporary image file. Example: `some text`. |
| `logo.x` | integer (int32) | No | The X coordinate of the rectangle starting point. Example: `1234`. |
| `logo.y` | integer (int32) | No | The Y coordinate of the rectangle starting point. Example: `1234`. |
| `logo.width` | integer (int32) | No | The rectangle width. |
| `logo.height` | integer (int32) | No | The rectangle height. |
| `copyLogo` | boolean | No | Specifies whether to copy room logo or not. Example: `true`. |
| `share` | string[], nullable | No | The collection of email addresses of users with whom to share a room. |
| `groups` | string[] (uuid), nullable | No | The collection of groups with whom to share a room. |
| `public` | boolean | No | Specifies whether the room template is public or not. Example: `true`. |
| `tags` | string[], nullable | No | The collection of tags. |
| `color` | string, nullable | No | The color of the room template. Example: `some text`. |
| `cover` | string, nullable | No | The cover of the room template. Example: `some text`. |
| `quota` | integer (int64), nullable | No | Room quota Example: `1234`. |

Example:

```json
{
  "roomId": 9846,
  "title": "legacy_1080p_small_wooden_mouse",
  "logo": {
    "tmpFile": "some text",
    "x": 1234,
    "y": 1234,
    "width": 0,
    "height": 0
  },
  "copyLogo": true,
  "share": [
    "some text"
  ],
  "groups": [
    "75a5f745-f697-4418-b38d-0fe0d277e258"
  ],
  "public": true,
  "tags": [
    "some text"
  ],
  "color": "some text",
  "cover": "some text",
  "quota": 1234
}
```

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

