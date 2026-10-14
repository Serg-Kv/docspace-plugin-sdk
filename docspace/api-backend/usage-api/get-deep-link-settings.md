# Get the deep link settings

`GET /api/2.0/settings/deeplink`

Returns the deep link settings.

Operation ID: `getDeepLinkSettings`

## Responses

### 200 — Ok

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The deep link settings. |
| `response.handlingMode` | string | No | The deep link handling mode. One of: `ProvideChoice`, `Web`, `App`. Example: `ProvideChoice`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

