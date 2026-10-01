# SearchRequest

Represents an individual search request within a search query. Follows the [MS Graph searchRequest](https://learn.microsoft.com/en-us/graph/api/resources/searchrequest) resource type. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**entityTypes** | **Array&lt;string&gt;** | One or more types of resources expected in the response. Currently only &#x60;driveItem&#x60; is supported.  | [default to undefined]
**query** | [**SearchQuery**](SearchQuery.md) |  | [default to undefined]
**from** | **number** | Specifies the offset for the search results. Offset 0 returns the very first result. Used together with the &#x60;size&#x60; property for pagination.  | [optional] [default to 0]
**size** | **number** | The size of the page to be retrieved. The maximum value is 500. Set to 0 to return only aggregations without any hits.  | [optional] [default to 25]
**aggregations** | [**Array&lt;AggregationOption&gt;**](AggregationOption.md) | Specifies aggregations (also known as refiners or facets) to be returned alongside the search results. Optional.  | [optional] [default to undefined]
**aggregationFilters** | **Array&lt;string&gt;** | Contains one or more filters to narrow search results to specific buckets of a prior aggregation. Build each filter from the response of a prior search that aggregated on the same field: take the &#x60;aggregationFilterToken&#x60; of the wanted &#x60;searchBucket&#x60; and combine it with the field as &#x60;{field}:{aggregationFilterToken}&#x60;, e.g. &#x60;audio.artist:\&quot;ǂǂ5361786f6e\&quot;&#x60; for a terms bucket or &#x60;audio.year:range(1980, 1990)&#x60; for a range bucket. Several buckets of the same field are combined with &#x60;{field}:or({aggregationFilterToken},{aggregationFilterToken})&#x60;. Whitespace after the commas of &#x60;range(...)&#x60; and &#x60;or(...)&#x60; is optional.  Multiple filters can be provided as separate array items. This results in a logical AND between the filters. Filters that are not built from server-issued tokens are rejected with &#x60;invalidRequest&#x60;.  | [optional] [default to undefined]
**sortProperties** | [**Array&lt;SortProperty&gt;**](SortProperty.md) | Contains the ordered collection of fields to sort the results on, primary sort key first. At most 5 sort properties. If absent, the results are sorted by relevance. See &#x60;sortProperty.name&#x60; for the set of sortable fields. Ties are broken by relevance, and results missing the sort property are placed last. Optional.  | [optional] [default to undefined]

## Example

```typescript
import { SearchRequest } from './api';

const instance: SearchRequest = {
    entityTypes,
    query,
    from,
    size,
    aggregations,
    aggregationFilters,
    sortProperties,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
