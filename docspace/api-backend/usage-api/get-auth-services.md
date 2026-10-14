# Get the authorization services

`GET /api/2.0/settings/authservice`

Returns the authorization services.

Operation ID: `getAuthServices`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Authorization services

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.name` | string, nullable | No | The name of the authorization service. Example: `Winfield Upton`. |
| `response.title` | string, nullable | No | The user-friendly display title of the authorization service. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.description` | string, nullable | No | The brief description of the authorization service. Example: `some text`. |
| `response.instruction` | string, nullable | No | The detailed instructions for configuring or using the authorization service. Example: `some text`. |
| `response.canSet` | boolean | No | Specifies whether the authorization service can be configured by the user. Example: `true`. |
| `response.paid` | boolean | No | Specifies whether the authorization service is paid or not. Example: `true`. |
| `response.props` | object[], nullable | No | The collection of authorization keys associated with the authorization service. |
| `response.props.name` | string, nullable | Yes | The authorization key name. Example: `Winfield Upton`. |
| `response.props.value` | string, nullable | Yes | The authorization key value. Example: `some text`. |
| `response.props.title` | string, nullable | No | The authorization key title. Example: `legacy_1080p_small_wooden_mouse`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

