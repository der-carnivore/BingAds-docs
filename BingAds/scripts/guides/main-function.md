---
title: "Bing Ads Scripts Script Structure"
description: "Describes how scripts should be structured in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Main Function

Unlike JavaScript that executes in a browser, in Bing Ads Scripts you must define a `main()` function to contain the program logic you wish to execute. You may also define custom functions but the main function is the entry point into code execution.  For example, the following code defines a main function which calls a custom function named getAllCampaigns.

```javascript
function main() {
    getAllCampaigns();
}

function getAllCampaigns() {
  var campaigns = BingAdsApp.campaigns().get();
    while(campaigns.hasNext()){
        var campaign = campaigns.next();
        Logger.log(`Campaign: ${campaign.getName()}`);
    }
}
```

