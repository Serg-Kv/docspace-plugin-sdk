# Change version history

`PUT /api/2.0/files/file/{fileId}/history`

Changes the version history of a file with the ID specified in the request.

Operation ID: `changeVersionHistory`

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
| `fileId` | path | integer (int32) | Yes | The file Id to change its version history. Example: `9846`. |

## Request body

The parameters for changing version history.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `version` | integer (int32) | Yes | The file version of the change history. Example: `1234`. |
| `continueVersion` | boolean | No | Specifies whether to start a new version or continue revision of the change history. Example: `true`. |

Example:

```json
{
  "version": 1234,
  "continueVersion": true
}
```

## Responses

### 200 — Updated information about file versions

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
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
| `response.id` | integer (int32) | No | The file entry ID. Example: `10`. |
| `response.rootFolderId` | integer (int32) | No | The root folder ID of the file entry. Example: `1234`. |
| `response.originId` | integer (int32) | No | The origin ID of the file entry. Example: `1234`. |
| `response.originRoomId` | integer (int32) | No | The origin room ID of the file entry. Example: `1234`. |
| `response.originTitle` | string, nullable | No | The origin title of the file entry. Example: `some text`. |
| `response.originRoomTitle` | string, nullable | No | The origin room title of the file entry. Example: `some text`. |
| `response.canShare` | boolean | No | Specifies if the file entry can be shared or not. Example: `true`. |
| `response.shareSettings` | object, nullable | No | A dictionary representing the sharing settings for the file entry. |
| `response.shareSettings.User` | integer (int32) | No |  |
| `response.shareSettings.ExternalLink` | integer (int32) | No |  |
| `response.shareSettings.Group` | integer (int32) | No |  |
| `response.shareSettings.InvitationLink` | integer (int32) | No |  |
| `response.shareSettings.PrimaryExternalLink` | integer (int32) | No |  |
| `response.security` | object, nullable | No | The actions that can be performed with the file entry. |
| `response.security.Read` | boolean | No |  |
| `response.security.Comment` | boolean | No |  |
| `response.security.FillForms` | boolean | No |  |
| `response.security.Review` | boolean | No |  |
| `response.security.Create` | boolean | No |  |
| `response.security.CreateFrom` | boolean | No |  |
| `response.security.Edit` | boolean | No |  |
| `response.security.Delete` | boolean | No |  |
| `response.security.CustomFilter` | boolean | No |  |
| `response.security.EditRoom` | boolean | No |  |
| `response.security.Rename` | boolean | No |  |
| `response.security.ReadHistory` | boolean | No |  |
| `response.security.Lock` | boolean | No |  |
| `response.security.EditHistory` | boolean | No |  |
| `response.security.CopyTo` | boolean | No |  |
| `response.security.Copy` | boolean | No |  |
| `response.security.MoveTo` | boolean | No |  |
| `response.security.Move` | boolean | No |  |
| `response.security.Pin` | boolean | No |  |
| `response.security.Mute` | boolean | No |  |
| `response.security.EditAccess` | boolean | No |  |
| `response.security.Duplicate` | boolean | No |  |
| `response.security.SubmitToFormGallery` | boolean | No |  |
| `response.security.Download` | boolean | No |  |
| `response.security.Convert` | boolean | No |  |
| `response.security.CopySharedLink` | boolean | No |  |
| `response.security.ReadLinks` | boolean | No |  |
| `response.security.Reconnect` | boolean | No |  |
| `response.security.CreateRoomFrom` | boolean | No |  |
| `response.security.CopyLink` | boolean | No |  |
| `response.security.Embed` | boolean | No |  |
| `response.security.ChangeOwner` | boolean | No |  |
| `response.security.IndexExport` | boolean | No |  |
| `response.security.StartFilling` | boolean | No |  |
| `response.security.FillingStatus` | boolean | No |  |
| `response.security.ResetFilling` | boolean | No |  |
| `response.security.StopFilling` | boolean | No |  |
| `response.security.OpenForm` | boolean | No |  |
| `response.security.EditInternal` | boolean | No |  |
| `response.security.EditExpiration` | boolean | No |  |
| `response.security.Vectorization` | boolean | No |  |
| `response.security.AskAi` | boolean | No |  |
| `response.security.UseChat` | boolean | No |  |
| `response.availableShareRights` | object, nullable | No | The available external rights of the file entry. |
| `response.availableShareRights.User` | string[] | No |  |
| `response.availableShareRights.ExternalLink` | string[] | No |  |
| `response.availableShareRights.Group` | string[] | No |  |
| `response.availableShareRights.InvitationLink` | string[] | No |  |
| `response.availableShareRights.PrimaryExternalLink` | string[] | No |  |
| `response.requestToken` | string, nullable | No | The request token of the file entry. Example: `some text`. |
| `response.external` | boolean, nullable | No | Specifies if the folder can be accessed via an external link or not. Example: `true`. |
| `response.expirationDate` | object | No | The API date and time parameters. |
| `response.expirationDate.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.expirationDate.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.isLinkExpired` | boolean, nullable | No | Indicates whether the shareable link associated with the file or folder has expired. Example: `true`. |
| `response.folderId` | integer (int32) | No | The folder ID where the file is located. Example: `9846`. |
| `response.version` | integer (int32) | No | The file version. Example: `3`. |
| `response.versionGroup` | integer (int32) | No | The version group of the file. Example: `1`. |
| `response.contentLength` | string, nullable | No | The content length of the file. Example: `12345`. |
| `response.pureContentLength` | integer (int64), nullable | No | The pure content length of the file. Example: `1234`. |
| `response.fileStatus` | string | No | The file status. One of: `None`, `IsEditing`, `IsNew`, `IsConverting`, `IsOriginal`, `IsEditingAlone`, `IsFavorite`, `IsTemplate`, `IsFillFormDraft`, `IsCompletedForm`. Example: `None`. |
| `response.mute` | boolean | No | Specifies if the file is muted or not. Example: `false`. |
| `response.viewUrl` | string (uri), nullable | No | The URL link to view the file. Example: `https://www.onlyoffice.com/viewfile?fileid=2221`. |
| `response.webUrl` | string (uri), nullable | No | The Web URL link to the file. Example: `some text`. |
| `response.fileType` | string | No | The file type. One of: `Unknown`, `Archive`, `Video`, `Audio`, `Image`, `Spreadsheet`, `Presentation`, `Document`, `Pdf`, `Diagram`. Example: `Unknown`. |
| `response.fileExst` | string, nullable | No | The file extension. Example: `.txt`. |
| `response.comment` | string, nullable | No | The comment to the file. Example: `some text`. |
| `response.encrypted` | boolean, nullable | No | Specifies if the file is encrypted or not. Example: `false`. |
| `response.thumbnailUrl` | string (uri), nullable | No | The thumbnail URL of the file. Example: `some text`. |
| `response.thumbnailStatus` | string | No | The file thumbnail status. One of: `Waiting`, `Created`, `Error`, `NotRequired`, `Creating`. Example: `Waiting`. |
| `response.locked` | boolean, nullable | No | Specifies if the file is locked or not. Example: `true`. |
| `response.lockedBy` | string, nullable | No | The user ID of the person who locked the file. Example: `some text`. |
| `response.hasDraft` | boolean, nullable | No | Specifies if the file has a draft or not. Example: `false`. |
| `response.formFillingStatus` | string | No | The form filling status. One of: `None`, `Draft`, `YouTurn`, `InProgress`, `Complete`, `Stoped`. Example: `None`. |
| `response.isForm` | boolean, nullable | No | Specifies if the file is a form or not. Example: `false`. |
| `response.customFilterEnabled` | boolean, nullable | No | Specifies if the Custom Filter editing mode is enabled for a file or not. Example: `true`. |
| `response.customFilterEnabledBy` | string, nullable | No | The name of the user who enabled a Custom Filter editing mode for a file. Example: `some text`. |
| `response.startFilling` | boolean, nullable | No | Specifies if the filling has started or not. Example: `false`. |
| `response.inProcessFolderId` | integer (int32), nullable | No | The InProcess folder ID of the file. Example: `1234`. |
| `response.inProcessFolderTitle` | string, nullable | No | The InProcess folder title of the file. Example: `some text`. |
| `response.draftLocation` | object | No | The file draft parameters. |
| `response.draftLocation.folderId` | integer (int32) | No | The InProcess folder ID of the draft. Example: `9846`. |
| `response.draftLocation.folderTitle` | string, nullable | No | The InProcess folder title of the draft. Example: `some text`. |
| `response.draftLocation.fileId` | integer (int32) | No | The draft ID. Example: `9846`. |
| `response.draftLocation.fileTitle` | string, nullable | No | The draft title. Example: `some text`. |
| `response.viewAccessibility` | object, nullable | No | The file accessibility. |
| `response.viewAccessibility.ImageView` | boolean | No |  |
| `response.viewAccessibility.MediaView` | boolean | No |  |
| `response.viewAccessibility.WebView` | boolean | No |  |
| `response.viewAccessibility.WebEdit` | boolean | No |  |
| `response.viewAccessibility.WebReview` | boolean | No |  |
| `response.viewAccessibility.WebCustomFilterEditing` | boolean | No |  |
| `response.viewAccessibility.WebRestrictedEditing` | boolean | No |  |
| `response.viewAccessibility.WebComment` | boolean | No |  |
| `response.viewAccessibility.CanConvert` | boolean | No |  |
| `response.viewAccessibility.MustConvert` | boolean | No |  |
| `response.lastOpened` | object | No | The API date and time parameters. |
| `response.lastOpened.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.lastOpened.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.expired` | object | No | The API date and time parameters. |
| `response.expired.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.expired.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.vectorizationStatus` | string | No | [InProgress - In Progress, Completed - Completed, Failed - Failed] One of: `InProgress`, `Completed`, `Failed`. Example: `InProgress`. |
| `response.dimensions` | object | No |  |
| `response.dimensions.height` | integer (int32) | No |  |
| `response.dimensions.width` | integer (int32) | No |  |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — You do not have enough permissions to edit the file

