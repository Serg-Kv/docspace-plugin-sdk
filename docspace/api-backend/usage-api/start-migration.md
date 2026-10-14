# Start migration

`POST /api/2.0/migration/migrate`

Starts the migration process.

Operation ID: `startMigration`

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
| `migratorName` | string, nullable | No | Example: `some text`. |
| `operation` | string, nullable | No | Example: `some text`. |
| `failedArchives` | string[], nullable | No |  |
| `users` | object[], nullable | No |  |
| `users.shouldImport` | boolean | No | Example: `true`. |
| `users.key` | string, nullable | No | Example: `some text`. |
| `users.email` | string (email), nullable | No | Example: `Sydney_Roberts4@hotmail.com`. |
| `users.displayName` | string, nullable | No | Example: `some text`. |
| `users.firstName` | string, nullable | No | Example: `Winfield`. |
| `users.lastName` | string, nullable | No | Example: `Upton`. |
| `users.userType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `users.migratingFiles` | object | No |  |
| `users.migratingFiles.foldersCount` | integer (int32) | No | Example: `1234`. |
| `users.migratingFiles.filesCount` | integer (int32) | No | Example: `1234`. |
| `users.migratingFiles.bytesTotal` | integer (int64) | No | Example: `1234`. |
| `withoutEmailUsers` | object[], nullable | No |  |
| `withoutEmailUsers.shouldImport` | boolean | No | Example: `true`. |
| `withoutEmailUsers.key` | string, nullable | No | Example: `some text`. |
| `withoutEmailUsers.email` | string (email), nullable | No | Example: `Sydney_Roberts4@hotmail.com`. |
| `withoutEmailUsers.displayName` | string, nullable | No | Example: `some text`. |
| `withoutEmailUsers.firstName` | string, nullable | No | Example: `Winfield`. |
| `withoutEmailUsers.lastName` | string, nullable | No | Example: `Upton`. |
| `withoutEmailUsers.userType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `withoutEmailUsers.migratingFiles` | object | No |  |
| `withoutEmailUsers.migratingFiles.foldersCount` | integer (int32) | No | Example: `1234`. |
| `withoutEmailUsers.migratingFiles.filesCount` | integer (int32) | No | Example: `1234`. |
| `withoutEmailUsers.migratingFiles.bytesTotal` | integer (int64) | No | Example: `1234`. |
| `existUsers` | object[], nullable | No |  |
| `existUsers.shouldImport` | boolean | No | Example: `true`. |
| `existUsers.key` | string, nullable | No | Example: `some text`. |
| `existUsers.email` | string (email), nullable | No | Example: `Sydney_Roberts4@hotmail.com`. |
| `existUsers.displayName` | string, nullable | No | Example: `some text`. |
| `existUsers.firstName` | string, nullable | No | Example: `Winfield`. |
| `existUsers.lastName` | string, nullable | No | Example: `Upton`. |
| `existUsers.userType` | string | No | The user type. One of: `All`, `RoomAdmin`, `Guest`, `DocSpaceAdmin`, `User`. Example: `All`. |
| `existUsers.migratingFiles` | object | No |  |
| `existUsers.migratingFiles.foldersCount` | integer (int32) | No | Example: `1234`. |
| `existUsers.migratingFiles.filesCount` | integer (int32) | No | Example: `1234`. |
| `existUsers.migratingFiles.bytesTotal` | integer (int64) | No | Example: `1234`. |
| `groups` | object[], nullable | No |  |
| `groups.shouldImport` | boolean | No | Example: `true`. |
| `groups.groupName` | string, nullable | No | Example: `some text`. |
| `groups.moduleName` | string, nullable | No | Example: `some text`. |
| `groups.userUidList` | string[], nullable | No |  |
| `importPersonalFiles` | boolean | No | Example: `true`. |
| `importSharedFiles` | boolean | No | Example: `true`. |
| `importSharedFolders` | boolean | No | Example: `true`. |
| `importCommonFiles` | boolean | No | Example: `true`. |
| `importProjectFiles` | boolean | No | Example: `true`. |
| `importGroups` | boolean | No | Example: `true`. |
| `successedUsers` | integer (int32) | No | Example: `1234`. |
| `failedUsers` | integer (int32) | No | Example: `1234`. |
| `files` | string[], nullable | No |  |
| `errors` | string[], nullable | No |  |

Example:

```json
{
  "migratorName": "some text",
  "operation": "some text",
  "failedArchives": [
    "some text"
  ],
  "users": [
    {}
  ],
  "withoutEmailUsers": [
    {}
  ],
  "existUsers": [
    {}
  ],
  "groups": [
    {}
  ],
  "importPersonalFiles": true,
  "importSharedFiles": true,
  "importSharedFolders": true,
  "importCommonFiles": true,
  "importProjectFiles": true,
  "importGroups": true,
  "successedUsers": 1234,
  "failedUsers": 1234,
  "files": [
    "some text"
  ],
  "errors": [
    "some text"
  ]
}
```

## Responses

### 200 — Ok

### 401 — Unauthorized

### 403 — No permissions to perform this action

