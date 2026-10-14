# Get the portal settings

`GET /api/2.0/settings`

Returns a list of all the available portal settings with the current values for each parameter.

Operation ID: `getPortalSettings`

## Parameters

| Name | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| `withpassword` | query | boolean | No | Specifies whether to include the password hashing configuration in the response. Example: `true`. |

## Responses

### 200 — Settings

Content type: `application/json`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `response` | object | No | The settings information. |
| `response.timezone` | string, nullable | No | The time zone. Example: `UTC`. |
| `response.trustedDomains` | string[], nullable | No | The list of the trusted domains. Example: `mydomain.com`. |
| `response.trustedDomainsType` | string | No | The type of the tenant trusted domains. One of: `None`, `Custom`, `All`. Example: `None`. |
| `response.culture` | string, nullable | Yes | The language. Example: `en-US`. |
| `response.utcOffset` | string (date-span) | No | The UTC offset in the TimeSpan format. Example: `-8.5`. |
| `response.utcHoursOffset` | number (double) | No | The UTC offset in hours. Example: `-8.5`. |
| `response.greetingSettings` | string, nullable | No | The greeting settings. Example: `Web Office Applications`. |
| `response.ownerId` | string (uuid) | No | The owner ID. Example: `75a5f745-f697-4418-b38d-0fe0d277e258`. |
| `response.nameSchemaId` | string, nullable | No | The team template ID. Example: `some text`. |
| `response.enabledJoin` | boolean, nullable | No | Specifies if a user can join the portal or not. Example: `true`. |
| `response.enableAdmMess` | boolean, nullable | No | Specifies if a user can send a message to the administrator when accessing the DocSpace portal or not. Example: `true`. |
| `response.thirdpartyEnable` | boolean, nullable | No | Specifies if a user can connect third-party providers to the portal or not. Example: `true`. |
| `response.docSpace` | boolean | No | Specifies if this portal is a DocSpace portal or not. Example: `true`. |
| `response.standalone` | boolean | No | Indicates whether the system is running in standalone mode. Example: `true`. |
| `response.isAmi` | boolean | No | Specifies if this portal is the AMI instance or not. Example: `true`. |
| `response.baseDomain` | string, nullable | Yes | The base domain. Example: `some text`. |
| `response.wizardToken` | string, nullable | No | The wizard token. Example: `some text`. |
| `response.passwordHash` | object | No |  |
| `response.passwordHash.size` | integer (int32) | No | Example: `1234`. |
| `response.passwordHash.iterations` | integer (int32) | No | Example: `1234`. |
| `response.passwordHash.salt` | string, nullable | No | Example: `some text`. |
| `response.firebase` | object | No | The Firebase parameters. |
| `response.firebase.apiKey` | string, nullable | Yes | The Firebase API key. Example: `some text`. |
| `response.firebase.authDomain` | string, nullable | Yes | The Firebase authentication domain. Example: `some text`. |
| `response.firebase.projectId` | string, nullable | Yes | The Firebase project ID. Example: `some text`. |
| `response.firebase.storageBucket` | string, nullable | Yes | The Firebase storage bucket. Example: `some text`. |
| `response.firebase.messagingSenderId` | string, nullable | Yes | The Firebase messaging sender ID. Example: `some text`. |
| `response.firebase.appId` | string, nullable | Yes | The Firebase application ID. Example: `some text`. |
| `response.firebase.measurementId` | string, nullable | Yes | The Firebase measurement ID. Example: `some text`. |
| `response.firebase.databaseURL` | string, nullable | Yes | The Firebase database URL. Example: `some text`. |
| `response.version` | string, nullable | No | The portal version. Example: `some text`. |
| `response.recaptchaType` | string | No | The type of CAPTCHA validation used. One of: `Default`, `AndroidV2`, `iOSV2`, `hCaptcha`. Example: `Default`. |
| `response.recaptchaPublicKey` | string, nullable | No | The ReCAPTCHA public key. Example: `some text`. |
| `response.debugInfo` | boolean | No | Specifies if the debug information will be sent or not. Example: `true`. |
| `response.socketUrl` | string, nullable | No | The socket URL. Example: `some text`. |
| `response.tenantStatus` | string | No | The tenant status. One of: `Active`, `Suspended`, `RemovePending`, `Transfering`, `Restoring`, `Migrating`, `Encryption`. Example: `Active`. |
| `response.tenantAlias` | string, nullable | No | The tenant alias. Example: `some text`. |
| `response.displayAbout` | boolean | No | Specifies whether to display the "About" portal section. Example: `true`. |
| `response.domainValidator` | object | No | The domain validator. |
| `response.domainValidator.regex` | string, nullable | No | The regex string to validate a domain. Example: `some text`. |
| `response.domainValidator.minLength` | integer (int32) | No | The minimum length of the valid domain. Example: `1234`. |
| `response.domainValidator.maxLength` | integer (int32) | No | The maximum length of the valid domain. Example: `63`. |
| `response.zendeskKey` | string, nullable | No | The Zendesk key. Example: `some text`. |
| `response.tagManagerId` | string, nullable | No | The tag manager ID. Example: `some text`. |
| `response.cookieSettingsEnabled` | boolean | Yes | Specifies whether the cookie settings are enabled. Example: `true`. |
| `response.limitedAccessSpace` | boolean | No | Specifies whether the access to the space management is limited or not. Example: `true`. |
| `response.limitedAccessDevToolsForUsers` | boolean | No | Specifies whether the access to the Developer Tools is limited for users or not. Example: `true`. |
| `response.displayBanners` | boolean | No | Specifies whether to display the promotional banners. Example: `true`. |
| `response.userNameRegex` | string, nullable | No | The user name validation regex. Example: `some text`. |
| `response.invitationLimit` | integer (int32), nullable | No | The maximum number of invitations to the portal. Example: `1234`. |
| `response.plugins` | object | No | The plugins parameters. |
| `response.plugins.enabled` | boolean | No | Specifies if the plugins are enabled or not. Example: `true`. |
| `response.plugins.upload` | boolean | No | Specifies if the plugins can be uploaded or not. Example: `true`. |
| `response.plugins.delete` | boolean | No | Specifies if the plugins can be deleted or not. Example: `true`. |
| `response.deepLink` | object | Yes | The deep link parameters. |
| `response.deepLink.androidPackageName` | string, nullable | Yes | The Android package name. Example: `some text`. |
| `response.deepLink.url` | string, nullable | Yes | The deep link URL. Example: `some text`. |
| `response.deepLink.iosPackageId` | string, nullable | Yes | The deep link IOS package ID. Example: `some text`. |
| `response.formGallery` | object | No | The form gallery parameters. |
| `response.formGallery.path` | string, nullable | Yes | The form gallery path. Example: `some text`. |
| `response.formGallery.domain` | string, nullable | Yes | The form gallery domain. Example: `some text`. |
| `response.formGallery.ext` | string, nullable | Yes | The form gallery extension. Example: `.txt`. |
| `response.formGallery.uploadPath` | string, nullable | Yes | The form gallery upload path. Example: `some text`. |
| `response.formGallery.uploadDomain` | string, nullable | Yes | The form gallery upload domain. Example: `some text`. |
| `response.formGallery.uploadExt` | string, nullable | Yes | The form gallery upload extension. Example: `some text`. |
| `response.formGallery.uploadDashboard` | string, nullable | Yes | The form gallery upload dashboard. Example: `some text`. |
| `response.maxImageUploadSize` | integer (int64) | No | The maximum image upload size. Example: `1234`. |
| `response.logoText` | string, nullable | No | The white label logo text. Example: `some text`. |
| `response.externalResources` | object | No | The external resources settings. |
| `response.externalResources.api` | object | No | The external resource parameters. |
| `response.externalResources.api.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.api.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.common` | object | No | The external resource parameters. |
| `response.externalResources.common.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.common.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.forum` | object | No | The external resource parameters. |
| `response.externalResources.forum.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.forum.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.helpcenter` | object | No | The external resource parameters. |
| `response.externalResources.helpcenter.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.helpcenter.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.integrations` | object | No | The external resource parameters. |
| `response.externalResources.integrations.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.integrations.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.site` | object | No | The external resource parameters. |
| `response.externalResources.site.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.site.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.socialNetworks` | object | No | The external resource parameters. |
| `response.externalResources.socialNetworks.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.socialNetworks.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.support` | object | No | The external resource parameters. |
| `response.externalResources.support.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.support.entries` | object, nullable | No | The external resource entries. |
| `response.externalResources.videoguides` | object | No | The external resource parameters. |
| `response.externalResources.videoguides.domain` | string, nullable | No | The external resource domain. Example: `some text`. |
| `response.externalResources.videoguides.entries` | object, nullable | No | The external resource entries. |
| `count` | integer (int32) | No |  |
| `links` | object[] | No |  |
| `links.href` | string | No |  |
| `links.action` | string | No |  |
| `status` | integer (int32) | No |  |
| `statusCode` | integer (int32) | No |  |

