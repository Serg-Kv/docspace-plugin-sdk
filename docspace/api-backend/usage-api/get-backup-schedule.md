# Get the backup schedule

`GET /api/2.0/backup/getbackupschedule`

Returns the backup schedule of the current portal.

Operation ID: `getBackupSchedule`

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

### 200 — Backup schedule

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No |  |
| `response.storageType` | string | Yes | [Documents - Documents, ThridpartyDocuments - Thridparty documents, CustomCloud - Custom cloud, Local - Local, DataStore - Data store, ThirdPartyConsumer - Thirdparty consumer] One of: `Documents`, `ThridpartyDocuments`, `CustomCloud`, `Local`, `DataStore`, `ThirdPartyConsumer`. Example: `Documents`. |
| `response.storageParams` | object, nullable | Yes |  |
| `response.cronParams` | object | Yes |  |
| `response.cronParams.period` | string | No | [EveryDay - Every day, EveryWeek - Every week, EveryMonth - Every month] One of: `EveryDay`, `EveryWeek`, `EveryMonth`. Example: `EveryDay`. |
| `response.cronParams.hour` | integer (int32) | No | Example: `1234`. |
| `response.cronParams.day` | integer (int32) | No | Example: `1234`. |
| `response.backupsStored` | integer (int32), nullable | No | Example: `1234`. |
| `response.lastBackupTime` | string (date-time) | Yes | Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.dump` | boolean | Yes | Example: `false`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

