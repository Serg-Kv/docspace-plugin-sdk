# Get file settings

`GET /api/2.0/files/settings`

Returns all the file settings.

Operation ID: `getFilesSettings`

## Responses

### 200 — File settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The file settings parameters. |
| `response.extsImagePreviewed` | string[], nullable | No | The list of extensions of the viewed images. |
| `response.extsMediaPreviewed` | string[], nullable | No | The list of extensions of the viewed media files. |
| `response.extsWebPreviewed` | string[], nullable | No | The list of extensions of the viewed files. |
| `response.extsWebEdited` | string[], nullable | No | The list of extensions of the edited files. |
| `response.extsWebEncrypt` | string[], nullable | No | The list of extensions of the encrypted files. |
| `response.extsWebReviewed` | string[], nullable | No | The list of extensions of the reviewed files. |
| `response.extsWebCustomFilterEditing` | string[], nullable | No | The list of extensions of the custom filter files. |
| `response.extsWebRestrictedEditing` | string[], nullable | No | The list of extensions of the files that are restricted for editing. |
| `response.extsWebCommented` | string[], nullable | No | The list of extensions of the commented files. |
| `response.extsWebTemplate` | string[], nullable | No | The list of extensions of the template files. |
| `response.extsMustConvert` | string[], nullable | No | The list of extensions of the files that must be converted. |
| `response.extsConvertible` | object, nullable | No | The list of the convertible extensions. |
| `response.extsUploadable` | string[], nullable | No | The list of the uploadable extensions. |
| `response.extsArchive` | string[], nullable | No | The list of extensions of the archive files. |
| `response.extsVideo` | string[], nullable | No | The list of the video extensions. |
| `response.extsAudio` | string[], nullable | No | The list of the audio extensions. |
| `response.extsImage` | string[], nullable | No | The list of the image extensions. |
| `response.extsSpreadsheet` | string[], nullable | No | The list of the spreadsheet extensions. |
| `response.extsPresentation` | string[], nullable | No | The list of the presentation extensions. |
| `response.extsDocument` | string[], nullable | No | The list of the text document extensions. |
| `response.extsDiagram` | string[], nullable | No | The list of the diagram extensions. |
| `response.internalFormats` | object, nullable | No | The internal file formats. |
| `response.internalFormats.Unknown` | string | No |  |
| `response.internalFormats.Archive` | string | No |  |
| `response.internalFormats.Video` | string | No |  |
| `response.internalFormats.Audio` | string | No |  |
| `response.internalFormats.Image` | string | No |  |
| `response.internalFormats.Spreadsheet` | string | No |  |
| `response.internalFormats.Presentation` | string | No |  |
| `response.internalFormats.Document` | string | No |  |
| `response.internalFormats.Pdf` | string | No |  |
| `response.internalFormats.Diagram` | string | No |  |
| `response.masterFormExtension` | string, nullable | No | The master form extension. Example: `some text`. |
| `response.paramVersion` | string, nullable | No | The URL parameter which specifies the file version. Example: `some text`. |
| `response.paramOutType` | string, nullable | No | The URL parameter which specifies the output type of the converted file. Example: `some text`. |
| `response.fileDownloadUrlString` | string (uri), nullable | No | The URL to download a file. Example: `some text`. |
| `response.fileWebViewerUrlString` | string, nullable | No | The URL to the file web viewer. Example: `some text`. |
| `response.fileWebViewerExternalUrlString` | string (uri), nullable | No | The external URL to the file web viewer. Example: `some text`. |
| `response.fileWebEditorUrlString` | string, nullable | No | The URL to the file web editor. Example: `some text`. |
| `response.fileWebEditorExternalUrlString` | string (uri), nullable | No | The external URL to the file web editor. Example: `some text`. |
| `response.fileRedirectPreviewUrlString` | string (uri), nullable | No | The redirect URL to the file viewer. Example: `some text`. |
| `response.fileThumbnailUrlString` | string (uri), nullable | No | The URL to the file thumbnail. Example: `some text`. |
| `response.confirmDelete` | boolean | No | Specifies whether to confirm the file deletion or not. Example: `true`. |
| `response.enableThirdParty` | boolean | No | Specifies whether to allow users to connect the third-party storages. Example: `true`. |
| `response.externalShare` | boolean | No | Specifies whether to enable sharing external links to the files. Example: `true`. |
| `response.externalShareSocialMedia` | boolean | No | Specifies whether to enable sharing files on social media. Example: `true`. |
| `response.storeOriginalFiles` | boolean | No | Specifies whether to enable storing original files. Example: `true`. |
| `response.keepNewFileName` | boolean | No | Specifies whether to keep the new file name. Example: `true`. |
| `response.displayFileExtension` | boolean | No | Specifies whether to display the file extension. Example: `true`. |
| `response.convertNotify` | boolean | No | Specifies whether to display the conversion notification. Example: `true`. |
| `response.hideConfirmCancelOperation` | boolean | No | Specifies whether to hide the confirmation dialog for the cancel operation. Example: `true`. |
| `response.hideConfirmConvertSave` | boolean | No | Specifies whether to hide the confirmation dialog for saving the file copy in the original format when converting a file. Example: `true`. |
| `response.hideConfirmConvertOpen` | boolean | No | Specifies whether to hide the confirmation dialog for opening the conversion result. Example: `true`. |
| `response.hideConfirmRoomLifetime` | boolean | No | Specifies whether to hide the confirmation dialog about the file lifetime in the room. Example: `true`. |
| `response.defaultOrder` | object | No | The sorting parameters. |
| `response.defaultOrder.is_asc` | boolean | No | Specifies if the order is ascending. Example: `true`. |
| `response.defaultOrder.property` | string | No | The parameters by which the files will be sorted. One of: `DateAndTime`, `AZ`, `Size`, `Author`, `Type`, `New`, `DateAndTimeCreation`, `RoomType`, `Tags`, `Room`, `CustomOrder`, `LastOpened`, `UsedSpace`. Example: `DateAndTime`. |
| `response.forcesave` | boolean | No | Specifies whether to forcesave the files or not. Example: `true`. |
| `response.storeForcesave` | boolean | No | Specifies whether to store the forcesaved file versions or not. Example: `true`. |
| `response.recentSection` | boolean | No | Specifies if the "Recent" section is displayed or not. Example: `true`. |
| `response.favoritesSection` | boolean | No | Specifies if the "Favorites" section is displayed or not. Example: `true`. |
| `response.templatesSection` | boolean | No | Specifies if the "Templates" section is displayed or not. Example: `true`. |
| `response.downloadTarGz` | boolean | No | Specifies whether to download the .tar.gz files or not. Example: `true`. |
| `response.automaticallyCleanUp` | object | No | The auto-clearing setting parameters. |
| `response.automaticallyCleanUp.isAutoCleanUp` | boolean | No | Specifies whether to permanently delete files in the Trash folder. Example: `true`. |
| `response.automaticallyCleanUp.gap` | string | No | The period when the trash bin will be cleared. One of: `OneWeek`, `TwoWeeks`, `OneMonth`, `ThirtyDays`, `TwoMonths`, `ThreeMonths`. Example: `OneWeek`. |
| `response.canSearchByContent` | boolean | No | Specifies whether the file can be searched by its content or not. Example: `true`. |
| `response.defaultSharingAccessRights` | string[], nullable | No | The default access rights in sharing settings. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. |
| `response.maxUploadThreadCount` | integer (int32) | No | The maximum number of upload threads. Example: `1234`. |
| `response.chunkUploadSize` | integer (int64) | No | The size of a large file that is uploaded in chunks. Example: `1234`. |
| `response.openEditorInSameTab` | boolean | No | Specifies whether to open the editor in the same tab or not. Example: `true`. |
| `response.extsFilesVectorized` | string[], nullable | No | List of extensions available for vectorization |
| `response.maxVectorizationFileSize` | integer (int64) | No | The maximum file size for vectorization Example: `1234`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

