# Get client details

`GET /api/2.0/clients/{clientId}`

Retrieves detailed information about a specific OAuth2 client including its name, description, redirect URIs, and scopes.

Operation ID: `getClient`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `clientId` | path | string | Yes | The client identifier. |

## Responses

### 200 — Client details successfully retrieved

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `name` | string | No | The client name. |
| `description` | string | No | The client description. |
| `tenant` | integer (int64) | No | The tenant ID associated with the client. |
| `scopes` | string[] | No | The client scopes. |
| `enabled` | boolean | No | Specifies if the client is currently enabled or not. |
| `client_id` | string | No | The client identifier issued to the client during registration. |
| `client_secret` | string | No | The client secret issued to the client during registration. |
| `website_url` | string | No | The URL to the client's website. |
| `terms_url` | string | No | The URL to the client's terms of service. |
| `policy_url` | string | No | The URL to the client's privacy policy. |
| `logo` | string | No | The URL to the client's logo. |
| `authentication_methods` | string[] | No | The authentication methods supported by the client. |
| `redirect_uris` | string[] | No | The list of allowed redirect URIs. |
| `allowed_origins` | string[] | No | The list of allowed CORS origins. |
| `logout_redirect_uris` | string[] | No | The list of allowed logout redirect URIs. |
| `created_on` | string (date-time) | No | The date and time when the client was created. |
| `created_by` | string | No | The user who created the client. |
| `modified_on` | string (date-time) | No | The date and time when the client was last modified. |
| `modified_by` | string | No | The user who last modified the client. |
| `is_public` | boolean | No | Indicates whether the client is accessible by third-party tenants. |

### 400 — Invalid client ID format

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 403 — Insufficient permissions to view client

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

