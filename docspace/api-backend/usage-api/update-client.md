# Update an existing OAuth2 client

`PUT /api/2.0/clients/{clientId}`

Updates the configuration of an existing OAuth2 client, allowing modifications to the client name, description, redirect URIs, and other settings. The client ID cannot be modified.

Operation ID: `updateClient`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `clientId` | path | string | Yes | The client identifier. |

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `name` | string | No | The client name. Example: `Updated Client`. |
| `description` | string | No | The client description Example: `Updated description of the client`. |
| `logo` | string | No | The client logo in base64 format. Example: `data:image/png;base64,...`. |
| `allow_pkce` | boolean | No | Indicates whether PKCE is allowed for the client. Example: `true`. |
| `is_public` | boolean | No | Indicates whether the client is accessible by third-party tenants. Example: `false`. |
| `allowed_origins` | string[] | No | The allowed origins for the client. |

Example:

```json
{
  "name": "Updated Client",
  "description": "Updated description of the client",
  "logo": "data:image/png;base64,...",
  "allow_pkce": true,
  "is_public": false,
  "allowed_origins": [
    "http://allowed.origin"
  ]
}
```

## Responses

### 200 — Client successfully updated

Content type: `application/json`

Type: object.

### 400 — Invalid request - missing required fields or validation failed

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 403 — Insufficient permissions to update client

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

