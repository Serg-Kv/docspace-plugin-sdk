# Get the backup history

`GET /api/2.0/backup/getbackuphistory`

Returns the history of the started backup.

Operation ID: `getBackupHistory`

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
| `Dump` | query | boolean | No | Specifies if a dump will be created or not. Example: `true`. |

## Responses

### 200 — List of backup history records

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | string (uuid) | Yes | Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.fileName` | string, nullable | Yes | Example: `some text`. |
| `response.storageType` | string | Yes | [Documents - Documents, ThridpartyDocuments - Thridparty documents, CustomCloud - Custom cloud, Local - Local, DataStore - Data store, ThirdPartyConsumer - Thirdparty consumer] One of: `Documents`, `ThridpartyDocuments`, `CustomCloud`, `Local`, `DataStore`, `ThirdPartyConsumer`. Example: `Documents`. |
| `response.createdOn` | string (date-time) | Yes | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.expiresOn` | string (date-time) | Yes | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

