# Delete the backup

`DELETE /api/2.0/backup/deletebackup/{id}`

Deletes the backup with the ID specified in the request.

Operation ID: `deleteBackup`

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
| `id` | path | string (uuid) | Yes | The backup ID. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |

## Responses

### 200 — Boolean value: true if the operation is successful

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

### 402 — Your pricing plan does not support this option

