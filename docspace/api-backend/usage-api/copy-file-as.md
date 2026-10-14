# Copy a file

`POST /api/2.0/files/file/{fileId}/copyas`

Copies (and converts if possible) an existing file to the specified folder.

Operation ID: `copyFileAs`

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
| `fileId` | path | integer (int32) | Yes | The file ID to copy. Example: `9846`. |

## Request body

The parameters for copying a file.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `destTitle` | string, nullable | Yes | The copied file name. Example: `some text`. |
| `destFolderId` | integer | Yes | The destination folder ID of the copied file. Example: `1234`. |
| `enableExternalExt` | boolean | No | Specifies whether to allow creating the copied file of an external extension or not. Example: `true`. |
| `password` | string, nullable | No | The copied file password. Example: `vfmf2vO1Kp`. |
| `toForm` | boolean | No | Specifies whether to convert the file to form or not. Example: `true`. |

Example:

```json
{
  "destTitle": "some text",
  "destFolderId": 1234,
  "enableExternalExt": true,
  "password": "vfmf2vO1Kp",
  "toForm": true
}
```

## Responses

### 200 — Copied file entry information

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The file entry information. |
| `response.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.sharedBy` | object | No | The user parameters. |
| `response.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.ownedBy` | object | No | The user parameters. |
| `response.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.created` | object | No | The API date and time parameters. |
| `response.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.createdBy` | object | No | The user parameters. |
| `response.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.updated` | object | No | The API date and time parameters. |
| `response.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.autoDelete` | object | No | The API date and time parameters. |
| `response.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.updatedBy` | object | No | The user parameters. |
| `response.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 400 — No file id or folder id toFolderId determine provider

### 401 — Unauthorized

### 403 — You don't have enough permission to create

### 404 — File not found

