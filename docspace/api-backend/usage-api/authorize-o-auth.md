# OAuth2 authorization endpoint

`GET /oauth2/authorize`

Initiates the OAuth2 authorization flow.

Operation ID: `authorizeOAuth`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `response_type` | query | string | Yes | The OAuth 2.0 response type, must be 'code' for authorization code flow. Example: `code`. |
| `client_id` | query | string | Yes | The client identifier issued to the client during registration. Example: `6c7cf17b-1bd3-47d5-94c6-be2d3570e168`. |
| `redirect_uri` | query | string | Yes | The URL to redirect to after authorization is complete. Example: `https://example.com`. |
| `scope` | query | string | Yes | The space-separated list of requested scope permissions. Example: `files:read`. |

## Responses

### 200 — Authorization page

### 400 — Invalid request parameters

