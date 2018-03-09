# ExecutionInfo
Provides information about the environment in which the current script is executing.

Example usage:
```javascript
var executionInfo = BingAdsApp.getExecutionInfo();
if(executionInfo.isPreview()) {
    Logger.log("script is running in preview mode.");
} else {
    SpreadsheetApp.create("report");
}
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[isPreview](#ispreview)|boolean|Returns a boolean value that determines if this script is executing in preview mode.

## <a name="ispreview"></a>isPreview
Returns a boolean value that determines if this script is executing in preview mode.
### Returns:
|Type|Description|
|-|-
boolean|Boolean value that determines if this script is executing in preview mode.

