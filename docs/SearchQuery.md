# SearchQuery

Represents the search query. Follows the [MS Graph searchQuery](https://learn.microsoft.com/en-us/graph/api/resources/searchquery) resource type. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**queryString** | **string** | The search query string in KQL (Keyword Query Language) format. The query string can contain free-text keywords and property filters.  Examples: - &#x60;budget report&#x60;: free text search - &#x60;mediatype:audio&#x60;: filter by media type - &#x60;audio.artist:\&quot;Saxon\&quot;&#x60;: filter by audio metadata - &#x60;audio.genre:Rock AND audio.year:1979&#x60;: combined filters  | [default to undefined]

## Example

```typescript
import { SearchQuery } from './api';

const instance: SearchQuery = {
    queryString,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
