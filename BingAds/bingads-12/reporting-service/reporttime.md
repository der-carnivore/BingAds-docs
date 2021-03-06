---
title: ReportTime Data Object - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the date range values of a report request.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# ReportTime Data Object - Reporting
Defines the date range values of a report request.

## Syntax
```xml
<xs:complexType name="ReportTime" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CustomDateRangeEnd" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="CustomDateRangeStart" nillable="true" type="tns:Date" />
    <xs:element minOccurs="0" name="PredefinedTime" nillable="true" type="tns:ReportTimePeriod" />
    <xs:element minOccurs="0" name="ReportTimeZone" nillable="true" type="tns:ReportTimeZone" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customdaterangeend"></a>CustomDateRangeEnd|The end date of the custom date range. The end date cannot be later than today's date.|[Date](date.md)|
|<a name="customdaterangestart"></a>CustomDateRangeStart|The start date of the custom date range. The start date must be earlier than or the same as the end date.|[Date](date.md)|
|<a name="predefinedtime"></a>PredefinedTime|A predefined date range value. Each report request type specifies the predefined time periods that you can specify for each aggregation type.|[ReportTimePeriod](reporttimeperiod.md)|
|<a name="reporttimezone"></a>ReportTimeZone|Determines the time zone that you want the Reporting service to use for the selected date range.<br/><br/>The time zone helps you accurately scope data for the selected date range.<br/><br/>If you do not choose a time zone, the Reporting service uses PacificTimeUSCanadaTijuana by default. A report requested without a time zone specified at 2 AM EasternTimeUSCanada on 9/2/2017 for 'Yesterday' will be interpreted as a request for 8/31/2017. A report requested at the same time for 'Yesterday' with time zone set as EasternTimeUSCanada will be interpreted as a request for 9/1/2017.|[ReportTimeZone](reporttimezone.md)|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[AccountPerformanceReportRequest](accountperformancereportrequest.md)  
[AdDynamicTextPerformanceReportRequest](addynamictextperformancereportrequest.md)  
[AdExtensionByAdReportRequest](adextensionbyadreportrequest.md)  
[AdExtensionByKeywordReportRequest](adextensionbykeywordreportrequest.md)  
[AdExtensionDetailReportRequest](adextensiondetailreportrequest.md)  
[AdGroupPerformanceReportRequest](adgroupperformancereportrequest.md)  
[AdPerformanceReportRequest](adperformancereportrequest.md)  
[AgeGenderDemographicReportRequest](agegenderdemographicreportrequest.md)  
[AudiencePerformanceReportRequest](audienceperformancereportrequest.md)  
[CallDetailReportRequest](calldetailreportrequest.md)  
[CampaignPerformanceReportRequest](campaignperformancereportrequest.md)  
[ConversionPerformanceReportRequest](conversionperformancereportrequest.md)  
[DestinationUrlPerformanceReportRequest](destinationurlperformancereportrequest.md)  
[DSAAutoTargetPerformanceReportRequest](dsaautotargetperformancereportrequest.md)  
[DSACategoryPerformanceReportRequest](dsacategoryperformancereportrequest.md)  
[DSASearchQueryPerformanceReportRequest](dsasearchqueryperformancereportrequest.md)  
[GeographicPerformanceReportRequest](geographicperformancereportrequest.md)  
[GoalsAndFunnelsReportRequest](goalsandfunnelsreportrequest.md)  
[KeywordPerformanceReportRequest](keywordperformancereportrequest.md)  
[ProductDimensionPerformanceReportRequest](productdimensionperformancereportrequest.md)  
[ProductPartitionPerformanceReportRequest](productpartitionperformancereportrequest.md)  
[ProductPartitionUnitPerformanceReportRequest](productpartitionunitperformancereportrequest.md)  
[ProductSearchQueryPerformanceReportRequest](productsearchqueryperformancereportrequest.md)  
[PublisherUsagePerformanceReportRequest](publisherusageperformancereportrequest.md)  
[SearchCampaignChangeHistoryReportRequest](searchcampaignchangehistoryreportrequest.md)  
[SearchQueryPerformanceReportRequest](searchqueryperformancereportrequest.md)  
[ShareOfVoiceReportRequest](shareofvoicereportrequest.md)  
[UserLocationPerformanceReportRequest](userlocationperformancereportrequest.md)  
