---
title: GetProfileDataFileUrl Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetProfileDataFileUrl Service Operation - Campaign Management
Reserved.

## <a name="request"></a>Request Elements
The *GetProfileDataFileUrlRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="languagelocale"></a>LanguageLocale|Reserved.|**string**|
|<a name="profiletype"></a>ProfileType|Reserved.|[ProfileType](profiletype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetProfileDataFileUrlResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="fileurl"></a>FileUrl|Reserved.|**string**|
|<a name="fileurlexpirytimeutc"></a>FileUrlExpiryTimeUtc|Reserved.|**dateTime**|
|<a name="lastmodifiedtimeutc"></a>LastModifiedTimeUtc|Reserved.|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetProfileDataFileUrl</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetProfileDataFileUrlRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <LanguageLocale i:nil="false">ValueHere</LanguageLocale>
      <ProfileType>ValueHere</ProfileType>
    </GetProfileDataFileUrlRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetProfileDataFileUrlResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <FileUrl d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</FileUrl>
      <FileUrlExpiryTimeUtc d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</FileUrlExpiryTimeUtc>
      <LastModifiedTimeUtc>ValueHere</LastModifiedTimeUtc>
    </GetProfileDataFileUrlResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetProfileDataFileUrlResponse> GetProfileDataFileUrlAsync(
	string languageLocale,
	ProfileType profileType)
{
	var request = new GetProfileDataFileUrlRequest
	{
		LanguageLocale = languageLocale,
		ProfileType = profileType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetProfileDataFileUrlAsync(r), request));
}
```
```java
static GetProfileDataFileUrlResponse getProfileDataFileUrl(
	java.lang.String languageLocale,
	ArrayList<ProfileType> profileType) throws RemoteException, Exception
{
	GetProfileDataFileUrlRequest request = new GetProfileDataFileUrlRequest();

	request.setLanguageLocale(languageLocale);
	request.setProfileType(profileType);

	return CampaignManagementService.getService().getProfileDataFileUrl(request);
}
```
```php
static function GetProfileDataFileUrl(
	$languageLocale,
	$profileType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetProfileDataFileUrlRequest();

	$request->LanguageLocale = $languageLocale;
	$request->ProfileType = $profileType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetProfileDataFileUrl($request);
}
```
```python
response=campaignmanagement_service.GetProfileDataFileUrl(
	LanguageLocale=LanguageLocale,
	ProfileType=ProfileType)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

