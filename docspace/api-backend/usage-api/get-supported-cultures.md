# Get supported languages

`GET /api/2.0/settings/cultures`

Returns a list of all the available portal languages in the format of a two-letter or four-letter language code (e.g. "de", "en-US", etc.).

Operation ID: `getSupportedCultures`

## Responses

### 200 — List of all the available portal languages

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string[] | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

