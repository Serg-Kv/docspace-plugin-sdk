# Save the greeting settings

`POST /api/2.0/settings/greetingsettings`

Saves the greeting settings specified in the request to the current portal.

Operation ID: `saveGreetingSettings`

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
| `title` | string, nullable | Yes | The title of the tenant greeting settings. Example: `legacy_1080p_small_wooden_mouse`. |

Example:

```json
{
  "title": "legacy_1080p_small_wooden_mouse"
}
```

## Responses

### 200 — Message about saving greeting settings successfully

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

