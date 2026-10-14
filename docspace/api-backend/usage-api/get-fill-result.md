# Get form-filling result

`GET /api/2.0/files/file/fillresult`

Retrieves the result of a form-filling session.

Operation ID: `getFillResult`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `fillingSessionId` | query | string | No | The form-filling session ID. Example: `some text`. |

## Responses

### 200 — Ok

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The parameters of the form filling result. |
| `response.formNumber` | integer (int32) | Yes | The filling form number. Example: `1234`. |
| `response.completedForm` | object | No | The file parameters. |
| `response.completedForm.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.completedForm.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.completedForm.sharedBy` | object | No | The user parameters. |
| `response.completedForm.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.completedForm.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.completedForm.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.completedForm.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.completedForm.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.completedForm.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.completedForm.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.completedForm.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.completedForm.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.completedForm.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.completedForm.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.completedForm.ownedBy` | object | No | The user parameters. |
| `response.completedForm.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.completedForm.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.completedForm.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.completedForm.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.completedForm.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.completedForm.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.completedForm.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.completedForm.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.completedForm.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.completedForm.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.completedForm.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.completedForm.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.completedForm.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.completedForm.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.completedForm.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.completedForm.created` | object | No | The API date and time parameters. |
| `response.completedForm.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.completedForm.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.completedForm.createdBy` | object | No | The user parameters. |
| `response.completedForm.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.completedForm.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.completedForm.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.completedForm.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.completedForm.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.completedForm.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.completedForm.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.completedForm.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.completedForm.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.completedForm.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.completedForm.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.completedForm.updated` | object | No | The API date and time parameters. |
| `response.completedForm.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.completedForm.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.completedForm.autoDelete` | object | No | The API date and time parameters. |
| `response.completedForm.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.completedForm.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.completedForm.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.completedForm.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.completedForm.updatedBy` | object | No | The user parameters. |
| `response.completedForm.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.completedForm.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.completedForm.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.completedForm.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.completedForm.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.completedForm.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.completedForm.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.completedForm.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.completedForm.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.completedForm.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.completedForm.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.completedForm.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.completedForm.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.completedForm.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.completedForm.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.completedForm.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.completedForm.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `response.completedForm.id` | integer (int32) | No | The file entry ID. Example: `10`. |
| `response.completedForm.rootFolderId` | integer (int32) | No | The root folder ID of the file entry. Example: `1234`. |
| `response.completedForm.originId` | integer (int32) | No | The origin ID of the file entry. Example: `1234`. |
| `response.completedForm.originRoomId` | integer (int32) | No | The origin room ID of the file entry. Example: `1234`. |
| `response.completedForm.originTitle` | string, nullable | No | The origin title of the file entry. Example: `some text`. |
| `response.completedForm.originRoomTitle` | string, nullable | No | The origin room title of the file entry. Example: `some text`. |
| `response.completedForm.canShare` | boolean | No | Specifies if the file entry can be shared or not. Example: `true`. |
| `response.completedForm.shareSettings` | object, nullable | No | A dictionary representing the sharing settings for the file entry. |
| `response.completedForm.shareSettings.User` | integer (int32) | No |  |
| `response.completedForm.shareSettings.ExternalLink` | integer (int32) | No |  |
| `response.completedForm.shareSettings.Group` | integer (int32) | No |  |
| `response.completedForm.shareSettings.InvitationLink` | integer (int32) | No |  |
| `response.completedForm.shareSettings.PrimaryExternalLink` | integer (int32) | No |  |
| `response.completedForm.security` | object, nullable | No | The actions that can be performed with the file entry. |
| `response.completedForm.security.Read` | boolean | No |  |
| `response.completedForm.security.Comment` | boolean | No |  |
| `response.completedForm.security.FillForms` | boolean | No |  |
| `response.completedForm.security.Review` | boolean | No |  |
| `response.completedForm.security.Create` | boolean | No |  |
| `response.completedForm.security.CreateFrom` | boolean | No |  |
| `response.completedForm.security.Edit` | boolean | No |  |
| `response.completedForm.security.Delete` | boolean | No |  |
| `response.completedForm.security.CustomFilter` | boolean | No |  |
| `response.completedForm.security.EditRoom` | boolean | No |  |
| `response.completedForm.security.Rename` | boolean | No |  |
| `response.completedForm.security.ReadHistory` | boolean | No |  |
| `response.completedForm.security.Lock` | boolean | No |  |
| `response.completedForm.security.EditHistory` | boolean | No |  |
| `response.completedForm.security.CopyTo` | boolean | No |  |
| `response.completedForm.security.Copy` | boolean | No |  |
| `response.completedForm.security.MoveTo` | boolean | No |  |
| `response.completedForm.security.Move` | boolean | No |  |
| `response.completedForm.security.Pin` | boolean | No |  |
| `response.completedForm.security.Mute` | boolean | No |  |
| `response.completedForm.security.EditAccess` | boolean | No |  |
| `response.completedForm.security.Duplicate` | boolean | No |  |
| `response.completedForm.security.SubmitToFormGallery` | boolean | No |  |
| `response.completedForm.security.Download` | boolean | No |  |
| `response.completedForm.security.Convert` | boolean | No |  |
| `response.completedForm.security.CopySharedLink` | boolean | No |  |
| `response.completedForm.security.ReadLinks` | boolean | No |  |
| `response.completedForm.security.Reconnect` | boolean | No |  |
| `response.completedForm.security.CreateRoomFrom` | boolean | No |  |
| `response.completedForm.security.CopyLink` | boolean | No |  |
| `response.completedForm.security.Embed` | boolean | No |  |
| `response.completedForm.security.ChangeOwner` | boolean | No |  |
| `response.completedForm.security.IndexExport` | boolean | No |  |
| `response.completedForm.security.StartFilling` | boolean | No |  |
| `response.completedForm.security.FillingStatus` | boolean | No |  |
| `response.completedForm.security.ResetFilling` | boolean | No |  |
| `response.completedForm.security.StopFilling` | boolean | No |  |
| `response.completedForm.security.OpenForm` | boolean | No |  |
| `response.completedForm.security.EditInternal` | boolean | No |  |
| `response.completedForm.security.EditExpiration` | boolean | No |  |
| `response.completedForm.security.Vectorization` | boolean | No |  |
| `response.completedForm.security.AskAi` | boolean | No |  |
| `response.completedForm.security.UseChat` | boolean | No |  |
| `response.completedForm.availableShareRights` | object, nullable | No | The available external rights of the file entry. |
| `response.completedForm.availableShareRights.User` | string[] | No |  |
| `response.completedForm.availableShareRights.ExternalLink` | string[] | No |  |
| `response.completedForm.availableShareRights.Group` | string[] | No |  |
| `response.completedForm.availableShareRights.InvitationLink` | string[] | No |  |
| `response.completedForm.availableShareRights.PrimaryExternalLink` | string[] | No |  |
| `response.completedForm.requestToken` | string, nullable | No | The request token of the file entry. Example: `some text`. |
| `response.completedForm.external` | boolean, nullable | No | Specifies if the folder can be accessed via an external link or not. Example: `true`. |
| `response.completedForm.expirationDate` | object | No | The API date and time parameters. |
| `response.completedForm.expirationDate.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.completedForm.expirationDate.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.completedForm.isLinkExpired` | boolean, nullable | No | Indicates whether the shareable link associated with the file or folder has expired. Example: `true`. |
| `response.completedForm.folderId` | integer (int32) | No | The folder ID where the file is located. Example: `9846`. |
| `response.completedForm.version` | integer (int32) | No | The file version. Example: `3`. |
| `response.completedForm.versionGroup` | integer (int32) | No | The version group of the file. Example: `1`. |
| `response.completedForm.contentLength` | string, nullable | No | The content length of the file. Example: `12345`. |
| `response.completedForm.pureContentLength` | integer (int64), nullable | No | The pure content length of the file. Example: `1234`. |
| `response.completedForm.fileStatus` | string | No | The file status. One of: `None`, `IsEditing`, `IsNew`, `IsConverting`, `IsOriginal`, `IsEditingAlone`, `IsFavorite`, `IsTemplate`, `IsFillFormDraft`, `IsCompletedForm`. Example: `None`. |
| `response.completedForm.mute` | boolean | No | Specifies if the file is muted or not. Example: `false`. |
| `response.completedForm.viewUrl` | string (uri), nullable | No | The URL link to view the file. Example: `https://www.onlyoffice.com/viewfile?fileid=2221`. |
| `response.completedForm.webUrl` | string (uri), nullable | No | The Web URL link to the file. Example: `some text`. |
| `response.completedForm.fileType` | string | No | The file type. One of: `Unknown`, `Archive`, `Video`, `Audio`, `Image`, `Spreadsheet`, `Presentation`, `Document`, `Pdf`, `Diagram`. Example: `Unknown`. |
| `response.completedForm.fileExst` | string, nullable | No | The file extension. Example: `.txt`. |
| `response.completedForm.comment` | string, nullable | No | The comment to the file. Example: `some text`. |
| `response.completedForm.encrypted` | boolean, nullable | No | Specifies if the file is encrypted or not. Example: `false`. |
| `response.completedForm.thumbnailUrl` | string (uri), nullable | No | The thumbnail URL of the file. Example: `some text`. |
| `response.completedForm.thumbnailStatus` | string | No | The file thumbnail status. One of: `Waiting`, `Created`, `Error`, `NotRequired`, `Creating`. Example: `Waiting`. |
| `response.completedForm.locked` | boolean, nullable | No | Specifies if the file is locked or not. Example: `true`. |
| `response.completedForm.lockedBy` | string, nullable | No | The user ID of the person who locked the file. Example: `some text`. |
| `response.completedForm.hasDraft` | boolean, nullable | No | Specifies if the file has a draft or not. Example: `false`. |
| `response.completedForm.formFillingStatus` | string | No | The form filling status. One of: `None`, `Draft`, `YouTurn`, `InProgress`, `Complete`, `Stoped`. Example: `None`. |
| `response.completedForm.isForm` | boolean, nullable | No | Specifies if the file is a form or not. Example: `false`. |
| `response.completedForm.customFilterEnabled` | boolean, nullable | No | Specifies if the Custom Filter editing mode is enabled for a file or not. Example: `true`. |
| `response.completedForm.customFilterEnabledBy` | string, nullable | No | The name of the user who enabled a Custom Filter editing mode for a file. Example: `some text`. |
| `response.completedForm.startFilling` | boolean, nullable | No | Specifies if the filling has started or not. Example: `false`. |
| `response.completedForm.inProcessFolderId` | integer (int32), nullable | No | The InProcess folder ID of the file. Example: `1234`. |
| `response.completedForm.inProcessFolderTitle` | string, nullable | No | The InProcess folder title of the file. Example: `some text`. |
| `response.completedForm.draftLocation` | object | No | The file draft parameters. |
| `response.completedForm.draftLocation.folderId` | integer (int32) | No | The InProcess folder ID of the draft. Example: `9846`. |
| `response.completedForm.draftLocation.folderTitle` | string, nullable | No | The InProcess folder title of the draft. Example: `some text`. |
| `response.completedForm.draftLocation.fileId` | integer (int32) | No | The draft ID. Example: `9846`. |
| `response.completedForm.draftLocation.fileTitle` | string, nullable | No | The draft title. Example: `some text`. |
| `response.completedForm.viewAccessibility` | object, nullable | No | The file accessibility. |
| `response.completedForm.viewAccessibility.ImageView` | boolean | No |  |
| `response.completedForm.viewAccessibility.MediaView` | boolean | No |  |
| `response.completedForm.viewAccessibility.WebView` | boolean | No |  |
| `response.completedForm.viewAccessibility.WebEdit` | boolean | No |  |
| `response.completedForm.viewAccessibility.WebReview` | boolean | No |  |
| `response.completedForm.viewAccessibility.WebCustomFilterEditing` | boolean | No |  |
| `response.completedForm.viewAccessibility.WebRestrictedEditing` | boolean | No |  |
| `response.completedForm.viewAccessibility.WebComment` | boolean | No |  |
| `response.completedForm.viewAccessibility.CanConvert` | boolean | No |  |
| `response.completedForm.viewAccessibility.MustConvert` | boolean | No |  |
| `response.completedForm.lastOpened` | object | No | The API date and time parameters. |
| `response.completedForm.lastOpened.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.completedForm.lastOpened.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.completedForm.expired` | object | No | The API date and time parameters. |
| `response.completedForm.expired.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.completedForm.expired.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.completedForm.vectorizationStatus` | string | No | [InProgress - In Progress, Completed - Completed, Failed - Failed] One of: `InProgress`, `Completed`, `Failed`. Example: `InProgress`. |
| `response.completedForm.dimensions` | object | No |  |
| `response.completedForm.dimensions.height` | integer (int32) | No |  |
| `response.completedForm.dimensions.width` | integer (int32) | No |  |
| `response.originalForm` | object | No | The file parameters. |
| `response.originalForm.title` | string, nullable | No | The file entry title. Example: `Some titile.txt/ Some title`. |
| `response.originalForm.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.originalForm.sharedBy` | object | No | The user parameters. |
| `response.originalForm.sharedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.originalForm.sharedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.originalForm.sharedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.originalForm.sharedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.originalForm.sharedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.originalForm.sharedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.originalForm.sharedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.originalForm.sharedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.originalForm.sharedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.originalForm.sharedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.originalForm.sharedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.originalForm.ownedBy` | object | No | The user parameters. |
| `response.originalForm.ownedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.originalForm.ownedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.originalForm.ownedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.originalForm.ownedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.originalForm.ownedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.originalForm.ownedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.originalForm.ownedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.originalForm.ownedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.originalForm.ownedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.originalForm.ownedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.originalForm.ownedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.originalForm.shared` | boolean | No | Specifies if the file entry is shared via link or not. Example: `false`. |
| `response.originalForm.sharedForUser` | boolean | No | Specifies if the file entry is shared for user or not. Example: `false`. |
| `response.originalForm.parentShared` | boolean | No | Indicates whether the parent entity is shared. Example: `true`. |
| `response.originalForm.shortWebUrl` | string (uri), nullable | No | The short Web URL. Example: `some text`. |
| `response.originalForm.created` | object | No | The API date and time parameters. |
| `response.originalForm.created.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.originalForm.created.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.originalForm.createdBy` | object | No | The user parameters. |
| `response.originalForm.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.originalForm.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.originalForm.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.originalForm.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.originalForm.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.originalForm.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.originalForm.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.originalForm.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.originalForm.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.originalForm.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.originalForm.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.originalForm.updated` | object | No | The API date and time parameters. |
| `response.originalForm.updated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.originalForm.updated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.originalForm.autoDelete` | object | No | The API date and time parameters. |
| `response.originalForm.autoDelete.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.originalForm.autoDelete.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.originalForm.rootFolderType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.originalForm.parentRoomType` | string | No | The folder type. One of: `DEFAULT`, `COMMON`, `BUNCH`, `TRASH`, `USER`, `SHARE`, `Projects`, `Favorites`, `Recent`, `Templates`, `Privacy`, `VirtualRooms`, `FillingFormsRoom`, `EditingRoom`, `CustomRoom`, and 13 more. Example: `DEFAULT`. |
| `response.originalForm.updatedBy` | object | No | The user parameters. |
| `response.originalForm.updatedBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.originalForm.updatedBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.originalForm.updatedBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.originalForm.updatedBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.originalForm.updatedBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.originalForm.updatedBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.originalForm.updatedBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.originalForm.updatedBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.originalForm.updatedBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.originalForm.updatedBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.originalForm.updatedBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.originalForm.providerItem` | boolean, nullable | No | Specifies if the file entry provider is specified or not. Example: `true`. |
| `response.originalForm.providerKey` | string, nullable | No | The provider key of the file entry. Example: `some text`. |
| `response.originalForm.providerId` | integer (int32), nullable | No | The provider ID of the file entry. Example: `1234`. |
| `response.originalForm.order` | string, nullable | No | The order of the file entry. Example: `some text`. |
| `response.originalForm.isFavorite` | boolean, nullable | No | Specifies if the file is a favorite or not. Example: `true`. |
| `response.originalForm.fileEntryType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `response.originalForm.id` | integer (int32) | No | The file entry ID. Example: `10`. |
| `response.originalForm.rootFolderId` | integer (int32) | No | The root folder ID of the file entry. Example: `1234`. |
| `response.originalForm.originId` | integer (int32) | No | The origin ID of the file entry. Example: `1234`. |
| `response.originalForm.originRoomId` | integer (int32) | No | The origin room ID of the file entry. Example: `1234`. |
| `response.originalForm.originTitle` | string, nullable | No | The origin title of the file entry. Example: `some text`. |
| `response.originalForm.originRoomTitle` | string, nullable | No | The origin room title of the file entry. Example: `some text`. |
| `response.originalForm.canShare` | boolean | No | Specifies if the file entry can be shared or not. Example: `true`. |
| `response.originalForm.shareSettings` | object, nullable | No | A dictionary representing the sharing settings for the file entry. |
| `response.originalForm.shareSettings.User` | integer (int32) | No |  |
| `response.originalForm.shareSettings.ExternalLink` | integer (int32) | No |  |
| `response.originalForm.shareSettings.Group` | integer (int32) | No |  |
| `response.originalForm.shareSettings.InvitationLink` | integer (int32) | No |  |
| `response.originalForm.shareSettings.PrimaryExternalLink` | integer (int32) | No |  |
| `response.originalForm.security` | object, nullable | No | The actions that can be performed with the file entry. |
| `response.originalForm.security.Read` | boolean | No |  |
| `response.originalForm.security.Comment` | boolean | No |  |
| `response.originalForm.security.FillForms` | boolean | No |  |
| `response.originalForm.security.Review` | boolean | No |  |
| `response.originalForm.security.Create` | boolean | No |  |
| `response.originalForm.security.CreateFrom` | boolean | No |  |
| `response.originalForm.security.Edit` | boolean | No |  |
| `response.originalForm.security.Delete` | boolean | No |  |
| `response.originalForm.security.CustomFilter` | boolean | No |  |
| `response.originalForm.security.EditRoom` | boolean | No |  |
| `response.originalForm.security.Rename` | boolean | No |  |
| `response.originalForm.security.ReadHistory` | boolean | No |  |
| `response.originalForm.security.Lock` | boolean | No |  |
| `response.originalForm.security.EditHistory` | boolean | No |  |
| `response.originalForm.security.CopyTo` | boolean | No |  |
| `response.originalForm.security.Copy` | boolean | No |  |
| `response.originalForm.security.MoveTo` | boolean | No |  |
| `response.originalForm.security.Move` | boolean | No |  |
| `response.originalForm.security.Pin` | boolean | No |  |
| `response.originalForm.security.Mute` | boolean | No |  |
| `response.originalForm.security.EditAccess` | boolean | No |  |
| `response.originalForm.security.Duplicate` | boolean | No |  |
| `response.originalForm.security.SubmitToFormGallery` | boolean | No |  |
| `response.originalForm.security.Download` | boolean | No |  |
| `response.originalForm.security.Convert` | boolean | No |  |
| `response.originalForm.security.CopySharedLink` | boolean | No |  |
| `response.originalForm.security.ReadLinks` | boolean | No |  |
| `response.originalForm.security.Reconnect` | boolean | No |  |
| `response.originalForm.security.CreateRoomFrom` | boolean | No |  |
| `response.originalForm.security.CopyLink` | boolean | No |  |
| `response.originalForm.security.Embed` | boolean | No |  |
| `response.originalForm.security.ChangeOwner` | boolean | No |  |
| `response.originalForm.security.IndexExport` | boolean | No |  |
| `response.originalForm.security.StartFilling` | boolean | No |  |
| `response.originalForm.security.FillingStatus` | boolean | No |  |
| `response.originalForm.security.ResetFilling` | boolean | No |  |
| `response.originalForm.security.StopFilling` | boolean | No |  |
| `response.originalForm.security.OpenForm` | boolean | No |  |
| `response.originalForm.security.EditInternal` | boolean | No |  |
| `response.originalForm.security.EditExpiration` | boolean | No |  |
| `response.originalForm.security.Vectorization` | boolean | No |  |
| `response.originalForm.security.AskAi` | boolean | No |  |
| `response.originalForm.security.UseChat` | boolean | No |  |
| `response.originalForm.availableShareRights` | object, nullable | No | The available external rights of the file entry. |
| `response.originalForm.availableShareRights.User` | string[] | No |  |
| `response.originalForm.availableShareRights.ExternalLink` | string[] | No |  |
| `response.originalForm.availableShareRights.Group` | string[] | No |  |
| `response.originalForm.availableShareRights.InvitationLink` | string[] | No |  |
| `response.originalForm.availableShareRights.PrimaryExternalLink` | string[] | No |  |
| `response.originalForm.requestToken` | string, nullable | No | The request token of the file entry. Example: `some text`. |
| `response.originalForm.external` | boolean, nullable | No | Specifies if the folder can be accessed via an external link or not. Example: `true`. |
| `response.originalForm.expirationDate` | object | No | The API date and time parameters. |
| `response.originalForm.expirationDate.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.originalForm.expirationDate.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.originalForm.isLinkExpired` | boolean, nullable | No | Indicates whether the shareable link associated with the file or folder has expired. Example: `true`. |
| `response.originalForm.folderId` | integer (int32) | No | The folder ID where the file is located. Example: `9846`. |
| `response.originalForm.version` | integer (int32) | No | The file version. Example: `3`. |
| `response.originalForm.versionGroup` | integer (int32) | No | The version group of the file. Example: `1`. |
| `response.originalForm.contentLength` | string, nullable | No | The content length of the file. Example: `12345`. |
| `response.originalForm.pureContentLength` | integer (int64), nullable | No | The pure content length of the file. Example: `1234`. |
| `response.originalForm.fileStatus` | string | No | The file status. One of: `None`, `IsEditing`, `IsNew`, `IsConverting`, `IsOriginal`, `IsEditingAlone`, `IsFavorite`, `IsTemplate`, `IsFillFormDraft`, `IsCompletedForm`. Example: `None`. |
| `response.originalForm.mute` | boolean | No | Specifies if the file is muted or not. Example: `false`. |
| `response.originalForm.viewUrl` | string (uri), nullable | No | The URL link to view the file. Example: `https://www.onlyoffice.com/viewfile?fileid=2221`. |
| `response.originalForm.webUrl` | string (uri), nullable | No | The Web URL link to the file. Example: `some text`. |
| `response.originalForm.fileType` | string | No | The file type. One of: `Unknown`, `Archive`, `Video`, `Audio`, `Image`, `Spreadsheet`, `Presentation`, `Document`, `Pdf`, `Diagram`. Example: `Unknown`. |
| `response.originalForm.fileExst` | string, nullable | No | The file extension. Example: `.txt`. |
| `response.originalForm.comment` | string, nullable | No | The comment to the file. Example: `some text`. |
| `response.originalForm.encrypted` | boolean, nullable | No | Specifies if the file is encrypted or not. Example: `false`. |
| `response.originalForm.thumbnailUrl` | string (uri), nullable | No | The thumbnail URL of the file. Example: `some text`. |
| `response.originalForm.thumbnailStatus` | string | No | The file thumbnail status. One of: `Waiting`, `Created`, `Error`, `NotRequired`, `Creating`. Example: `Waiting`. |
| `response.originalForm.locked` | boolean, nullable | No | Specifies if the file is locked or not. Example: `true`. |
| `response.originalForm.lockedBy` | string, nullable | No | The user ID of the person who locked the file. Example: `some text`. |
| `response.originalForm.hasDraft` | boolean, nullable | No | Specifies if the file has a draft or not. Example: `false`. |
| `response.originalForm.formFillingStatus` | string | No | The form filling status. One of: `None`, `Draft`, `YouTurn`, `InProgress`, `Complete`, `Stoped`. Example: `None`. |
| `response.originalForm.isForm` | boolean, nullable | No | Specifies if the file is a form or not. Example: `false`. |
| `response.originalForm.customFilterEnabled` | boolean, nullable | No | Specifies if the Custom Filter editing mode is enabled for a file or not. Example: `true`. |
| `response.originalForm.customFilterEnabledBy` | string, nullable | No | The name of the user who enabled a Custom Filter editing mode for a file. Example: `some text`. |
| `response.originalForm.startFilling` | boolean, nullable | No | Specifies if the filling has started or not. Example: `false`. |
| `response.originalForm.inProcessFolderId` | integer (int32), nullable | No | The InProcess folder ID of the file. Example: `1234`. |
| `response.originalForm.inProcessFolderTitle` | string, nullable | No | The InProcess folder title of the file. Example: `some text`. |
| `response.originalForm.draftLocation` | object | No | The file draft parameters. |
| `response.originalForm.draftLocation.folderId` | integer (int32) | No | The InProcess folder ID of the draft. Example: `9846`. |
| `response.originalForm.draftLocation.folderTitle` | string, nullable | No | The InProcess folder title of the draft. Example: `some text`. |
| `response.originalForm.draftLocation.fileId` | integer (int32) | No | The draft ID. Example: `9846`. |
| `response.originalForm.draftLocation.fileTitle` | string, nullable | No | The draft title. Example: `some text`. |
| `response.originalForm.viewAccessibility` | object, nullable | No | The file accessibility. |
| `response.originalForm.viewAccessibility.ImageView` | boolean | No |  |
| `response.originalForm.viewAccessibility.MediaView` | boolean | No |  |
| `response.originalForm.viewAccessibility.WebView` | boolean | No |  |
| `response.originalForm.viewAccessibility.WebEdit` | boolean | No |  |
| `response.originalForm.viewAccessibility.WebReview` | boolean | No |  |
| `response.originalForm.viewAccessibility.WebCustomFilterEditing` | boolean | No |  |
| `response.originalForm.viewAccessibility.WebRestrictedEditing` | boolean | No |  |
| `response.originalForm.viewAccessibility.WebComment` | boolean | No |  |
| `response.originalForm.viewAccessibility.CanConvert` | boolean | No |  |
| `response.originalForm.viewAccessibility.MustConvert` | boolean | No |  |
| `response.originalForm.lastOpened` | object | No | The API date and time parameters. |
| `response.originalForm.lastOpened.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.originalForm.lastOpened.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.originalForm.expired` | object | No | The API date and time parameters. |
| `response.originalForm.expired.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.originalForm.expired.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.originalForm.vectorizationStatus` | string | No | [InProgress - In Progress, Completed - Completed, Failed - Failed] One of: `InProgress`, `Completed`, `Failed`. Example: `InProgress`. |
| `response.originalForm.dimensions` | object | No |  |
| `response.originalForm.dimensions.height` | integer (int32) | No |  |
| `response.originalForm.dimensions.width` | integer (int32) | No |  |
| `response.manager` | object | No | The full list of user parameters. |
| `response.manager.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.manager.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.manager.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.manager.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.manager.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.manager.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.manager.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.manager.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.manager.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.manager.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.manager.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.manager.firstName` | string, nullable | No | The user first name. Example: `Mike`. |
| `response.manager.lastName` | string, nullable | No | The user last name. Example: `Zanyatski`. |
| `response.manager.userName` | string, nullable | No | The user username. Example: `Mike.Zanyatski`. |
| `response.manager.email` | string (email), nullable | No | The user email. Example: `my@gmail.com`. |
| `response.manager.contacts` | object[], nullable | No | The list of user contacts. |
| `response.manager.contacts.type` | string, nullable | No | The contact type. Example: `GTalk`. |
| `response.manager.contacts.value` | string, nullable | No | The contact value. Example: `my@gmail.com`. |
| `response.manager.birthday` | object | No | The API date and time parameters. |
| `response.manager.birthday.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.manager.birthday.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.manager.sex` | string, nullable | No | The user sex. Example: `male`. |
| `response.manager.status` | string | No | The user status. One of: `Active`, `Terminated`, `Pending`, `Default`, `All`. Example: `Active`. |
| `response.manager.activationStatus` | string | No | The user activation status. One of: `NotActivated`, `Activated`, `Pending`, `AutoGenerated`. Example: `NotActivated`. |
| `response.manager.terminated` | object | No | The API date and time parameters. |
| `response.manager.terminated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.manager.terminated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.manager.department` | string, nullable | No | The user department. Example: `Marketing`. |
| `response.manager.workFrom` | object | No | The API date and time parameters. |
| `response.manager.workFrom.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.manager.workFrom.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.manager.groups` | object[], nullable | No | The list of user groups. |
| `response.manager.groups.id` | string (uuid) | Yes | The group ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.manager.groups.name` | string, nullable | Yes | The group name. Example: `Group Name`. |
| `response.manager.groups.manager` | string, nullable | No | The group manager. Example: `Jake.Zazhitski`. |
| `response.manager.groups.isSystem` | boolean, nullable | No | Indicates whether the group is a system group. Example: `true`. |
| `response.manager.location` | string, nullable | No | The user location. Example: `Palo Alto`. |
| `response.manager.notes` | string, nullable | No | The user notes. Example: `Notes to worker`. |
| `response.manager.isAdmin` | boolean | No | Specifies if the user is an administrator or not. Example: `false`. |
| `response.manager.isRoomAdmin` | boolean | No | Specifies if the user is a room administrator or not. Example: `true`. |
| `response.manager.isLDAP` | boolean | No | Specifies if the LDAP settings are enabled for the user or not. Example: `false`. |
| `response.manager.listAdminModules` | string[], nullable | No | The list of the administrator modules. Example: `["projects", "crm"]`. |
| `response.manager.isOwner` | boolean | No | Specifies if the user is a portal owner or not. Example: `true`. |
| `response.manager.isVisitor` | boolean | No | Specifies if the user is a portal visitor or not. Example: `true`. |
| `response.manager.isCollaborator` | boolean | No | Specifies if the user is a portal collaborator or not. Example: `true`. |
| `response.manager.cultureName` | string, nullable | No | The user culture code. Example: `en-EN`. |
| `response.manager.mobilePhone` | string, nullable | No | The user mobile phone number. Example: `some text`. |
| `response.manager.mobilePhoneActivationStatus` | string | No | The user mobile phone activation status. One of: `NotActivated`, `Activated`. Example: `NotActivated`. |
| `response.manager.isSSO` | boolean | No | Specifies if the SSO settings are enabled for the user or not. Example: `false`. |
| `response.manager.theme` | string | No | The theme type. One of: `Base`, `Dark`, `System`. Example: `Base`. |
| `response.manager.quotaLimit` | integer (int64), nullable | No | The user quota limit. Example: `1234`. |
| `response.manager.usedSpace` | number (double), nullable | No | The portal used space of the user. Example: `12345`. |
| `response.manager.shared` | boolean, nullable | No | Specifies if the user has access rights. Example: `true`. |
| `response.manager.isCustomQuota` | boolean, nullable | No | Specifies if the user has a custom quota or not. Example: `true`. |
| `response.manager.loginEventId` | integer (int32), nullable | No | The current login event ID. Example: `1234`. |
| `response.manager.authCookieLifetime` | number (double), nullable | No | The auth cookie lifetime in seconds. Example: `-8.5`. |
| `response.manager.createdBy` | object | No | The user parameters. |
| `response.manager.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.manager.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.manager.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.manager.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.manager.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.manager.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.manager.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.manager.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.manager.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.manager.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.manager.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.manager.registrationDate` | object | No | The API date and time parameters. |
| `response.manager.registrationDate.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.manager.registrationDate.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.manager.hasPersonalFolder` | boolean | No | Specifies if the user has a personal folder or not. Example: `true`. |
| `response.manager.tfaAppEnabled` | boolean, nullable | No | Indicates whether the user has enabled two-factor authentication (TFA) using an authentication app. Example: `true`. |
| `response.roomId` | integer (int32) | Yes | The room ID where filling the form. Example: `9846`. |
| `response.isRoomMember` | boolean | No | Specifies if the manager who fills the form is a room member or not. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

