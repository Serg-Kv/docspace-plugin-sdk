# Get clients

`GET /api/2.0/clients`

Retrieves a paginated list of OAuth2 clients. The results can be paginated using the 'limit' parameter and the last seen client ID or creation date.

Operation ID: `getClients`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `limit` | query | integer (int32) | Yes | The maximum number of results returned per page. |
| `last_client_id` | query | string | No | The ID of the last retrieved client. |
| `last_created_on` | query | string (date-time) | No | The creation date of the last retrieved client. |

## Responses

### 200 — Client list successfully retrieved

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `data` | object | No | The paginated data. |
| `limit` | integer (int32) | No | The maximum number of results returned per page. |
| `last_client_id` | string | No | The identifier of the last retrieved client. |
| `last_created_on` | string (date-time) | No | The creation date of the last retrieved client. |

### 400 — Invalid pagination parameters

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 403 — Insufficient permissions to create a client list

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

