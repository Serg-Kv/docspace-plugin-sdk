# IsFormSigned

Checks whether the specified form has been digitally signed.

## Syntax

```javascript
expression.IsFormSigned();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

boolean

## Example

```javascript
window.Asc.plugin.executeMethod ("IsFormSigned", [], function(isSigned) {
    console.log ("Form is signed: " + isSigned);
});
```
