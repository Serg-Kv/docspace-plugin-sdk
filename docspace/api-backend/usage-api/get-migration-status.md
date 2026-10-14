# Get migration status

`GET /api/2.0/migration/status`

Returns the migration status.

Operation ID: `getMigrationStatus`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — Ok

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The migration status parameters. |
| `response.progress` | number (double) | No | The migration progress. Example: `1`. |
| `response.error` | string, nullable | No | The migration error. Example: `some text`. |
| `response.parseResult` | object | No |  |
| `response.parseResult.migratorName` | string, nullable | No | Example: `some text`. |
| `response.parseResult.operation` | string, nullable | No | Example: `some text`. |
| `response.parseResult.failedArchives` | string[], nullable | No |  |
| `response.parseResult.users` | object[], nullable | No |  |
| `response.parseResult.users.shouldImport` | boolean | No | Example: `true`. |
| `response.parseResult.users.key` | string, nullable | No | Example: `some text`. |
| `response.parseResult.users.email` | string (email), nullable | No | Example: `Sydney_Roberts4@hotmail.com`. |
| `response.parseResult.users.displayName` | string, nullable | No | Example: `some text`. |
| `response.parseResult.users.firstName` | string, nullable | No | Example: `Winfield`. |
| `response.parseResult.users.lastName` | string, nullable | No | Example: `Upton`. |
| `response.parseResult.users.userType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `response.parseResult.users.migratingFiles` | object | No |  |
| `response.parseResult.users.migratingFiles.foldersCount` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.users.migratingFiles.filesCount` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.users.migratingFiles.bytesTotal` | integer (int64) | No | Example: `1234`. |
| `response.parseResult.withoutEmailUsers` | object[], nullable | No |  |
| `response.parseResult.withoutEmailUsers.shouldImport` | boolean | No | Example: `true`. |
| `response.parseResult.withoutEmailUsers.key` | string, nullable | No | Example: `some text`. |
| `response.parseResult.withoutEmailUsers.email` | string (email), nullable | No | Example: `Sydney_Roberts4@hotmail.com`. |
| `response.parseResult.withoutEmailUsers.displayName` | string, nullable | No | Example: `some text`. |
| `response.parseResult.withoutEmailUsers.firstName` | string, nullable | No | Example: `Winfield`. |
| `response.parseResult.withoutEmailUsers.lastName` | string, nullable | No | Example: `Upton`. |
| `response.parseResult.withoutEmailUsers.userType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `response.parseResult.withoutEmailUsers.migratingFiles` | object | No |  |
| `response.parseResult.withoutEmailUsers.migratingFiles.foldersCount` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.withoutEmailUsers.migratingFiles.filesCount` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.withoutEmailUsers.migratingFiles.bytesTotal` | integer (int64) | No | Example: `1234`. |
| `response.parseResult.existUsers` | object[], nullable | No |  |
| `response.parseResult.existUsers.shouldImport` | boolean | No | Example: `true`. |
| `response.parseResult.existUsers.key` | string, nullable | No | Example: `some text`. |
| `response.parseResult.existUsers.email` | string (email), nullable | No | Example: `Sydney_Roberts4@hotmail.com`. |
| `response.parseResult.existUsers.displayName` | string, nullable | No | Example: `some text`. |
| `response.parseResult.existUsers.firstName` | string, nullable | No | Example: `Winfield`. |
| `response.parseResult.existUsers.lastName` | string, nullable | No | Example: `Upton`. |
| `response.parseResult.existUsers.userType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `response.parseResult.existUsers.migratingFiles` | object | No |  |
| `response.parseResult.existUsers.migratingFiles.foldersCount` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.existUsers.migratingFiles.filesCount` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.existUsers.migratingFiles.bytesTotal` | integer (int64) | No | Example: `1234`. |
| `response.parseResult.groups` | object[], nullable | No |  |
| `response.parseResult.groups.shouldImport` | boolean | No | Example: `true`. |
| `response.parseResult.groups.groupName` | string, nullable | No | Example: `some text`. |
| `response.parseResult.groups.moduleName` | string, nullable | No | Example: `some text`. |
| `response.parseResult.groups.userUidList` | string[], nullable | No |  |
| `response.parseResult.importPersonalFiles` | boolean | No | Example: `true`. |
| `response.parseResult.importSharedFiles` | boolean | No | Example: `true`. |
| `response.parseResult.importSharedFolders` | boolean | No | Example: `true`. |
| `response.parseResult.importCommonFiles` | boolean | No | Example: `true`. |
| `response.parseResult.importProjectFiles` | boolean | No | Example: `true`. |
| `response.parseResult.importGroups` | boolean | No | Example: `true`. |
| `response.parseResult.successedUsers` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.failedUsers` | integer (int32) | No | Example: `1234`. |
| `response.parseResult.files` | string[], nullable | No |  |
| `response.parseResult.errors` | string[], nullable | No |  |
| `response.isCompleted` | boolean | No | Specifies whether the migration is completed or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — No permissions to perform this action

