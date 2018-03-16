# AdSelector
Provides methods to select ads by using filtering and sorting.


Example usage:
```javascript
 var adSelector = BingAdsApp
     .ads()
     .withCondition("Impressions > 100")
     .forDateRange("LAST_MONTH")
     .orderBy("Clicks DESC");

 var adIterator = adSelector.get();
 while (adIterator.hasNext()) {
   var ad = adIterator.next();
 }
```

See also:
- [AdIterator](./AdIterator)
- [Ad](./Ad)


# Methods
|Method Name|Return Type|Description|
|-|-|-
[forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~)|[AdSelector](./AdSelector)|Returns a selector with the specified start and end dates.
[forDateRange(String dateRange)](#fordaterange~string-daterange~)|[AdSelector](./AdSelector)|Returns a selector using the specified predefined date range.
[get](#get)|[AdIterator](./AdIterator)|Returns an iterator indexing the ads in this selector.<br />
[orderBy(String orderBy)](#orderby~string-orderby~)|[AdSelector](./AdSelector)|Returns a selector with the specified ordering.
[withCondition(String condition)](#withcondition~string-condition~)|[AdSelector](./AdSelector)|Returns a selector with the specified filtering conditions.
[withIds(long[] ids)](#withids~long-ids~)|[AdSelector](./AdSelector)|Returns a selector that will return only ads with the specified IDs.
[withLimit(int limit)](#withlimit~int-limit~)|[AdSelector](./AdSelector)|Returns a selector that will return only the specified number of results from the beginning of the result set.

## <a name="fordaterange~object-datefrom_-object-dateto~"></a>forDateRange(Object dateFrom, Object dateTo)
Returns a selector with the specified start and end dates. You may specify the date parameters using strings or objects. To use strings, specify the date in the form, YYYYMMDD. If you use objects, create a JSON object with the following fields:  

- year
- month
- day

For example, {year: 2016, month: 5, day: 13}.

The date range is inclusive on both ends.

Date range must be specified if the selector has conditions or ordering for metrics statistics applied.  Only the last date range specified will be used.


### Arguments:
|Name|Type|Description|
|-|-|-
dateTo|Object|End date of the date range.
dateFrom|Object|Start date of the date range.
### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector with date range applied.

## <a name="fordaterange~string-daterange~"></a>forDateRange(String dateRange)
Returns a selector using the specified predefined date range. Supported date range values:

- TODAY
- YESTERDAY
- LAST_7_DAYS
- THIS_WEEK_SUN_TODAY
- LAST_14_DAYS
- LAST_30_DAYS
- LAST_WEEK_SUN_SAT
- THIS_MONTH
- LAST_MONTH
- ALL_TIME

Example:
```
selector.forDateRange("LAST_7_DAYS");
```

Date range must be specified if the selector has conditions or ordering for metrics statistics applied.  Only the last date range specified will be used.


### Arguments:
|Name|Type|Description|
|-|-|-
dateRange|String|Date range to set onto the selector.
### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector with date range applied.

## <a name="get"></a>get
Returns an iterator indexing the ads in this selector.


### Returns:
|Type|Description|
|-|-
[AdIterator](./AdIterator)|Iterator of the requested ads.

## <a name="orderby~string-orderby~"></a>orderBy(String orderBy)
Returns a selector with the specified ordering. Specify the orderBy parameter in the form, "columnName orderDirection" where:

- columnName can only be one column which is supported by the withCondition method.
- orderDirection is the direction to order the results in. Set to ASC to order the results in ascending order or DESC to order the results in descending order. The default is ASC.

You may order the results by one or more metrics by chaining together multiple orderBy calls. For example, the following call returns results in ascending order by MaxCpc.

<code>agSelector = agSelector.orderBy("MaxCpc");</code>


### Arguments:
|Name|Type|Description|
|-|-|-
orderBy|String|Ordering to apply.
### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector with ordering applied.

## <a name="withcondition~string-condition~"></a>withCondition(String condition)
Returns a selector with the specified filtering conditions. Specify the condition parameter in the form, "columnName operator value" where: 

- columnName is the name of a performance metric to order the results by. For a list of possible values, see [Supported Columns](#supported-ad-columns).  If you set columName to a performance metric column name, you must also specify a date range using [forDateRange(String dateRange)](#fordaterange~string-daterange~) or [forDateRange(Object dateFrom, Object dateTo)](#fordaterange~object-datefrom_-object-dateto~).
- operator is one of the supported [operators](#operators).

### Operators
The operator that can be used in a condition depends on the type of column. 
For Integer and Long columns: 

```
<  <=  >  >=  =  !=
```
For Double columns: 
```
<  >
```
For String columns: 
```
=  !=  STARTS_WITH  STARTS_WITH_IGNORE_CASE  CONTAINS
 CONTAINS_IGNORE_CASE  DOES_NOT_CONTAIN  DOES_NOT_CONTAIN_IGNORE_CASE
```
For Enumeration columns: 
```
=  !=  IN []  NOT_IN []
```

Operators are case-sensitive: `starts_with` won't work. 

<a name="supported-ad-columns"></a>
### Supported Columns
Supported columns for ad filtering. 

|Column|Type|Example|Bing Web UI filter|
|-|-|-|-
<strong>Stats</strong>|
AverageCpc|double|`withCondition("AverageCpc < 1.45")`|Avg. CPC
AverageCpm|double|`withCondition("AverageCpm > 0.48")`|Avg. CPM
AveragePageviews|double|`withCondition("AveragePageviews > 0")`|
AveragePosition|double|`withCondition("AveragePosition > 7.5")`|Avg. pos.
BounceRate|double|`withCondition("BounceRate < 0.5")`|
ClickConversionRate|double|`withCondition("ClickConversionRate > 0.1")`|Conv. Rate
Clicks|long|`withCondition("Clicks >= 21")`|Clicks
ConvertedClicks|long|`withCondition("ConvertedClicks <= 4")`|Conv.
Cost|double|`withCondition("Cost > 4.48"). The value is in the currency of the account.`|Spend
Ctr|double|`withCondition("Ctr > 0.01"). Ctr is returned in 0..1 range, so 5% Ctr is represented as 0.05.`|CTR
Impressions|long|`withCondition("Impressions != 0")`|Impr.
&nbsp;|&nbsp;|&nbsp;|&nbsp;
<strong>Ad attributes</strong>|
Status|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`DISABLED`|`withCondition("Status = PAUSED")`|Status
ApprovalStatus|Enumeration:<br />&nbsp;`APPROVED`<br />&nbsp;`DISAPPROVED`<br />&nbsp;`UNCHECKED`|`withCondition("ApprovalStatus NOT_IN [DISAPPROVED, UNCHECKED]")`|Delivery
Type|Enumeration:<br />&nbsp;`EXPANDED_TEXT_AD`<br />&nbsp;`MOBILE_AD`<br />&nbsp;`TEXT_AD`|`withCondition("Type NOT_IN [IMAGE_AD, RICH_MEDIA_AD]")`|Ad type
Headline|String|`withCondition("Headline CONTAINS_IGNORE_CASE 'leather shoes'")`|Ad title
Description1|String|`withCondition("Description1 STARTS_WITH 'Leather'")`|Ad text
Description2|String|`withCondition("Description2 = 'Hurry to buy'")`|
DisplayUrl|String|`withCondition("DisplayUrl STARTS_WITH 'www.example.com'")`|Display URL
DestinationUrl|String|`withCondition("DestinationUrl STARTS_WITH 'http://www.example.com'")`|Destination URL
CreativeFinalUrls|String|`withCondition("CreativeFinalUrls CONTAINS 'http://www.example.com'")`|
AdGroupName|String|`withCondition("AdGroupName CONTAINS_IGNORE_CASE 'shoes'")`|Ad group name
AdGroupStatus|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`REMOVED`|`withCondition("AdGroupStatus = ENABLED"). Use to fetch ads from only ENABLED ad groups.`|
CampaignName|String|`withCondition("CampaignName CONTAINS_IGNORE_CASE 'promotion'")	Campaign name`|
CampaignStatus|Enumeration:<br />&nbsp;`ENABLED`<br />&nbsp;`PAUSED`<br />&nbsp;`REMOVED`|`withCondition("CampaignStatus = ENABLED"). Use to fetch ads from only ENABLED campaigns.`|
DevicePreferenceType|Enumeration:<br />&nbsp;`MOBILE`<br />&nbsp;`ALL`|`withCondition("DevicePreferenceType = MOBILE"). Use to fetch only mobile-preferred ads.`|Device preference
&nbsp;|&nbsp;|&nbsp;|&nbsp;

### Arguments:
|Name|Type|Description|
|-|-|-
condition|String|Condition to add to the selector.
### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector with the condition applied.

## <a name="withids~long-ids~"></a>withIds(long[] ids)
Returns a selector that will return only ads with the specified IDs. 
The resulting selector can be further filtered by applying additional conditions to it.  All conditions will be 'AND' concatenated including any other ID based conditions.  For example:

```javascript
BingAdsApp.campaigns()
    .withIds([11111, 22222, 33333])
    .withIds([33333, 44444, 55555])
```

will only get the campaign with ID 33333 because it would be the only one satisfying both conditions.

The maximum number of IDs that you may specify is 1,000. If you specify more than 1,000 IDs, calling the get method will fail.

### Arguments:
|Name|Type|Description|
|-|-|-
ids|long[][]|Array of ad IDs.
### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector restricted to the given IDs.

## <a name="withlimit~int-limit~"></a>withLimit(int limit)
Returns a selector that will return only the specified number of results from the beginning of the result set.

### Arguments:
|Name|Type|Description|
|-|-|-
limit|int|How many entities to return.
### Returns:
|Type|Description|
|-|-
[AdSelector](./AdSelector)|The selector with limit applied.
