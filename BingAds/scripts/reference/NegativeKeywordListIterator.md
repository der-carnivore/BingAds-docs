# NegativeKeywordListIterator
Provides methods to iterate through a list of negative keyword lists. For information about Iterators, see [Iterators](../concepts/iterators).

Example usage:
```javascript
var negativeKeywordListSelector = BingAdsApp.negativeKeywordLists();
var negativeKeywordListIterator = negativeKeywordListSelector.get();
while (negativeKeywordListIterator.hasNext()) {
  var negativeKeywordList = negativeKeywordListIterator.next();
}
```

See also:
- [NegativeKeywordListSelector.get()](./NegativeKeywordListSelector#get)
- [NegativeKeywordList](./NegativeKeywordList)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that determines if this iterator has more elements.
[next](#next)|[AdGroup](./AdGroup)|Advances to the next negative keyword lists in this iterator and returns it.
[totalNumEntities](#totalnumentities)|int|Returns the total number of negative keyword lists indexed by this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that determines if this iterator has more elements.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this iterator has more elements.

## <a name="next"></a>next
Advances to the next negative keyword lists in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[AdGroup](./AdGroup)|Next ad group in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of negative keyword lists indexed by this iterator. 

### Returns:
|Type|Description|
|-|-
int|Number of ad groups matched by the selector which generated this iterator.

