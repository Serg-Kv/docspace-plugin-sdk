# Get an invitation link

`GET /api/2.0/portal/users/invite/{employeeType}`

Returns an invitation link for joining the portal.

Operation ID: `getInvitationLink`

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
| `employeeType` | path | string | Yes | The type of employee role for the invitation link (All, RoomAdmin, Guest, DocSpaceAdmin, User). One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |

## Responses

### 200 — Invitation link

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | string | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

