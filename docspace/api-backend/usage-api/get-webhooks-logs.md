# Get webhook logs

`GET /api/2.0/settings/webhooks/log`

Returns the logs of the webhook activities.

Operation ID: `getWebhooksLogs`

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
| `deliveryFrom` | query | string (date-time) | No | The delivery start time for filtering webhook logs. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `deliveryTo` | query | string (date-time) | No | The delivery end time for filtering webhook logs. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `hookUri` | query | string | No | The destination URL where webhooks are delivered. Example: `some text`. |
| `configId` | query | integer (int32) | No | The webhook configuration identifier. Example: `1234`. |
| `eventId` | query | integer (int32) | No | The unique identifier of the event that triggered the webhook. Example: `1234`. |
| `groupStatus` | query | string | No | The status of the webhook delivery group. One of: `None`, `NotSent`, `Status2xx`, `Status3xx`, `Status4xx`, `Status5xx`. Example: `None`. |
| `userId` | query | string (uuid) | No | The identifier of the user associated with the webhook event. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `trigger` | query | string | No | The type of event that triggered the webhook. One of: `All`, `UserCreated`, `UserInvited`, `UserUpdated`, `UserDeleted`, `GroupCreated`, `GroupUpdated`, `GroupDeleted`, `FileCreated`, `FileUploaded`, `FileUpdated`, `FileTrashed`, `FileDeleted`, `FileRestored`, `FileCopied`, and 14 more. Example: `All`. |
| `count` | query | integer (int32) | No | The maximum number of webhook log records to return in the query response. Example: `1234`. |
| `startIndex` | query | integer (int32) | No | Specifies the starting index for retrieving webhook logs. Used for pagination in the webhook delivery log queries. Example: `1234`. |

## Responses

### 200 — Logs of the webhook activities

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
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

### 401 — Unauthorized

