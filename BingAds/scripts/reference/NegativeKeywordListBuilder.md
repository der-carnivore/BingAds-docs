# NegativeKeywordListBuilder
Provides methods which are used to define and build a negative keyword list. For more information about Builders, see [Builders](../concepts/builders).

Example usage:
```javascript
 var negativeKeywordListBuilder = BingAdsApp.newNegativeKeywordListBuilder()
         .withName("NegativeKeywordList");

 var negativeKeywordListOperation = negativeKeywordListBuilder.build();

 var negativeKeywordList = negativeKeywordListOperation.getResult();
```

It is only necessary to call [NegativeKeywordListOperation.getResult](./NegativeKeywordListOperation#getresult) if you need to access the actual negative keyword list. Calling the build method on the negative keyword list builder is enough to create the negative keyword list.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[build](#build)|[NegativeKeywordListOperation](./NegativeKeywordListOperation)|Returns an operation object with the defined properties which can later be used to construct the keyword.
[withName(String name)](#withname~string-name~)|[NegativeKeywordListBuilder](./NegativeKeywordListBuilder)|Returns a negative keyword list builder with the name set to the specified value.

## <a name="build"></a>build
Returns an operation object with the defined properties which can later be used to construct the keyword.

### Returns:
|Type|Description|
|-|-
[NegativeKeywordListOperation](./NegativeKeywordListOperation)|Operation object with the defined properties which can later be used to construct the keyword.

## <a name="withname~string-name~"></a>withName(String name)
Returns a negative keyword list builder with the name set to the specified value.

### Arguments:
|Name|Type|Description|
|-|-|-
name|String|Name of the new negative keyword list.
### Returns:
|Type|Description|
|-|-
[NegativeKeywordListBuilder](./NegativeKeywordListBuilder)|Negative keyword list builder with the name set to the specified value.

