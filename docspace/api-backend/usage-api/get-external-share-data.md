# Get the external data

`GET /api/2.0/files/share/{key}`

Returns the external data by the key specified in the request.

Operation ID: `getExternalShareData`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `key` | path | string | Yes | The unique key of the external shared data. Example: `some text`. |
| `fileId` | query | string | No | The unique document identifier. Example: `9846`. |
| `folderId` | query | string | No | The unique folder identifier. Example: `9846`. |

## Responses

### 200 — External data

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The external sharing information and validation data. |
| `response.status` | string | Yes | The external data status. One of: `Ok`, `Invalid`, `Expired`, `RequiredPassword`, `InvalidPassword`, `ExternalAccessDenied`. Example: `Ok`. |
| `response.id` | string, nullable | Yes | The external data ID. Example: `9846`. |
| `response.title` | string, nullable | Yes | The external data title. Example: `legacy_1080p_small_wooden_mouse`. |
| `response.type` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `response.tenantId` | integer (int32) | Yes | The tenant ID. Example: `1234`. |
| `response.entityId` | string, nullable | No | The unique identifier of the shared entity. Example: `some text`. |
| `response.entityTitle` | string, nullable | No | The title of the shared entity. Example: `some text`. |
| `response.entityType` | string | No | The file entry type. One of: `Folder`, `File`. Example: `Folder`. |
| `response.isRoom` | boolean, nullable | No | Indicates whether the entity represents a room. Example: `true`. |
| `response.shared` | boolean | Yes | Specifies whether to share the external data or not. Example: `true`. |
| `response.linkId` | string (uuid) | Yes | The link ID of the external data. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `response.isAuthenticated` | boolean | Yes | Specifies whether the user is authenticated or not. Example: `true`. |
| `response.isRoomMember` | boolean | No | The room ID of the external data. Example: `true`. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

