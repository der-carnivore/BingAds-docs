# NegativeKeywordListOperation
Represents the definition of a keyword constructed via [NegativeKeywordListBuilder](./NegativeKeywordListBuilder). The negative keyword list is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. To make the script execute more efficiently, store the operation objects in an array and only invoke its methods when all operations have been constructed.
Example usage:
```javascript
 // For the purpose of this example, suppose that the fetchKeywords()
 // function fetches keyword data from your data source of choice, so that
 // keywordsToCreate is an array of strings, where each string is the text
 // for a keyword.
 var adGroup = BingAdsApp.adGroups().get().next();
 var keywordsToCreate = fetchKeywords();
 var keywordOps = [];
 for (var i = 0; i < keywordsToCreate.length; i++) {
   keywordOps.push(
       adGroup.newKeywordBuilder().withText(keywordsToCreate[i]).build());
 }
 for (var i = 0; i < keywordOps.length; i++) {
   if (keywordOps[i].isSuccessful()) {
     keywordOps[i].getResult().applyLabel('myLabel');
   } else {
     Logger.log('Errors from Keyword [' + keywordsToCreate[i] + ']: '
         + keywordOps[i].getErrors());
   }
 }
```

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|String[]|Returns an empty array if the keyword was successfully created, otherwise returns the errors encountered during the execution of this operation.<br />
[getResult](#getresult)|[NegativeKeywordList](./NegativeKeywordList)|Returns the newly created NegativeKeywordList, otherwise returns null if the operation failed.<br />
[isSuccessful](#issuccessful)|boolean|Returns <br />true if the operation was successful.

## <a name="geterrors"></a>getErrors
Returns an empty array if the keyword was successfully created, otherwise returns the errors encountered during the execution of this operation.

### Returns:
|Type|Description|
|-|-
String[]|The errors that occurred during the operation.

## <a name="getresult"></a>getResult
Returns the newly created NegativeKeywordList, otherwise returns null if the operation failed.

### Returns:
|Type|Description|
|-|-
[NegativeKeywordList](./NegativeKeywordList)|The NegativeKeywordList created by the NegativeKeywordListOperation.

## <a name="issuccessful"></a>isSuccessful
Returns 
true if the operation was successful.

### Returns:
|Type|Description|
|-|-
boolean|True if the operation was successful.
