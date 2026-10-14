# GetInstalledPlugins

Returns all the installed plugins.

## Syntax

```javascript
expression.GetInstalledPlugins();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/interacting-with-editors/form-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[PluginData](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/interacting-with-editors/form-api/Enumeration/PluginData.md)[]

## Example

```javascript
window.Asc.plugin.executeMethod ("GetInstalledPlugins", null, function (result) {
    postMessage (JSON.stringify ({type: 'InstalledPlugins', data: result }));
});
```
