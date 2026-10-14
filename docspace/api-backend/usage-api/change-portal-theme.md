# Change the portal theme

`PUT /api/2.0/people/theme`

Changes the current portal theme.

Operation ID: `changePortalTheme`

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
| `theme` | string | Yes | The theme type. One of: `Base`, `Dark`, `System`. Example: `Base`. |

Example:

```json
{
  "theme": "Base"
}
```

## Responses

### 200 — Theme

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The theme parameters. |
| `response.theme` | string | No | The theme type. One of: `Base`, `Dark`, `System`. Example: `Base`. |
| `response.lastModified` | string (date-time) | No | The last modified date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

