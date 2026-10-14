# Get folder history

`GET /api/2.0/files/folder/{folderId}/log`

Returns the activity history of a folder with a specified identifier.

Operation ID: `getFolderHistory`

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
| `folderId` | path | integer (int32) | Yes | The folder ID of the history request. Example: `9846`. |
| `fromDate` | query | object | No | The start date of the history request. |
| `toDate` | query | object | No | The end date of the history request. |
| `count` | query | integer (int32) | No | The number of records to retrieve for the folder history. Example: `1234`. |
| `startIndex` | query | integer (int32) | No | The starting index from which the history records are retrieved in the request. Example: `1234`. |

## Responses

### 200 — List of actions in the folder

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | integer (int32) | Yes | The unique identifier for the file history entry. Example: `9846`. |
| `response.action` | object | Yes | The action performed on the file. |
| `response.action.id` | string | No | The event action ID. One of: `LoginSuccess`, `LoginSuccessViaSocialAccount`, `LoginFailInvalidCombination`, `LoginFailSocialAccountNotFound`, `LoginFailDisabledProfile`, `LoginFail`, `Logout`, `LoginSuccessViaSms`, `LoginFailViaSms`, `LoginFailIpSecurity`, `LoginSuccessViaApi`, `LoginSuccessViaSocialApp`, `LoginSuccessViaApiSms`, `LoginFailViaApi`, `LoginFailViaApiSms`, and 297 more. Example: `LoginSuccess`. |
| `response.action.key` | string, nullable | No | Example: `some text`. |
| `response.initiator` | object | Yes | The user parameters. |
| `response.initiator.id` | string (uuid) | No | The user ID. Example: `{00000000-0000-0000-0000-000000000000}`. |
| `response.initiator.displayName` | string, nullable | No | The user display name. Example: `Mike Zanyatski`. |
| `response.initiator.title` | string, nullable | No | The user title. Example: `Manager`. |
| `response.initiator.avatar` | string, nullable | No | The user avatar. Example: `some text`. |
| `response.initiator.avatarOriginal` | string, nullable | No | The user original size avatar. Example: `some text`. |
| `response.initiator.avatarMax` | string, nullable | No | The user maximum size avatar. Example: `some text`. |
| `response.initiator.avatarMedium` | string, nullable | No | The user medium size avatar. Example: `some text`. |
| `response.initiator.avatarSmall` | string, nullable | No | The user small size avatar. Example: `url to small avatar`. |
| `response.initiator.profileUrl` | string, nullable | No | The user profile URL. Example: `some text`. |
| `response.initiator.hasAvatar` | boolean | No | Specifies if the user has an avatar or not. Example: `true`. |
| `response.initiator.isAnonim` | boolean | No | Specifies if the user is anonymous or not. Example: `true`. |
| `response.date` | object | Yes | The API date and time parameters. |
| `response.date.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.date.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.data` | object | Yes | The history data. |
| `response.data.initiatorName` | string, nullable | No | The name of the action initiator. Example: `some text`. |
| `response.related` | object[], nullable | No | The list of related history. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 403 — You don't have enough permission to perform the operation

### 404 — The required folder was not found

