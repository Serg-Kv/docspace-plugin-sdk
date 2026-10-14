# Save the authorization keys

`POST /api/2.0/settings/authservice`

Saves the authorization keys.

Operation ID: `saveAuthKeys`

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
| `name` | string, nullable | No | The name of the authorization service. Example: `Winfield Upton`. |
| `title` | string, nullable | No | The user-friendly display title of the authorization service. Example: `legacy_1080p_small_wooden_mouse`. |
| `description` | string, nullable | No | The brief description of the authorization service. Example: `some text`. |
| `instruction` | string, nullable | No | The detailed instructions for configuring or using the authorization service. Example: `some text`. |
| `canSet` | boolean | No | Specifies whether the authorization service can be configured by the user. Example: `true`. |
| `paid` | boolean | No | Specifies whether the authorization service is paid or not. Example: `true`. |
| `props` | object[], nullable | No | The collection of authorization keys associated with the authorization service. |
| `props.name` | string, nullable | Yes | The authorization key name. Example: `Winfield Upton`. |
| `props.value` | string, nullable | Yes | The authorization key value. Example: `some text`. |
| `props.title` | string, nullable | No | The authorization key title. Example: `legacy_1080p_small_wooden_mouse`. |

Example:

```json
{
  "name": "Winfield Upton",
  "title": "legacy_1080p_small_wooden_mouse",
  "description": "some text",
  "instruction": "some text",
  "canSet": true,
  "paid": true,
  "props": [
    {
      "name": "Winfield Upton",
      "value": "some text",
      "title": "legacy_1080p_small_wooden_mouse"
    }
  ]
}
```

## Responses

### 200 — Boolean value: true if the authorization keys are changed

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

### 400 — Bad keys

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

