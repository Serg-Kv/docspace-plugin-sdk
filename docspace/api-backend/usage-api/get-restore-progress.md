# Get the restoring progress

`GET /api/2.0/backup/getrestoreprogress`

Returns the progress of the started restoring process.

Operation ID: `getRestoreProgress`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `Dump` | query | boolean | No | Specifies if a dump will be created or not. Example: `true`. |

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

