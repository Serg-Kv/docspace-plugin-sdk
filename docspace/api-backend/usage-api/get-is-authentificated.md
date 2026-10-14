# Check authentication

`GET /api/2.0/authentication`

Checks if the current user is authenticated or not.

Operation ID: `getIsAuthentificated`

## Responses

### 200 — Boolean value: true if the current user is authenticated

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

