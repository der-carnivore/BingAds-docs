---
title: "Bing Ads Scripts Preview Mode"
description: "Describes how preview mode works in the Bing Ads Scripts system."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Preview Mode

Scripts executed in preview mode don't make changes to actual campaign data. Instead, you'll be shown changes that would be made if the script is executed. When you're satisfied with the script's output, you can run the script or schedule it to run later.

Preview mode is specific to Bing Ads components. Calls to other services will execute as normal. Spreadsheet updates will be made whether the script is executed in preview mode or not. To determine if a script is executing in preview mode, see [ExecutionInfo](../reference/ExecutionInfo).