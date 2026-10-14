# Unlink a third-pary account

`DELETE /api/2.0/people/thirdparty/unlinkaccount`

Unlinks a third-party account specified in the request from the user profile.

Operation ID: `unlinkThirdPartyAccount`

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
| `provider` | query | string | No | The provider name. Example: `some text`. |

## Responses

### 200 — OK

### 401 — Unauthorized

