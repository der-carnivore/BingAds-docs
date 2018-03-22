---
title: "Bing Ads Scripts Changes and Text Logs"
description: "Describes how logging works in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Changes and Text Logs
Bing Ads Scripts provides two types of logs, changes and logger text output. Both are available for preview mode and for real executions.

## Changes Log
The Changes log lists all changes that a script makes to Bing Ads entities. Details include Changed Item, Type of change, Current value, New value, and Status. To view the Changes log click on "Changes" below the script editor text area.

## Text Log
Calling the `Logger.log` method will output text to the logger text log. This can be useful when debugging your scripts as well as for printing other information related to the script's activity. For example, the following code prints all campaign names and progress messages to the logger text log.

```javascript
var campaigns = BingAdsApp.campaigns().get();
Logger.log('retrieved ' + campaigns.totalNumEntities() + ' campaigns');
while(campaigns.hasNext()){
    Logger.log('getting next campaign');
    var campaign = campaigns.next();
    Logger.log('Campaign: ' + campaign.getName());
}
Logger.log('script complete');
```

In addition to output from `Logger.log` [errors and warning](./errors-and-warnings) will also be output to the logger text log. To view the logger text log click on "Logs" below the script editor text area.