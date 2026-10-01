# SearchAggregation

Provides the details of a search aggregation in the search response. Follows the [MS Graph searchAggregation](https://learn.microsoft.com/en-us/graph/api/resources/searchaggregation) resource type. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**field** | **string** | Defines the field in the request on which the aggregation was computed.  | [optional] [default to undefined]
**buckets** | [**Array&lt;SearchBucket&gt;**](SearchBucket.md) | Defines the computed buckets for this aggregation. Buckets are sorted according to the &#x60;sortBy&#x60; and &#x60;isDescending&#x60; specified in the &#x60;bucketDefinition&#x60; of the corresponding &#x60;aggregationOption&#x60;.  | [optional] [default to undefined]
**libre_graph_metric** | [**SearchMetric**](SearchMetric.md) |  | [optional] [default to undefined]

## Example

```typescript
import { SearchAggregation } from './api';

const instance: SearchAggregation = {
    field,
    buckets,
    libre_graph_metric,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
