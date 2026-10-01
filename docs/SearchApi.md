# SearchApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**searchQuery**](#searchquery) | **POST** /v1beta1/search/query | Search for resources|

# **searchQuery**
> SearchQuery200Response searchQuery(searchQueryRequest)

Run a specified search query. Search results are provided in the response.  The search endpoint allows clients to search for resources across all accessible spaces and retrieve aggregated metadata (facets) about the result set.  Aggregations can be used to group results by properties such as file type, author, or any indexed metadata field. This is useful for building faceted search UIs or computing statistics about the result set.  The query string uses KQL (Keyword Query Language) syntax for filtering. Results are sorted by relevance unless the request specifies `sortProperties`.  Modeled on the MS Graph search query endpoint (https://learn.microsoft.com/en-us/graph/api/search-query). Request and response follow the MS Graph resource types; Libregraph additions carry the `@libre.graph.` prefix. 

### Example

```typescript
import {
    SearchApi,
    Configuration,
    SearchQueryRequest
} from './api';

const configuration = new Configuration();
const apiInstance = new SearchApi(configuration);

let searchQueryRequest: SearchQueryRequest; //
let $expand: Set<'thumbnails'>; //Relationships to expand inline on each hit\'s driveItem. Only `thumbnails` is supported, attaching a preview thumbnail set for thumbnailable mime types. Libregraph extension: MS Graph search has no $expand and returns no thumbnails on search hits.  (optional) (default to undefined)

const { status, data } = await apiInstance.searchQuery(
    searchQueryRequest,
    $expand
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **searchQueryRequest** | **SearchQueryRequest**|  | |
| **$expand** | **Array<&#39;thumbnails&#39;>** | Relationships to expand inline on each hit\&#39;s driveItem. Only &#x60;thumbnails&#x60; is supported, attaching a preview thumbnail set for thumbnailable mime types. Libregraph extension: MS Graph search has no $expand and returns no thumbnails on search hits.  | (optional) defaults to undefined|


### Return type

**SearchQuery200Response**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | OK |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

