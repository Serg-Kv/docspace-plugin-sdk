# OAuth2 consent endpoint

`POST /oauth2/authorize`

Sends a consent request with the specified parameters.

Operation ID: `submitConsent`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Request body

Content type: `multipart/form-data`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `client_id` | string | No | The client identifier issued to the client during registration. Example: `6c7cf17b-1bd3-47d5-94c6-be2d3570e168`. |
| `state` | string | No | The random string used to solve the CSRF vulnerability problem. Example: `abcde`. |
| `scope` | string | No | The space-separated list of requested scope permissions. Example: `files:read`. |

## Responses

### 302 — Redirect to the client's redirect URI with authorization code

### 400 — Invalid request parameters

