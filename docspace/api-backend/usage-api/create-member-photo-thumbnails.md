# Create photo thumbnails

`POST /api/2.0/people/{userid}/photo/thumbnails`

Creates the user photo thumbnails by coordinates of the original image specified in the request.

Operation ID: `createMemberPhotoThumbnails`

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
| `userid` | path | string | Yes | The user ID. Example: `9846`. |

## Request body

The thumbnail request.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `tmpFile` | string, nullable | No | The path to the temporary thumbnail file. Example: `some text`. |
| `x` | integer (int32) | No | The thumbnail horizontal coordinate. Example: `1234`. |
| `y` | integer (int32) | No | The thumbnail vertical coordinate. Example: `1234`. |
| `width` | integer (int32) | No | The thumbnail width. |
| `height` | integer (int32) | No | The thumbnail height. |

Example:

```json
{
  "tmpFile": "some text",
  "x": 1234,
  "y": 1234,
  "width": 0,
  "height": 0
}
```

## Responses

### 200 — Thumbnail parameters

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The thumbnails data parameters. |
| `response.original` | string, nullable | No | The thumbnail original photo. Example: `default_user_photo_size_1280-1280.png`. |
| `response.retina` | string, nullable | No | The thumbnail retina. Example: `default_user_photo_size_360-360.png`. |
| `response.max` | string, nullable | No | The thumbnail maximum size photo. Example: `default_user_photo_size_200-200.png`. |
| `response.big` | string, nullable | No | The thumbnail big size photo. Example: `default_user_photo_size_82-82.png`. |
| `response.medium` | string, nullable | No | The thumbnail medium size photo. Example: `default_user_photo_size_48-48.png`. |
| `response.small` | string, nullable | No | The thumbnail small size photo. Example: `default_user_photo_size_32-32.png`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

### 404 — User not found

