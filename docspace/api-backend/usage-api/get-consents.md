# Get user consents

`GET /api/2.0/clients/consents`

Retrieves a paginated list of user consents.

Operation ID: `getConsents`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `limit` | query | integer (int32) | Yes | The maximum number of results returned per page. |
| `last_modified_on` | query | string (date-time) | No | The date when the user consent was last modified. |

## Responses

### 200 — Successfully retrieved user consents

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `data` | object | No | The paginated modification data. |
| `limit` | integer (int32) | No | The maximum number of results returned per page. |
| `last_modified_on` | string (date-time) | No | The date when the user consent was last modified. |

