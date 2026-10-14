# Get the number of backups

`GET /api/2.0/backup/getbackupscount`

Returns the number of backups for a period of time. The default is one month.

Operation ID: `getBackupsCount`

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
| `from` | query | string (date-time) | No | The from date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `to` | query | string (date-time) | No | The to date. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `paid` | query | boolean | No | Specifies if the backups are paid or not. Example: `true`. |

## Responses

### 200 — Number of backups

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | integer | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

