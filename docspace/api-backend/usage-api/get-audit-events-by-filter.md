# Get filtered audit trail data

`GET /api/2.0/security/audit/events/filter`

Returns a list of the audit events by the parameters specified in the request.

Operation ID: `getAuditEventsByFilter`

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
| `userId` | query | string (uuid) | No | The ID of the user who triggered the audit event. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `moduleType` | query | string | No | The location where the audit event occurred. One of: `None`, `Files`, `Folders`, `DocumentsSettings`, `Rooms`, `Settings`, `Contacts`, `Agents`. Example: `None`. |
| `actionType` | query | string | No | The type of action performed in the audit event (e.g., Create, Update, Delete). One of: `None`, `Create`, `Update`, `Delete`, `Link`, `Unlink`, `Attach`, `Detach`, `Send`, `Import`, `Export`, `UpdateAccess`, `Download`, `Upload`, `Copy`, and 5 more. Example: `None`. |
| `action` | query | string | No | The specific action that occurred within the audit event. One of: `LoginSuccess`, `LoginSuccessViaSocialAccount`, `LoginFailInvalidCombination`, `LoginFailSocialAccountNotFound`, `LoginFailDisabledProfile`, `LoginFail`, `Logout`, `LoginSuccessViaSms`, `LoginFailViaSms`, `LoginFailIpSecurity`, `LoginSuccessViaApi`, `LoginSuccessViaSocialApp`, `LoginSuccessViaApiSms`, `LoginFailViaApi`, `LoginFailViaApiSms`, and 297 more. Example: `LoginSuccess`. |
| `entryType` | query | string | No | The type of audit entry (e.g., Folder, User, File). One of: `None`, `File`, `Folder`, `User`, `Group`, `Room`, `Tag`, `Agent`. Example: `None`. |
| `target` | query | string | No | The target object affected by the audit event (e.g., document ID, user account). Example: `some text`. |
| `from` | query | object | No | The starting date and time for filtering audit events. |
| `to` | query | object | No | The ending date and time for filtering audit events. |
| `count` | query | integer (int32) | No | The maximum number of audit event records to retrieve. Example: `1234`. |
| `startIndex` | query | integer (int32) | No | The index of the first audit event record to retrieve in a paged query. Example: `1234`. |

## Responses

### 200 — List of filtered audit trail data

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object[] | No |  |
| `response.id` | integer (int32) | No | The audit event ID. Example: `9846`. |
| `response.date` | object | No | The API date and time parameters. |
| `response.date.utcTime` | string (date-time) | No | The time in UTC format. Example: `2008-04-10T06:30:00.0000000+04:00`. |
| `response.date.timeZoneOffset` | string (date-span) | No | The time zone offset. Example: `00:00:00`. |
| `response.user` | string, nullable | No | The name of the user who triggered the audit event. Example: `some text`. |
| `response.userId` | string (uuid) | No | The ID of the user who triggered the audit event. Example: `aae1e103-bca5-9fa1-ba8c-42058b4abf28`. |
| `response.action` | string, nullable | No | The audit event action. Example: `some text`. |
| `response.actionId` | string | No | The event action ID. One of: `LoginSuccess`, `LoginSuccessViaSocialAccount`, `LoginFailInvalidCombination`, `LoginFailSocialAccountNotFound`, `LoginFailDisabledProfile`, `LoginFail`, `Logout`, `LoginSuccessViaSms`, `LoginFailViaSms`, `LoginFailIpSecurity`, `LoginSuccessViaApi`, `LoginSuccessViaSocialApp`, `LoginSuccessViaApiSms`, `LoginFailViaApi`, `LoginFailViaApiSms`, and 297 more. Example: `LoginSuccess`. |
| `response.ip` | string, nullable | No | The audit event IP. Example: `some text`. |
| `response.country` | string, nullable | No | The audit event country. Example: `some text`. |
| `response.city` | string, nullable | No | The audit event city. Example: `some text`. |
| `response.browser` | string, nullable | No | The audit event browser. Example: `some text`. |
| `response.platform` | string, nullable | No | The audit event platform. Example: `some text`. |
| `response.page` | string, nullable | No | The audit event page. Example: `some text`. |
| `response.actionType` | string | No | [None - None, Create - Create, Update - Update, Delete - Delete, Link - Link, Unlink - Unlink, Attach - Attach, Detach - Detach, Send - Send, Import - Import, Export - Export, UpdateAccess - Update access, Download - Download, Upload - Upload, Copy - Copy, Move - Move, Reassigns - Reassigns, Follow - Follow, Unfollow - Unfollow, Logout - Logout] One of: `None`, `Create`, `Update`, `Delete`, `Link`, `Unlink`, `Attach`, `Detach`, `Send`, `Import`, `Export`, `UpdateAccess`, `Download`, `Upload`, `Copy`, and 5 more. Example: `None`. |
| `response.product` | string | No | [Documents - Documents, Login - Login, Settings - Settings, Contacts - Contacts] One of: `Documents`, `Login`, `Settings`, `Contacts`. Example: `Documents`. |
| `response.location` | string | No | [None - None, Files - Files, Folders - Folders, DocumentsSettings - Documents settings, Rooms - Rooms, Settings - Settings, Contacts - Contacts, Agents - Agents] One of: `None`, `Files`, `Folders`, `DocumentsSettings`, `Rooms`, `Settings`, `Contacts`, `Agents`. Example: `None`. |
| `response.target` | string[], nullable | No | The list of target objects affected by the audit event (e.g., document ID, user account). |
| `response.entries` | string[], nullable | No | The list of audit entry types (e.g., Folder, User, File). One of: `None`, `File`, `Folder`, `User`, `Group`, `Room`, `Tag`, `Agent`. |
| `response.context` | string, nullable | No | The audit event context. Example: `some text`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

### 401 — Unauthorized

### 402 — Your pricing plan does not support this option

