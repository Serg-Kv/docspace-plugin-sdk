# Perform form filling action

`PUT /api/2.0/files/file/{fileId}/manageformfilling`

Performs the specified form filling action.

Operation ID: `manageFormFilling`

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
| `fileId` | path | string | Yes |  |

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `formId` | integer (int32) | Yes | The ID of the form to manage. Example: `1234`. |
| `action` | string | No | The action to perform on the form. One of: `Stop`, `Resume`. Example: `Stop`. |

Example:

```json
{
  "formId": 1234,
  "action": "Stop"
}
```

## Responses

### 200 — Successfully processed the form filling action

### 401 — Unauthorized

### 403 — You do not have enough permissions to perform this action

