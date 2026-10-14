# Get user groups

`GET /api/2.0/group/user/{userid}`

Returns a list of groups for the user with the ID specified in the request.

Operation ID: `getGroupByUserId`

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
| `userid` | path | string (uuid) | Yes | The user ID. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |

## Responses

### 200 — List of groups

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | string (uuid) | Yes | The group ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.name` | string, nullable | Yes | The group name. Example: `Group Name`. |
| `response.manager` | string, nullable | No | The group manager. Example: `Jake.Zazhitski`. |
| `response.isSystem` | boolean, nullable | No | Indicates whether the group is a system group. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

