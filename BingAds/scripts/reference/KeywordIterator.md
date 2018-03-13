# KeywordIterator
Provides methods to iterate through a list of keywords. For more information about Iterators, see [Iterators](../concepts/iterators).
Example usage:
```javascript
 var keywordSelector = BingAdsApp.keywords();
 var keywordIterator = keywordSelector.get();
 while (keywordIterator.hasNext()) {
   var keyword = keywordIterator.next();
 }
```

See also:

- [KeywordSelector.get()](./KeywordSelector#get)
- [Keyword](./Keyword)


# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that determines if this iterator has more keyword elements.
[next](#next)|[Keyword](./Keyword)|Advances to the next keyword in this iterator and returns it.
[totalNumEntities](#totalnumentities)|int|Returns the total number of keywords indexed by this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that determines if this iterator has more keyword elements.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this iterator has more keyword elements.

## <a name="next"></a>next
Advances to the next keyword in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[Keyword](./Keyword)|Next keyword in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of keywords indexed by this iterator. hasNext will start to return false and next will start to throw exceptions when the limit for entity reads has been reached, even if the selector matched more entities.

### Returns:
|Type|Description|
|-|-
int|Number of keywords matched by the selector which generated this iterator.

