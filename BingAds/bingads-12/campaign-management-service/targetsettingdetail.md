---
title: TargetSettingDetail Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Determines whether you want to use the "target and bid" option or the "bid only" target option for the criterion type group.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# TargetSettingDetail Data Object - Campaign Management
Determines whether you want to use the "target and bid" option or the "bid only" target option for the criterion type group.

## Syntax
```xml
<xs:complexType name="TargetSettingDetail" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CriterionTypeGroup" type="tns:CriterionTypeGroup" />
    <xs:element minOccurs="0" name="TargetAll" type="xs:boolean" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="criteriontypegroup"></a>CriterionTypeGroup|The criterion type group that you want to set either the "target and bid" option or the "bid only" target option.<br/><br/>If the [Campaign Type](campaign.md#type) is set to Audience, the supported values are Age, Audience, CompanyName, Gender, Industry, and JobFunction. Otherwise the only value currently supported for other campaign types e.g., Search is Audience.|[CriterionTypeGroup](criteriontypegroup.md)|
|<a name="targetall"></a>TargetAll|Determines whether you want to use the "target and bid" option or the "bid only" target option for the criterion type group. A value of *True* corresponds to the "target and bid" option, and in this case we will only deliver ads to people who meet at least one of your criteria, while letting you make bid adjustments for specific criteria. A value of *False* corresponds to the "bid only" option, and in this case we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific criteria.<br/><br/>**Add:** Required<br/><br/>**Update:** Required|**boolean**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[TargetSetting](targetsetting.md)  
