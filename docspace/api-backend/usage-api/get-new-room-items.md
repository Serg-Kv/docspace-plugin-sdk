# Get the new room items

`GET /api/2.0/files/rooms/{id}/news`

Returns a list of all the new items from a room with the ID specified in the request.

Operation ID: `getNewRoomItems`

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
| `id` | path | integer (int32) | Yes | The room ID. Example: `9846`. |

## Responses

### 200 — List of file entry information

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.date` | object | Yes | The API date and time parameters. |
| `response.date.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.date.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items` | object[], nullable | Yes | The list of items. |
| `response.items.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.items.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.items.sharedBy` | object | No | The user parameters. |
| `response.items.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.ownedBy` | object | No | The user parameters. |
| `response.items.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.items.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.items.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.items.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.items.created` | object | No | The API date and time parameters. |
| `response.items.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.createdBy` | object | No | The user parameters. |
| `response.items.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.updated` | object | No | The API date and time parameters. |
| `response.items.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.autoDelete` | object | No | The API date and time parameters. |
| `response.items.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.items.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.items.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.items.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.items.updatedBy` | object | No | The user parameters. |
| `response.items.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.items.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.items.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.items.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.items.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.items.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.items.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.items.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.items.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.items.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.items.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.items.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.items.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.items.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.items.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.items.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.items.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

