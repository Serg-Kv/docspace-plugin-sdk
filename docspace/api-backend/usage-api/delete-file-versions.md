# Delete file versions

`PUT /api/2.0/files/fileops/deleteversion`

Deletes the file versions with the IDs specified in the request.

Operation ID: `deleteFileVersions`

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
| `returnSingleOperation` | boolean | No | Specifies whether to return only the current operation Example: `true`. |
| `deleteAfter` | boolean | No | Specifies whether to delete a file after the editing session is finished or not. Example: `true`. |
| `fileId` | integer (int32) | Yes | The file ID to delete. Example: `9846`. |
| `versions` | integer[] (int32), nullable | Yes | The collection of file versions to be deleted. |

Example:

```json
{}
```

## Responses

### 200 — List of file operations

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The file operation information. |
| `response.id` | string, nullable | Yes | The file operation ID. Example: `9846`. |
| `response.Operation` | string | Yes | The file operation type. One of: `Move`, `Copy`, `Delete`, `Download`, `MarkAsRead`, `Import`, `Convert`, `Duplicate`. Example: `Move`. |
| `response.progress` | integer (int32) | Yes | The file operation progress in percentage. Example: `100`. |
| `response.error` | string, nullable | Yes | The file operation error message. Example: ``. |
| `response.processed` | string, nullable | Yes | The file operation processing status. Example: `1`. |
| `response.finished` | boolean | Yes | Specifies if the file operation is finished or not. Example: `true`. |
| `response.url` | string (uri), nullable | No | The file operation URL. Example: `some text`. |
| `response.files` | object[], nullable | No | The list of files of the file operation. |
| `response.files.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.files.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.files.sharedBy` | object | No | The user parameters. |
| `response.files.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.files.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.files.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.files.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.files.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.files.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.files.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.files.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.files.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.files.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.files.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.files.ownedBy` | object | No | The user parameters. |
| `response.files.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.files.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.files.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.files.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.files.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.files.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.files.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.files.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.files.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.files.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.files.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.files.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.files.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.files.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.files.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.files.created` | object | No | The API date and time parameters. |
| `response.files.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.files.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.files.createdBy` | object | No | The user parameters. |
| `response.files.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.files.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.files.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.files.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.files.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.files.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.files.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.files.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.files.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.files.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.files.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.files.updated` | object | No | The API date and time parameters. |
| `response.files.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.files.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.files.autoDelete` | object | No | The API date and time parameters. |
| `response.files.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.files.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.files.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.files.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.files.updatedBy` | object | No | The user parameters. |
| `response.files.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.files.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.files.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.files.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.files.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.files.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.files.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.files.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.files.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.files.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.files.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.files.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.files.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.files.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.files.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.files.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.files.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `response.folders` | object[], nullable | No | The list of folders of the file operation. |
| `response.folders.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.folders.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.folders.sharedBy` | object | No | The user parameters. |
| `response.folders.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.folders.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.folders.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.folders.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.folders.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.folders.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.folders.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.folders.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.folders.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.folders.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.folders.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.folders.ownedBy` | object | No | The user parameters. |
| `response.folders.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.folders.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.folders.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.folders.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.folders.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.folders.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.folders.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.folders.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.folders.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.folders.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.folders.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.folders.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.folders.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.folders.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.folders.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.folders.created` | object | No | The API date and time parameters. |
| `response.folders.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.folders.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.folders.createdBy` | object | No | The user parameters. |
| `response.folders.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.folders.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.folders.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.folders.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.folders.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.folders.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.folders.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.folders.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.folders.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.folders.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.folders.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.folders.updated` | object | No | The API date and time parameters. |
| `response.folders.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.folders.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.folders.autoDelete` | object | No | The API date and time parameters. |
| `response.folders.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.folders.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.folders.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.folders.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.folders.updatedBy` | object | No | The user parameters. |
| `response.folders.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.folders.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.folders.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.folders.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.folders.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.folders.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.folders.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.folders.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.folders.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.folders.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.folders.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.folders.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.folders.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.folders.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.folders.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.folders.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.folders.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

