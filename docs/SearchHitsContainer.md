# SearchHitsContainer

Contains a collection of search results. Follows the [MS Graph searchHitsContainer](https://learn.microsoft.com/en-us/graph/api/resources/searchhitscontainer) resource type. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hits** | [**Array&lt;SearchHit&gt;**](SearchHit.md) | A collection of the search results, ordered by relevance or, when the request specifies &#x60;sortProperties&#x60;, by those properties.  | [optional] [default to undefined]
**total** | **number** | The total number of results. Note this is not the number of results on the page, but the total number of results satisfying the query.  | [optional] [readonly] [default to undefined]
**moreResultsAvailable** | **boolean** | Provides information if more results are available. Based on this information, you can adjust the &#x60;from&#x60; and &#x60;size&#x60; properties of the &#x60;searchRequest&#x60; accordingly.  | [optional] [readonly] [default to undefined]
**aggregations** | [**Array&lt;SearchAggregation&gt;**](SearchAggregation.md) | Contains the collection of aggregations computed based on the provided &#x60;aggregationOption&#x60; definitions in the request.  | [optional] [default to undefined]

## Example

```typescript
import { SearchHitsContainer } from './api';

const instance: SearchHitsContainer = {
    hits,
    total,
    moreResultsAvailable,
    aggregations,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
