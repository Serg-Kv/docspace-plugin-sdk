# Get the room tags

`GET /api/2.0/files/tags`

Returns a list of custom room tags.

Operation ID: `getRoomTagsInfo`

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
| `count` | query | integer (int32) | No | Gets or sets the number of tag results to retrieve. This property specifies the maximum amount of tag data to be included in the result set. Example: `1234`. |
| `startIndex` | query | integer (int32) | No | Represents the starting index from which the tags' information will be retrieved. This property is used to define the offset for pagination when retrieving a list of tags. It determines the point in the data set from which the retrieval begins. Example: `1234`. |
| `filterValue` | query | string | No | Gets or sets the text value used for searching tags. This property is typically used as a filter value when retrieving tag information. Example: `some text`. |

## Responses

### 200 — List of tag names

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

