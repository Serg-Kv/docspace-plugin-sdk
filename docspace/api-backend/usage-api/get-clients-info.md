# Get detailed information of clients

`GET /api/2.0/clients/info`

Retrieves a paginated list of information for all clients.

Operation ID: `getClientsInfo`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `limit` | query | integer (int32) | Yes | The maximum number of results returned per page. |
| `last_client_id` | query | string | No | The identifier of the last retrieved client. |
| `last_created_on` | query | string (date-time) | No | The creation date of the last retrieved client. |

## Responses

### 200 — Successfully retrieved clients info

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `data` | object | No | The paginated client data. |
| `limit` | integer (int32) | No | The maximum number of results returned per page. |
| `last_client_id` | string | No | The identifier of the last retrieved client. |
| `last_created_on` | string (date-time) | No | The creation date of the last retrieved client. |

### 400 — Bad request

### 429 — Too many requests

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `reason` | string | No | The human-readable error explanation. |

### 500 — Internal server error

