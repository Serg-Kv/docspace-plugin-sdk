# Retry a webhook

`PUT /api/2.0/settings/webhook/{id}/retry`

Retries a webhook with the ID specified in the request.

Operation ID: `retryWebhook`

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
| `id` | path | integer (int32) | Yes | The ID extracted from the route parameters. Example: `9846`. |

## Responses

### 200 — Logs of the webhook activities

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The webhook log parameters. |
| `response.id` | integer (int32) | Yes | The webhook log ID. Example: `9846`. |
| `response.configName` | string, nullable | No | The webhook configuration name. Example: `some text`. |
| `response.trigger` | string | No | The webhook trigger type. One of: `All`, `UserCreated`, `UserInvited`, `UserUpdated`, `UserDeleted`, `GroupCreated`, `GroupUpdated`, `GroupDeleted`, `FileCreated`, `FileUploaded`, `FileUpdated`, `FileTrashed`, `FileDeleted`, `FileRestored`, `FileCopied`, and 14 more. Example: `All`. |
| `response.creationTime` | string (date-time) | No | The webhook creation time. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.method` | string, nullable | No | The webhook method. Example: `some text`. |
| `response.route` | string, nullable | No | The webhook route. Example: `some text`. |
| `response.requestHeaders` | string, nullable | No | The webhook request headers. Example: `some text`. |
| `response.requestPayload` | string, nullable | No | The webhook request payload. Example: `some text`. |
| `response.responseHeaders` | string, nullable | No | The webhook response headers. Example: `some text`. |
| `response.responsePayload` | string, nullable | No | The webhook response payload. Example: `some text`. |
| `response.status` | integer (int32) | No | The webhook status. Example: `1234`. |
| `response.delivery` | string (date-time), nullable | No | The webhook delivery time. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Id incorrect

### 401 — Unauthorized

### 404 — Item not found

