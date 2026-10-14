# Create the backup schedule

`POST /api/2.0/backup/createbackupschedule`

Creates the backup schedule of the current portal with the parameters specified in the request.

Operation ID: `createBackupSchedule`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Request body

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `storageType` | string | No | [Documents - Documents, ThridpartyDocuments - Thridparty documents, CustomCloud - Custom cloud, Local - Local, DataStore - Data store, ThirdPartyConsumer - Thirdparty consumer] One of: `Documents`, `ThridpartyDocuments`, `CustomCloud`, `Local`, `DataStore`, `ThirdPartyConsumer`. Example: `Documents`. |
| `storageParams` | object[], nullable | No | The backup storage parameters. |
| `storageParams.key` | any, nullable | No |  |
| `storageParams.value` | any, nullable | No |  |
| `backupsStored` | integer (int32), nullable | No | The maximum number of the stored backup copies. Example: `1234`. |
| `cronParams` | object | No | The backup cron parameters. |
| `cronParams.period` | string | No | [EveryDay - Every day, EveryWeek - Every week, EveryMonth - Every month] One of: `EveryDay`, `EveryWeek`, `EveryMonth`. Example: `EveryDay`. |
| `cronParams.hour` | integer (int32) | No | The time of the day to start the backup process. Example: `0`. |
| `cronParams.day` | integer (int32), nullable | No | The day of the week to start the backup process. Example: `0`. |
| `dump` | boolean | No | Specifies if a dump will be created or not. Example: `true`. |

Example:

```json
{
  "storageType": "Documents",
  "storageParams": [
    {
      "key": {
        "int": 1234,
        "string": "some text",
        "boolean": true
      },
      "value": {
        "int": 1234,
        "string": "some text",
        "boolean": true
      }
    }
  ],
  "backupsStored": 1234,
  "cronParams": {
    "period": "EveryDay",
    "hour": 0,
    "day": 0
  },
  "dump": true
}
```

## Responses

### 200 — Boolean value: true if the operation is successful

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | boolean | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — BackupStored must be 1 - 30 or backup can not start as dump

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

### 403 — You don't have enough permission to create

### 404 — The required folder was not found

