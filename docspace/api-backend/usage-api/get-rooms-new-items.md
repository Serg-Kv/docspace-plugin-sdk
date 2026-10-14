# Get the room new items

`GET /api/2.0/files/rooms/news`

Returns the room new items.

Operation ID: `getRoomsNewItems`

## Authorization

One of:

- `asc_auth_key` (apiKey) — `asc_auth_key` in cookie
- `Bearer` (http bearer)
- `ApiKeyBearer` (apiKey) — `ApiKeyBearer` in header
- `Basic` (http basic)
- `OAuth2` (oauth2)
- `OpenId` (openIdConnect)

## Responses

### 200 — List of new items

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.date` | object | Yes | The API date and time parameters. |
| `response.date.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.date.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items` | object[], nullable | Yes | The list of items. |
| `response.items.room` | object | No | The file entry information. |
| `response.items.room.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.items.room.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.items.room.sharedBy` | object | No | The user parameters. |
| `response.items.room.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.room.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.room.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.room.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.room.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.room.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.room.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.room.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.room.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.room.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.room.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.room.ownedBy` | object | No | The user parameters. |
| `response.items.room.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.room.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.room.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.room.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.room.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.room.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.room.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.room.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.room.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.room.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.room.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.room.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.items.room.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.items.room.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.items.room.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.items.room.created` | object | No | The API date and time parameters. |
| `response.items.room.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.room.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.room.createdBy` | object | No | The user parameters. |
| `response.items.room.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.room.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.room.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.room.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.room.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.room.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.room.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.room.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.room.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.room.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.room.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.room.updated` | object | No | The API date and time parameters. |
| `response.items.room.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.room.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.room.autoDelete` | object | No | The API date and time parameters. |
| `response.items.room.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.room.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.room.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.items.room.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.items.room.updatedBy` | object | No | The user parameters. |
| `response.items.room.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.room.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.room.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.room.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.room.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.room.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.room.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.room.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.room.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.room.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.room.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.room.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.items.room.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.items.room.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.items.room.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.items.room.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.items.room.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `response.items.items` | object[], nullable | No | The list of file entry items. |
| `response.items.items.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.items.items.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.items.items.sharedBy` | object | No | The user parameters. |
| `response.items.items.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.items.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.items.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.items.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.items.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.items.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.items.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.items.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.items.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.items.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.items.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.items.ownedBy` | object | No | The user parameters. |
| `response.items.items.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.items.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.items.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.items.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.items.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.items.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.items.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.items.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.items.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.items.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.items.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.items.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.items.items.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.items.items.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.items.items.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.items.items.created` | object | No | The API date and time parameters. |
| `response.items.items.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.items.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.items.createdBy` | object | No | The user parameters. |
| `response.items.items.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.items.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.items.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.items.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.items.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.items.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.items.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.items.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.items.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.items.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.items.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.items.updated` | object | No | The API date and time parameters. |
| `response.items.items.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.items.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.items.autoDelete` | object | No | The API date and time parameters. |
| `response.items.items.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.items.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.items.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.items.items.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.items.items.updatedBy` | object | No | The user parameters. |
| `response.items.items.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.items.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.items.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.items.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.items.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.items.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.items.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.items.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.items.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.items.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.items.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.items.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.items.items.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.items.items.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.items.items.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.items.items.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.items.items.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

