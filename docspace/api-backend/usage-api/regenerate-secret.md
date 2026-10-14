# Regenerate the client secret

`PATCH /api/2.0/clients/{clientId}/regenerate`

Generates a new client secret for the specified OAuth2 client. The old secret will be immediately invalidated. This operation should be used with caution as it requires updating the secret in all client applications.

Operation ID: `regenerateSecret`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `clientId` | path | string | Yes | The client identifier. |

## Responses

### 200 — Client secret successfully regenerated

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `client_secret` | string | No | The newly generated client secret. |

### 400 — Invalid client ID format

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 403 — Insufficient permissions to regenerate client secret

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 404 — Client not found

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 429 — Too many requests - rate limit exceeded

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 500 — Internal server error occurred

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

