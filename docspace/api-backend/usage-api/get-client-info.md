# Get detailed client information

`GET /api/2.0/clients/{clientId}/info`

Retrieves the detailed information for a client with the ID specified in the request.

Operation ID: `getClientInfo`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `clientId` | path | string | Yes | The client identifier. |

## Responses

### 200 — Successfully retrieved client info

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `name` | string | No | The client name. |
| `description` | string | No | The client description. |
| `scopes` | string[] | No | The client scopes. |
| `client_id` | string | No | The client ID. |
| `website_url` | string | No | The URL to the client's website |
| `terms_url` | string | No | The URL to the client's terms of service. |
| `policy_url` | string | No | The URL to the client's privacy policy. |
| `logo` | string | No | The client logo in base64 format. |
| `authentication_methods` | string[] | No | The authentication methods supported by the client. |
| `is_public` | boolean | No | Indicates whether the client is accessible by third-party tenants. |
| `created_on` | string (date-time) | No | The date and time when the client was created. |
| `created_by` | string | No | The user who created the client. |
| `modified_on` | string (date-time) | No | The date and time when the client was last modified. |
| `modified_by` | string | No | The user who last modified the client. |

### 400 — Bad request

### 429 — Too many requests

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 500 — Internal server error

