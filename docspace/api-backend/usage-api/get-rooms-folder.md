# Get rooms

`GET /api/2.0/files/rooms`

Returns the contents of the "Rooms" section by the parameters specified in the request.

Operation ID: `getRoomsFolder`

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
| `type` | query | string[] | No | The filter by room type. One of: `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, `PublicRoom`, `VirtualDataRoom`, `AiRoom`. |
| `subjectId` | query | string | No | The filter by user ID. Example: `some text`. |
| `searchArea` | query | string | No | The room search area (Active, Archive, Any, Recent by links). One of: `Active`, `Archive`, `Any`, `RecentByLinks`, `Templates`, `Knowledge`, `ResultStorage`, `AiAgents`. Example: `Active`. |
| `withoutTags` | query | boolean | No | Specifies whether to search by tags or not. Example: `true`. |
| `tags` | query | string | No | The tags in the serialized format. Example: `some text`. |
| `excludeSubject` | query | boolean | No | Specifies whether to exclude search by user or group ID. Example: `true`. |
| `provider` | query | string | No | The filter by provider name (None, Box, DropBox, GoogleDrive, kDrive, OneDrive, SharePoint, WebDav, Yandex, Storage). One of: `None`, `Box`, `DropBox`, `GoogleDrive`, `kDrive`, `OneDrive`, `SharePoint`, `WebDav`, `Yandex`, `Storage`. Example: `None`. |
| `subjectFilter` | query | string | No | The filter by user (Owner - 0, Member - 1). One of: `Owner`, `Member`. Example: `Owner`. |
| `quotaFilter` | query | string | No | The filter by quota (All - 0, Default - 1, Custom - 2). One of: `All`, `Default`, `Custom`. Example: `All`. |
| `storageFilter` | query | string | No | The filter by storage (None - 0, Internal - 1, ThirdParty - 2). One of: `None`, `Internal`, `ThirdParty`. Example: `None`. |
| `count` | query | integer (int32) | No | Specifies the maximum number of items to retrieve. Example: `1234`. |
| `startIndex` | query | integer (int32) | No | The index from which to start retrieving the room content. Example: `1234`. |
| `sortBy` | query | string | No | Specifies the field by which the room content should be sorted. Example: `some text`. |
| `sortOrder` | query | string | No | The order in which the results are sorted. One of: `Ascending`, `Descending`. Example: `Ascending`. |
| `filterValue` | query | string | No | The text filter value used to refine search or query operations. Example: `some text`. |

## Responses

### 200 — Returns the contents of the "Rooms" section

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The folder content information. |
| `response.files` | object[], nullable | No | The list of files in the folder. |
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
| `response.folders` | object[], nullable | No | The list of folders in the folder. |
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
| `response.current` | object | No | The folder parameters. |
| `response.current.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.current.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.current.sharedBy` | object | No | The user parameters. |
| `response.current.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.current.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.current.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.current.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.current.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.current.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.current.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.current.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.current.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.current.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.current.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.current.ownedBy` | object | No | The user parameters. |
| `response.current.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.current.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.current.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.current.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.current.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.current.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.current.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.current.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.current.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.current.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.current.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.current.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.current.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.current.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.current.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.current.created` | object | No | The API date and time parameters. |
| `response.current.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.current.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.current.createdBy` | object | No | The user parameters. |
| `response.current.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.current.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.current.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.current.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.current.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.current.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.current.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.current.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.current.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.current.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.current.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.current.updated` | object | No | The API date and time parameters. |
| `response.current.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.current.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.current.autoDelete` | object | No | The API date and time parameters. |
| `response.current.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.current.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.current.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.current.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.current.updatedBy` | object | No | The user parameters. |
| `response.current.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.current.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.current.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.current.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.current.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.current.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.current.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.current.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.current.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.current.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.current.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.current.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.current.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.current.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.current.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.current.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.current.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `response.current.id` | integer (int32) | No | The file entry ID. Example: `10`. |
| `response.current.rootFolderId` | integer (int32) | No | The root folder ID of the file entry. Example: `1234`. |
| `response.current.originId` | integer (int32) | No | The origin ID of the file entry. Example: `1234`. |
| `response.current.originRoomId` | integer (int32) | No | The origin room ID of the file entry. Example: `1234`. |
| `response.current.originTitle` | string, nullable | No | The origin title of the file entry. Example: `some text`. |
| `response.current.originRoomTitle` | string, nullable | No | The origin room title of the file entry. Example: `some text`. |
| `response.current.canShare` | boolean | No | Specifies if the file entry can be shared or not. Example: `true`. |
| `response.current.shareSettings` | object, nullable | No | A dictionary representing the sharing settings for the file entry. |
| `response.current.shareSettings.User` | integer (int32) | No |  |
| `response.current.shareSettings.ExternalLink` | integer (int32) | No |  |
| `response.current.shareSettings.Group` | integer (int32) | No |  |
| `response.current.shareSettings.InvitationLink` | integer (int32) | No |  |
| `response.current.shareSettings.PrimaryExternalLink` | integer (int32) | No |  |
| `response.current.security` | object, nullable | No | The actions that can be performed with the file entry. |
| `response.current.security.Read` | boolean | No |  |
| `response.current.security.Comment` | boolean | No |  |
| `response.current.security.FillForms` | boolean | No |  |
| `response.current.security.Review` | boolean | No |  |
| `response.current.security.Create` | boolean | No |  |
| `response.current.security.CreateFrom` | boolean | No |  |
| `response.current.security.Edit` | boolean | No |  |
| `response.current.security.Delete` | boolean | No |  |
| `response.current.security.CustomFilter` | boolean | No |  |
| `response.current.security.EditRoom` | boolean | No |  |
| `response.current.security.Rename` | boolean | No |  |
| `response.current.security.ReadHistory` | boolean | No |  |
| `response.current.security.Lock` | boolean | No |  |
| `response.current.security.EditHistory` | boolean | No |  |
| `response.current.security.CopyTo` | boolean | No |  |
| `response.current.security.Copy` | boolean | No |  |
| `response.current.security.MoveTo` | boolean | No |  |
| `response.current.security.Move` | boolean | No |  |
| `response.current.security.Pin` | boolean | No |  |
| `response.current.security.Mute` | boolean | No |  |
| `response.current.security.EditAccess` | boolean | No |  |
| `response.current.security.Duplicate` | boolean | No |  |
| `response.current.security.SubmitToFormGallery` | boolean | No |  |
| `response.current.security.Download` | boolean | No |  |
| `response.current.security.Convert` | boolean | No |  |
| `response.current.security.CopySharedLink` | boolean | No |  |
| `response.current.security.ReadLinks` | boolean | No |  |
| `response.current.security.Reconnect` | boolean | No |  |
| `response.current.security.CreateRoomFrom` | boolean | No |  |
| `response.current.security.CopyLink` | boolean | No |  |
| `response.current.security.Embed` | boolean | No |  |
| `response.current.security.ChangeOwner` | boolean | No |  |
| `response.current.security.IndexExport` | boolean | No |  |
| `response.current.security.StartFilling` | boolean | No |  |
| `response.current.security.FillingStatus` | boolean | No |  |
| `response.current.security.ResetFilling` | boolean | No |  |
| `response.current.security.StopFilling` | boolean | No |  |
| `response.current.security.OpenForm` | boolean | No |  |
| `response.current.security.EditInternal` | boolean | No |  |
| `response.current.security.EditExpiration` | boolean | No |  |
| `response.current.security.Vectorization` | boolean | No |  |
| `response.current.security.AskAi` | boolean | No |  |
| `response.current.security.UseChat` | boolean | No |  |
| `response.current.availableShareRights` | object, nullable | No | The available external rights of the file entry. |
| `response.current.availableShareRights.User` | string[] | No |  |
| `response.current.availableShareRights.ExternalLink` | string[] | No |  |
| `response.current.availableShareRights.Group` | string[] | No |  |
| `response.current.availableShareRights.InvitationLink` | string[] | No |  |
| `response.current.availableShareRights.PrimaryExternalLink` | string[] | No |  |
| `response.current.requestToken` | string, nullable | No | The request token of the file entry. Example: `some text`. |
| `response.current.external` | boolean, nullable | No | Specifies if the folder can be accessed via an external link or not. Example: `true`. |
| `response.current.expirationDate` | object | No | The API date and time parameters. |
| `response.current.expirationDate.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.current.expirationDate.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.current.isLinkExpired` | boolean, nullable | No | Indicates whether the shareable link associated with the file or folder has expired. Example: `true`. |
| `response.current.parentId` | integer (int32) | No | The parent folder ID of the folder. Example: `10`. |
| `response.current.filesCount` | integer (int32) | No | The number of files that the folder contains. Example: `5`. |
| `response.current.foldersCount` | integer (int32) | No | The number of folders that the folder contains. Example: `7`. |
| `response.current.isShareable` | boolean, nullable | No | Specifies if the folder can be shared or not. Example: `true`. |
| `response.current.new` | integer (int32) | No | The new element index in the folder. Example: `1234`. |
| `response.current.mute` | boolean | No | Specifies if the folder notifications are enabled or not. Example: `true`. |
| `response.current.tags` | string[], nullable | No | The list of tags of the folder. |
| `response.current.logo` | object | No | The room logo information. |
| `response.current.logo.original` | string, nullable | Yes | The original logo. Example: `some text`. |
| `response.current.logo.large` | string, nullable | Yes | The large logo. Example: `some text`. |
| `response.current.logo.medium` | string, nullable | Yes | The medium logo. Example: `some text`. |
| `response.current.logo.small` | string, nullable | Yes | The small logo. Example: `some text`. |
| `response.current.logo.color` | string, nullable | No | The logo color. Example: `some text`. |
| `response.current.logo.cover` | object | No | The logo cover information. |
| `response.current.logo.cover.id` | string, nullable | Yes | The logo cover ID. Example: `9846`. |
| `response.current.logo.cover.data` | string, nullable | Yes | The logo cover data. Example: `some text`. |
| `response.current.pinned` | boolean | No | Specifies if the folder is pinned or not. Example: `true`. |
| `response.current.roomType` | string | No | The room type. One of: `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, `PublicRoom`, `VirtualDataRoom`, `AiRoom`. Example: `FillingFormsRoom`. |
| `response.current.private` | boolean | No | Specifies if the folder is private or not. Example: `true`. |
| `response.current.indexing` | boolean | No | Specifies if the folder is indexed or not. Example: `true`. |
| `response.current.denyDownload` | boolean | No | Specifies if the folder can be downloaded or not. Example: `true`. |
| `response.current.lifetime` | object | No | The room data lifetime information. |
| `response.current.lifetime.deletePermanently` | boolean | No | Specifies whether to permanently delete the room data or not. Example: `true`. |
| `response.current.lifetime.period` | string | No | The room data lifetime period. One of: `Day`, `Month`, `Year`. Example: `Day`. |
| `response.current.lifetime.value` | integer (int32), nullable | No | Specifies the time period value of the room data lifetime. Example: `1234`. |
| `response.current.lifetime.enabled` | boolean, nullable | No | Specifies whether the room data lifetime setting is enabled or not. Example: `true`. |
| `response.current.watermark` | object | No | The watermark settings. |
| `response.current.watermark.additions` | string | Yes | The watermark additions. One of: `UserName`, `UserEmail`, `UserIpAdress`, `CurrentDate`, `RoomName`. Example: `UserName`. |
| `response.current.watermark.text` | string, nullable | No | The watermark text. Example: `some text`. |
| `response.current.watermark.rotate` | integer (int32) | Yes | The watermark text and image rotate. Example: `1234`. |
| `response.current.watermark.imageScale` | integer (int32) | Yes | The watermark image scale. Example: `1234`. |
| `response.current.watermark.imageUrl` | string, nullable | No | The watermark image url. Example: `some text`. |
| `response.current.watermark.imageHeight` | number (double) | Yes | The watermark image height. Example: `-8.5`. |
| `response.current.watermark.imageWidth` | number (double) | Yes | The watermark image width. Example: `-8.5`. |
| `response.current.type` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.current.inRoom` | boolean, nullable | No | Specifies if the folder is placed in the room or not. Example: `true`. |
| `response.current.quotaLimit` | integer (int64), nullable | No | The folder quota limit. Example: `1234`. |
| `response.current.isCustomQuota` | boolean, nullable | No | Specifies if the folder room has a custom quota or not. Example: `true`. |
| `response.current.usedSpace` | integer (int64), nullable | No | How much folder space is used (counter). Example: `1234`. |
| `response.current.passwordProtected` | boolean, nullable | No | Specifies if the folder is password protected or not. Example: `true`. |
| `response.current.expired` | boolean, nullable | No | Specifies if an external link to the folder is expired or not. **Deprecated.** Example: `true`. |
| `response.current.chatSettings` | object | No |  |
| `response.current.chatSettings.providerId` | integer (int32) | No | Example: `1234`. |
| `response.current.chatSettings.modelId` | string, nullable | No | Example: `some text`. |
| `response.current.chatSettings.prompt` | string, nullable | No | Example: `some text`. |
| `response.current.rootRoomType` | string | No | The room type. One of: `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, `PublicRoom`, `VirtualDataRoom`, `AiRoom`. Example: `FillingFormsRoom`. |
| `response.pathParts` | any, nullable | Yes | The folder path. Example: `{key = "Key", path = "//path//to//folder"}`. |
| `response.startIndex` | integer (int32) | No | The folder start index. Example: `0`. |
| `response.count` | integer (int32) | No | The number of folder elements. Example: `4`. |
| `response.total` | integer (int32) | Yes | The total number of elements in the folder. Example: `4`. |
| `response.new` | integer (int32) | No | The new element index in the folder. Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — You don't have enough permission to view the room content

