# MoveToNextReviewChange

Navigates through the review changes.

## Syntax

```javascript
expression.MoveToNextReviewChange(isForward);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/docspace-plugin-sdk/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| isForward | Optional | boolean | true | Specifies whether to navigate to the next (**true**) or previous (**false**) review change. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("MoveToNextReviewChange", [true]);
```
