# Set room notification status

`POST /api/2.0/settings/notification/rooms`

Sets a notification status for a room with the ID specified in the request.

Operation ID: `setRoomsNotificationStatus`

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
| `roomsId` | any, nullable | No | The target room identifier. |
| `mute` | boolean | No | Specifies whether the notifications will be delivered to the specified room or not. Example: `true`. |

Example:

```json
{
  "roomsId": {
    "int": 1234,
    "string": "some text",
    "boolean": true
  },
  "mute": true
}
```

## Responses

### 200 — Room notification settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The rooms notification settings. |
| `response.disabledRooms` | object[], nullable | No | The list of rooms with the disabled notifications. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

