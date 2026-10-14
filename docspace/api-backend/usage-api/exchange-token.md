# OAuth2 token endpoint

`POST /oauth2/token`

Exchanges an authorization code specified in the request for the access token.

Operation ID: `exchangeToken`

## Request body

Content type: `application/x-www-form-urlencoded`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `grant_type` | string | No | The OAuth2 grant type, must be 'authorization_code' for the authorization code flow. Example: `authorization_code`. |
| `code` | string | No | A temporary authorization code that is sent to the client to be exchanged for a token. Example: `abcde`. |
| `redirect_uri` | string | No | The URL where the user will be redirected after successful or unsuccessful authentication. Example: `https://example.com`. |
| `client_id` | string | No | The client identifier issued to the client during registration. Example: `6c7cf17b-1bd3-47d5-94c6-be2d3570e168`. |
| `client_secret` | string | No | The client secret issued to the client during registration. Example: `6c7cf17b-1bd3-47d5-94c6-be2d3570e168`. |

## Responses

### 200 — The authorization code was successfully exchanged for the access token

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `access_token` | string | No | The access token issued by the authorization server. Example: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...`. |
| `token_type` | string | No | The type of token issued, typically 'Bearer'. Example: `Bearer`. |
| `expires_in` | integer | No | The number of seconds until the access token expires. Example: `3600`. |
| `refresh_token` | string | No | The token used to obtain a new access token when the current one expires. Example: `def502...`. |

### 400 — Invalid request parameters

