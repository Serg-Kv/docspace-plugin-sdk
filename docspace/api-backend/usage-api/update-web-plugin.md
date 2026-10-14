# Update a web plugin

`PUT /api/2.0/settings/webplugins/{name}`

Updates a web plugin with the parameters specified in the request.

Operation ID: `updateWebPlugin`

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
| `name` | path | string | Yes | The web plugin name. Example: `Winfield Upton`. |

## Request body

The configuration settings for the web plugin instance.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `enabled` | boolean | No | Controls whether the web plugin is active and operational. Example: `true`. |
| `settings` | string, nullable | Yes | The JSON-formatted configuration settings for the web plugin. Example: `some text`. |

Example:

```json
{
  "enabled": true,
  "settings": "some text"
}
```

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — Plugins disabled

