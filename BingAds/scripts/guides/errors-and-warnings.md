---
title: "Bing Ads Scripts Errors and Warnings"
description: "Describes how errors and warnings are handled in Bing Ads Scripts."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Errors and Warnings

Scripts in Bing Ads Scripts attempt to make changes to Bing Ads data, if certain operations fail, messages are logged to the [Changes Log](./changes-and-text-logs#changes-log) and execution continues. For example, the following code attempts to set a campaign's budget amount to an invalid value.

```javascript
function main() {
    var campaign = BingAdsApp.campaigns().get().next();
    campaign.getBudget().setAmount(-5);
    
    if (campaign.getBudget() != -5) {
        // The budget amount doesn't match what we attempted to set it to, so the change must have failed.
    }
}
```

Other errors, such as runtime errors or entity retrieval failures will cause script execution to stop. When this happens the error message is output to the [Text Log](./changes-and-text-logs#text-log). For example, the following code attempts to call a function that does not exist.

```javascript
function main() {
    doSomething(); // ReferenceError: 'doSomething' is undefined
}
```

You should carefully review all messages logged to the [Changes and Text logs](./changes-and-text-logs).