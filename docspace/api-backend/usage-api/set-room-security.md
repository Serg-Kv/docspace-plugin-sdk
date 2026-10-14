# Set the room access rights

`PUT /api/2.0/files/rooms/{id}/share`

Sets the access rights to the room with the ID specified in the request.

Operation ID: `setRoomSecurity`

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

## Request body

The room invitation request.

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `invitations` | object[], nullable | No | The collection of invitation parameters. |
| `invitations.email` | string (email), nullable | No | The email address. Example: `Sydney_Roberts4@hotmail.com`. |
| `invitations.id` | string (uuid) | No | The ID of the user to share a room with. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `invitations.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `notify` | boolean | No | Specifies whether to notify users about the shared room or not. Example: `true`. |
| `message` | string, nullable | No | The message to send when notifying about the shared room. Example: `some text`. |
| `culture` | string, nullable | No | The language of the room invitation. Example: `some text`. |
| `force` | boolean | No | Specifies whether to forcibly delete a user with form roles from the room. Example: `true`. |

Example:

```json
{
  "invitations": [
    {}
  ],
  "notify": true,
  "message": "some text",
  "culture": "some text",
  "force": true
}
```

## Responses

### 200 — Room security information

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The room security parameters. |
| `response.members` | object[], nullable | No | The list of room members. |
| `response.members.access` | string | No | The access rights type. One of: `None`, `ReadWrite`, `Read`, `Restrict`, `Varies`, `Review`, `Comment`, `FillForms`, `CustomFilter`, `RoomManager`, `Editing`, `ContentCreator`. Example: `None`. |
| `response.members.sharedTo` | any, nullable | No | The user who has the access to the specified file. **Deprecated.** |
| `response.members.sharedToUser` | object | No | The full list of user parameters. |
| `response.members.sharedToUser.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.members.sharedToUser.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.members.sharedToUser.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.members.sharedToUser.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.members.sharedToUser.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.members.sharedToUser.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.members.sharedToUser.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.members.sharedToUser.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.members.sharedToUser.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.members.sharedToUser.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.members.sharedToUser.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.members.sharedToUser.firstName` | string, nullable | No | The user first name. Example: `Mike`. |
| `response.members.sharedToUser.lastName` | string, nullable | No | The user last name. Example: `Zanyatski`. |
| `response.members.sharedToUser.userName` | string, nullable | No | The user username. Example: `Mike.Zanyatski`. |
| `response.members.sharedToUser.email` | string (email), nullable | No | The user email. Example: `my@gmail.com`. |
| `response.members.sharedToUser.contacts` | object[], nullable | No | The list of user contacts. |
| `response.members.sharedToUser.contacts.type` | string, nullable | No | The contact type. Example: `GTalk`. |
| `response.members.sharedToUser.contacts.value` | string, nullable | No | The contact value. Example: `my@gmail.com`. |
| `response.members.sharedToUser.birthday` | object | No | The API date and time parameters. |
| `response.members.sharedToUser.birthday.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.members.sharedToUser.birthday.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.members.sharedToUser.sex` | string, nullable | No | The user sex. Example: `male`. |
| `response.members.sharedToUser.status` | string | No | The user status. One of: `Active`, `Terminated`, `Pending`, `Default`, `All`. Example: `Active`. |
| `response.members.sharedToUser.activationStatus` | string | No | The user activation status. One of: `NotActivated`, `Activated`, `Pending`, `AutoGenerated`. Example: `NotActivated`. |
| `response.members.sharedToUser.terminated` | object | No | The API date and time parameters. |
| `response.members.sharedToUser.terminated.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.members.sharedToUser.terminated.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.members.sharedToUser.department` | string, nullable | No | The user department. Example: `Marketing`. |
| `response.members.sharedToUser.workFrom` | object | No | The API date and time parameters. |
| `response.members.sharedToUser.workFrom.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.members.sharedToUser.workFrom.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.members.sharedToUser.groups` | object[], nullable | No | The list of user groups. |
| `response.members.sharedToUser.groups.id` | string (uuid) | Yes | The group ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.members.sharedToUser.groups.name` | string, nullable | Yes | The group name. Example: `Group Name`. |
| `response.members.sharedToUser.groups.manager` | string, nullable | No | The group manager. Example: `Jake.Zazhitski`. |
| `response.members.sharedToUser.groups.isSystem` | boolean, nullable | No | Indicates whether the group is a system group. Example: `true`. |
| `response.members.sharedToUser.location` | string, nullable | No | The user location. Example: `Palo Alto`. |
| `response.members.sharedToUser.notes` | string, nullable | No | The user notes. Example: `Notes to worker`. |
| `response.members.sharedToUser.isAdmin` | boolean | No | Specifies if the user is an administrator or not. Example: `false`. |
| `response.members.sharedToUser.isRoomAdmin` | boolean | No | Specifies if the user is a room administrator or not. Example: `true`. |
| `response.members.sharedToUser.isLDAP` | boolean | No | Specifies if the LDAP settings are enabled for the user or not. Example: `false`. |
| `response.members.sharedToUser.listAdminModules` | string[], nullable | No | The list of the administrator modules. Example: `["projects", "crm"]`. |
| `response.members.sharedToUser.isOwner` | boolean | No | Specifies if the user is a portal owner or not. Example: `true`. |
| `response.members.sharedToUser.isVisitor` | boolean | No | Specifies if the user is a portal visitor or not. Example: `true`. |
| `response.members.sharedToUser.isCollaborator` | boolean | No | Specifies if the user is a portal collaborator or not. Example: `true`. |
| `response.members.sharedToUser.cultureName` | string, nullable | No | The user culture code. Example: `en-EN`. |
| `response.members.sharedToUser.mobilePhone` | string, nullable | No | The user mobile phone number. Example: `some text`. |
| `response.members.sharedToUser.mobilePhoneActivationStatus` | string | No | The user mobile phone activation status. One of: `NotActivated`, `Activated`. Example: `NotActivated`. |
| `response.members.sharedToUser.isSSO` | boolean | No | Specifies if the SSO settings are enabled for the user or not. Example: `false`. |
| `response.members.sharedToUser.theme` | string | No | The theme type. One of: `Base`, `Dark`, `System`. Example: `Base`. |
| `response.members.sharedToUser.quotaLimit` | integer (int64), nullable | No | The user quota limit. Example: `1234`. |
| `response.members.sharedToUser.usedSpace` | number (double), nullable | No | The portal used space of the user. Example: `12345`. |
| `response.members.sharedToUser.shared` | boolean, nullable | No | Specifies if the user has access rights. Example: `true`. |
| `response.members.sharedToUser.isCustomQuota` | boolean, nullable | No | Specifies if the user has a custom quota or not. Example: `true`. |
| `response.members.sharedToUser.loginEventId` | integer (int32), nullable | No | The current login event ID. Example: `1234`. |
| `response.members.sharedToUser.authCookieLifetime` | number (double), nullable | No | The auth cookie lifetime in seconds. Example: `-8.5`. |
| `response.members.sharedToUser.createdBy` | object | No | The user parameters. |
| `response.members.sharedToUser.createdBy.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.members.sharedToUser.createdBy.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.members.sharedToUser.createdBy.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.members.sharedToUser.createdBy.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.members.sharedToUser.createdBy.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.members.sharedToUser.createdBy.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.members.sharedToUser.createdBy.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.members.sharedToUser.createdBy.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.members.sharedToUser.createdBy.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.members.sharedToUser.createdBy.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.members.sharedToUser.createdBy.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.members.sharedToUser.registrationDate` | object | No | The API date and time parameters. |
| `response.members.sharedToUser.registrationDate.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.members.sharedToUser.registrationDate.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.members.sharedToUser.hasPersonalFolder` | boolean | No | Specifies if the user has a personal folder or not. Example: `true`. |
| `response.members.sharedToUser.tfaAppEnabled` | boolean, nullable | No | Indicates whether the user has enabled two-factor authentication (TFA) using an authentication app. Example: `true`. |
| `response.members.sharedToGroup` | object | No | The group summary parameters. |
| `response.members.sharedToGroup.id` | string (uuid) | Yes | The group ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.members.sharedToGroup.name` | string, nullable | Yes | The group name. Example: `Group Name`. |
| `response.members.sharedToGroup.manager` | string, nullable | No | The group manager. Example: `Jake.Zazhitski`. |
| `response.members.sharedToGroup.isSystem` | boolean, nullable | No | Indicates whether the group is a system group. Example: `true`. |
| `response.members.sharedLink` | object | No | A shareable link for a file with its configuration and status. |
| `response.members.sharedLink.id` | string (uuid) | No | The unique identifier of the shared link. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.members.sharedLink.title` | string, nullable | No | The title of the shared content. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.members.sharedLink.shareLink` | string, nullable | No | The URL for accessing the shared content. Example: `some text`. |
| `response.members.sharedLink.expirationDate` | object | No | The API date and time parameters. |
| `response.members.sharedLink.expirationDate.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.members.sharedLink.expirationDate.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.members.sharedLink.linkType` | string | No | Defines the types of the sharing links. One of: `Invitation`, `External`. Example: `Invitation`. |
| `response.members.sharedLink.password` | string, nullable | No | The password protection for accessing the shared content. Example: `vfmf2vO1Kp`. |
| `response.members.sharedLink.denyDownload` | boolean, nullable | No | Indicates whether downloading of the shared content is prohibited. Example: `true`. |
| `response.members.sharedLink.isExpired` | boolean, nullable | No | Indicates whether the shared link has expired. Example: `true`. |
| `response.members.sharedLink.primary` | boolean | No | Indicates whether this is the primary shared link. Example: `true`. |
| `response.members.sharedLink.internal` | boolean, nullable | No | Indicates whether the link is for the internal sharing only. Example: `true`. |
| `response.members.sharedLink.requestToken` | string, nullable | No | The token for validating access requests. Example: `some text`. |
| `response.members.isLocked` | boolean | Yes | Specifies if the access right is locked or not. Example: `false`. |
| `response.members.isOwner` | boolean | Yes | Specifies if the user is an owner of the specified file or not. Example: `true`. |
| `response.members.canEditAccess` | boolean | Yes | Specifies if the user can edit the access to the specified file or not. Example: `true`. |
| `response.members.canEditInternal` | boolean | Yes | Indicates whether internal editing permissions are granted. Example: `true`. |
| `response.members.canEditDenyDownload` | boolean | Yes | Determines whether the user has permission to modify the deny download setting for the file share. Example: `true`. |
| `response.members.canEditExpirationDate` | boolean | Yes | Indicates whether the expiration date of access permissions can be edited. Example: `true`. |
| `response.members.canRevoke` | boolean | Yes | Specifies whether the file sharing access can be revoked by the current user. Example: `true`. |
| `response.members.subjectType` | string | Yes | The subject type of the access right. One of: `User`, `ExternalLink`, `Group`, `InvitationLink`, `PrimaryExternalLink`. Example: `User`. |
| `response.warning` | string, nullable | No | The warning message. Example: `some text`. |
| `response.error` | string | No | The error type. One of: `None`, `FormRoleBlockingDeletion`. Example: `None`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

