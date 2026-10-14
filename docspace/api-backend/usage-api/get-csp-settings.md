# Get CSP settings

`GET /api/2.0/security/csp`

Returns the CSP (Content Security Policy) settings for the current portal.

Operation ID: `getCspSettings`

## Responses

### 200 — Ok

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The CSP (Content Security Policy) parameters. |
| `response.domains` | string[], nullable | Yes | The list of CSP domains. |
| `response.header` | string, nullable | Yes | The CSP header. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

