# Check data for reassignment need

`GET /api/2.0/people/reassign/necessary`

Checks whether the reassignment of rooms and shared files is required.

Operation ID: `necessaryReassign`

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
| `UserId` | query | string (uuid) | No | The user ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `Type` | query | string | No | The expected user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |

## Responses

### 200 — Boolean value: true if neccessary reassign

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

### 401 — Unauthorized

