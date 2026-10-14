# GoToSlideInSlideShow

Displays the slide with the specific index.

## Syntax

```javascript
expression.GoToSlideInSlideShow(nSlideIndex);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/interacting-with-editors/presentation-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| nSlideIndex | Required | number |  | The slide index. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("GoToSlideInSlideShow", [2]);
```
