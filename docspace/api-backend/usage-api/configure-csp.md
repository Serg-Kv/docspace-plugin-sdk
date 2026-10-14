# Configure CSP settings

`POST /api/2.0/security/csp`

Configures the CSP (Content Security Policy) settings for the current portal.

Operation ID: `configureCsp`

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
| `domains` | string[], nullable | No | The collection of allowed domains in the Content Security Policy (CSP). |

Example:

```json
{
  "domains": [
    "some text"
  ]
}
```

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

### 400 — Exception in Domains

### 401 — Unauthorized

