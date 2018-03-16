# KeywordOperation
Represents the definition of a keyword constructed via [KeywordBuilder](./KeywordBuilder). The keyword is added to the campaign only when one of this object's methods is invoked or when the script finishes execution, whichever comes first. To improve performance, store the operation objects in an array and only invoke its methods when all operations have been constructed.

# Methods
|Method Name|Return Type|Description|
|-|-|-
[getErrors](#geterrors)|String[]|Returns an empty array if the keyword is successfully created; otherwise, it contains the list of errors.
[getResult](#getresult)|[Keyword](./Keyword)|Returns the newly created Keyword, otherwise returns null if this operation failed to execute.<br />
[isSuccessful](#issuccessful)|boolean|Returns <br />true if the operation was successful.

## <a name="geterrors"></a>getErrors
Returns an empty array if the keyword is successfully created; otherwise, it contains the list of errors.

### Returns:
|Type|Description|
|-|-
String[]|Errors that occurred while creating the keyword.

## <a name="getresult"></a>getResult
Returns the newly created Keyword, otherwise returns null if this operation failed to execute.


### Returns:
|Type|Description|
|-|-
[Keyword](./Keyword)|The Keyword created by the
 KeywordOperation.

## <a name="issuccessful"></a>isSuccessful
Returns 
true if the operation was successful.


### Returns:
|Type|Description|
|-|-
boolean|true if the operation was successful.

