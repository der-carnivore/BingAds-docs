# NegativeKeywordListOperation
Represents the definition of a keyword constructed via [NegativeKeywordListBuilder](./NegativeKeywordListBuilder). The negative keyword list is only stored in the system when any of the methods on this object are invoked or when the script finishes execution, whichever comes first. To make the script execute more efficiently, store the operation objects in an array and only invoke its methods when all operations have been constructed.
# Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|String[]|Returns an empty array if the negative keyword list is successfully created; otherwise, it contains the list of errors.
[getResult](#getresult)|[NegativeKeywordList](./NegativeKeywordList)|Returns the newly created NegativeKeywordList, otherwise returns null if the operation failed.
[isSuccessful](#issuccessful)|Boolean|Returns a Boolean value that determines if this operation was successful.

## <a name="geterrors"></a>getErrors
Returns an empty array if the negative keyword list is successfully created; otherwise, it contains the list of errors.

### Returns:
|Type|Description|
|-|-
String[]|Errors that occurred while creating the negative keyword list.

## <a name="getresult"></a>getResult
Returns the newly created NegativeKeywordList, otherwise returns null if the operation failed.

### Returns:
|Type|Description|
|-|-
[NegativeKeywordList](./NegativeKeywordList)|NegativeKeywordList created by the NegativeKeywordListOperation.

## <a name="issuccessful"></a>isSuccessful
Returns a Boolean value that determines if this operation was successful.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this operation was successful.

