# SearchResponse

Represents the response for an individual search request. Follows the [MS Graph searchResponse](https://learn.microsoft.com/en-us/graph/api/resources/searchresponse) resource type. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**searchTerms** | **Array&lt;string&gt;** | Contains the search terms sent in the initial search query. | [optional] [default to undefined]
**hitsContainers** | [**Array&lt;SearchHitsContainer&gt;**](SearchHitsContainer.md) | A collection of search result sets. One for each entity type that was queried.  | [optional] [default to undefined]

## Example

```typescript
import { SearchResponse } from './api';

const instance: SearchResponse = {
    searchTerms,
    hitsContainers,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
