# Create a new OAuth2 client

`POST /api/2.0/clients`

Creates a new OAuth2 client with the specified configuration. The client will be created with the provided scopes, redirect URIs, and other settings. Returns the created client details including the generated client ID.

Operation ID: `createClient`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `name` | string | No | The client name. Example: `Example Client`. |
| `description` | string | No | The client description. Example: `Description of the client`. |
| `logo` | string | No | The client logo in base64 format. Example: `data:image/png;base64,...`. |
| `scopes` | string[] | No | The client scopes. |
| `allow_pkce` | boolean | No | Indicates whether PKCE is allowed for the client. Example: `true`. |
| `is_public` | boolean | No | Indicates whether the client is accessible by third-party tenants. Example: `false`. |
| `website_url` | string | No | The URL to the client's website. Example: `http://example.com`. |
| `terms_url` | string | No | The URL to the client's terms of service. Example: `http://example.com/terms`. |
| `policy_url` | string | No | The URL to the client's privacy policy. Example: `http://example.com/policy`. |
| `redirect_uris` | string[] | Yes | The list of allowed redirect URIs. |
| `allowed_origins` | string[] | Yes | The list of allowed CORS origins. |
| `logout_redirect_uri` | string | No | The list of allowed logout redirect URIs. Example: `http://example.com/logout`. |

Example:

```json
{
  "name": "Example Client",
  "description": "Description of the client",
  "logo": "data:image/png;base64,...",
  "scopes": [
    "read",
    "write"
  ],
  "allow_pkce": true,
  "is_public": false,
  "website_url": "http://example.com",
  "terms_url": "http://example.com/terms",
  "policy_url": "http://example.com/policy",
  "redirect_uris": [
    "http://example.com/redirect"
  ],
  "allowed_origins": [
    "http://example.com"
  ],
  "logout_redirect_uri": "http://example.com/logout"
}
```

## Responses

### 201 — Client successfully created

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

### 400 — Invalid request - missing required fields or validation failed

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 403 — Insufficient permissions to create a client

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

