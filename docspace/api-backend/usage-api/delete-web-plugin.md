# Delete a web plugin

`DELETE /api/2.0/settings/webplugins/{name}`

Deletes a web plugin by the name specified in the request.

Operation ID: `deleteWebPlugin`

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

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — Plugins disabled

