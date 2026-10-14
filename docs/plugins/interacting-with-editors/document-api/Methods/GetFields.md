# GetFields

Returns all fields as a text.

## Syntax

```javascript
expression.GetFields();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

string[]

## Example

```javascript
window.Asc.plugin.executeMethod ("GetFields", null, function (res) {
    console.log ("First field: " + res[0])
});
```
