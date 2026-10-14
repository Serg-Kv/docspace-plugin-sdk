# Update a comment

`PUT /api/2.0/files/file/{fileId}/comment`

Updates a comment in a file with the ID specified in the request.

Operation ID: `updateFileComment`

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
| `fileId` | path | integer (int32) | Yes | The file ID where the comment is located. Example: `9846`. |

## Request body

The parameters for updating a comment.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `version` | integer (int32) | Yes | The comment version. Example: `1234`. |
| `comment` | string, nullable | No | The comment text. Example: `some text`. |

Example:

```json
{
  "version": 1234,
  "comment": "some text"
}
```

## Responses

### 200 — Updated comment

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

