# Create a room from the template

`POST /api/2.0/files/rooms/fromtemplate`

Creates a room in the "Rooms" section based on the template.

Operation ID: `createRoomFromTemplate`

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
| `templateId` | integer (int32) | Yes | The template ID from which the room to be created. Example: `1234`. |
| `title` | string, nullable | Yes | The room title. Example: `legacy_1080p_small_wooden_mouse`. |
| `logo` | object | No | The logo request parameters. |
| `logo.tmpFile` | string, nullable | No | The path to the temporary image file. Example: `some text`. |
| `logo.x` | integer (int32) | No | The X coordinate of the rectangle starting point. Example: `1234`. |
| `logo.y` | integer (int32) | No | The Y coordinate of the rectangle starting point. Example: `1234`. |
| `logo.width` | integer (int32) | No | The rectangle width. |
| `logo.height` | integer (int32) | No | The rectangle height. |
| `copyLogo` | boolean | No | Specifies whether to copy a logo or not. Example: `true`. |
| `tags` | string[], nullable | No | The collection of tags. |
| `color` | string, nullable | No | The color of the room to be created. Example: `some text`. |
| `cover` | string, nullable | No | The cover of the room to be created. Example: `some text`. |
| `quota` | integer (int64), nullable | No | The room quota. Example: `1234`. |
| `indexing` | boolean, nullable | No | Specifies whether to create a room with indexing. Example: `true`. |
| `denyDownload` | boolean, nullable | No | Specifies whether to deny downloads from the room. Example: `true`. |
| `lifetime` | object | No | The room data lifetime information. |
| `lifetime.deletePermanently` | boolean | No | Specifies whether to permanently delete the room data or not. Example: `true`. |
| `lifetime.period` | string | No | The room data lifetime period. One of: `Day`, `Month`, `Year`. Example: `Day`. |
| `lifetime.value` | integer (int32), nullable | No | Specifies the time period value of the room data lifetime. Example: `1234`. |
| `lifetime.enabled` | boolean, nullable | No | Specifies whether the room data lifetime setting is enabled or not. Example: `true`. |
| `watermark` | object | No | The request parameters for adding watermarks. |
| `watermark.enabled` | boolean, nullable | No | Specifies whether watermarks are on or off. Example: `true`. |
| `watermark.additions` | string | No | The watermark additions. One of: `UserName`, `UserEmail`, `UserIpAdress`, `CurrentDate`, `RoomName`. Example: `UserName`. |
| `watermark.text` | string, nullable | No | The watermark text. Example: `some text`. |
| `watermark.rotate` | integer (int32) | No | The watermark text and image rotate angle. Example: `1234`. |
| `watermark.imageScale` | integer (int32) | No | The watermark image scale. Example: `1234`. |
| `watermark.imageUrl` | string, nullable | No | The path to the temporary image file. Example: `some text`. |
| `watermark.imageHeight` | number (double) | No | The watermark image height. Example: `-8.5`. |
| `watermark.imageWidth` | number (double) | No | The watermark image width. Example: `-8.5`. |
| `private` | boolean, nullable | No | Specifies whether the room to be created is private or not. Example: `true`. |

Example:

```json
{
  "templateId": 1234,
  "title": "legacy_1080p_small_wooden_mouse",
  "logo": {
    "tmpFile": "some text",
    "x": 1234,
    "y": 1234,
    "width": 0,
    "height": 0
  },
  "copyLogo": true,
  "tags": [
    "some text"
  ],
  "color": "some text",
  "cover": "some text",
  "quota": 1234,
  "indexing": true,
  "denyDownload": true,
  "lifetime": {
    "deletePermanently": true,
    "period": "Day",
    "value": 1234,
    "enabled": true
  },
  "watermark": {
    "enabled": true,
    "additions": "UserName",
    "text": "some text",
    "rotate": 1234,
    "imageScale": 1234,
    "imageUrl": "some text",
    "imageHeight": -8.5,
    "imageWidth": -8.5
  },
  "private": true
}
```

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

