# Start the backup

`POST /api/2.0/backup/startbackup`

Starts the backup of the current portal with the parameters specified in the request.

Operation ID: `startBackup`

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
  "dump": true
}
```

## Responses

### 200 — Backup progress: completed or not, progress percentage, error, tenant ID, backup progress item (Backup, Restore, Transfer), link

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No |  |
| `response.isCompleted` | boolean | No | Example: `true`. |
| `response.progress` | integer (int32) | No | Example: `1234`. |
| `response.error` | string, nullable | No | Example: `some text`. |
| `response.warning` | string, nullable | No | Example: `some text`. |
| `response.link` | string, nullable | No | Example: `some text`. |
| `response.tenantId` | integer (int32) | No | Example: `1234`. |
| `response.backupProgressEnum` | string | No | [Backup - Backup, Restore - Restore, Transfer - Transfer] One of: `Backup`, `Restore`, `Transfer`. Example: `Backup`. |
| `response.taskId` | string, nullable | No | Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — Wrong folder type or backup can`t start as dump

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

### 403 — You don't have enough permission to create

### 404 — The required folder was not found

