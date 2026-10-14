# UpdatePlugin

Updates a plugin using the specified plugin config.

## Syntax

```javascript
expression.UpdatePlugin(config);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/interacting-with-editors/form-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| config | Optional | object |  | The plugin [config](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/configuration.md). |

## Returns

object

## Example

```javascript
window.Asc.plugin.executeMethod ("UpdatePlugin", [config], function (result) {
    postMessage (JSON.stringify (result));
});
```
