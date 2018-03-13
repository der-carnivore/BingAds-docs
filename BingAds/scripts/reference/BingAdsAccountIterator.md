# BingAdsAccountIterator
Provides methods to iterate through a list of accounts.

See also:
- [BingAdsAccountSelector.get()](./BingAdsAccountSelector#get)
- [BingAdsAccount](./BingAdsAccount)

# Methods
|Method Name|Return Type|Description|
|-|-|-
[hasNext](#hasnext)|Boolean|Returns a Boolean value that determines if this iterator has more bing ads account elements.
[next](#next)|[BingAdsAccount](./BingAdsAccount)|Advances to the next Bing Ads account in this iterator and returns it.
[totalNumEntities](#totalnumentities)|int|Returns the total number of bing ads accounts indexed by this iterator.

## <a name="hasnext"></a>hasNext
Returns a Boolean value that determines if this iterator has more bing ads account elements.

### Returns:
|Type|Description|
|-|-
Boolean|Boolean value that determines if this iterator has more Bing Ads account elements.

## <a name="next"></a>next
Advances to the next Bing Ads account in this iterator and returns it.

### Returns:
|Type|Description|
|-|-
[BingAdsAccount](./BingAdsAccount)|Next bing ads account in the iterator.

## <a name="totalnumentities"></a>totalNumEntities
Returns the total number of bing ads accounts indexed by this iterator. 

### Returns:
|Type|Description|
|-|-
int|Number of bing ads accounts matched by the selector which generated this iterator.

