# Set the Developer Tools access settings

`POST /api/2.0/settings/devtoolsaccess`

Sets the Developer Tools access settings for the portal.

Operation ID: `setTenantDevToolsAccessSettings`

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
| `limitedAccessForUsers` | boolean | No | Determines if users have restricted access to the Developer Tools. Example: `true`. |

Example:

```json
{
  "limitedAccessForUsers": true
}
```

## Responses

### 200 — Developer Tools access settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The Developer Tools access settings. |
| `response.limitedAccessForUsers` | boolean | No | Specifies if the Developer Tools access are limited for users or not. Example: `true`. |
| `response.lastModified` | string (date-time) | No | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

