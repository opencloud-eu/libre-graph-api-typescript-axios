# MetricDefinition

Provides the details of how to compute a scalar metric over the aggregation `field`, the counterpart of `bucketDefinition` for metric aggregations. When set on an `aggregationOption`, `size` is ignored, and the corresponding `searchAggregation` in the response carries a `@libre.graph.metric` rather than `buckets`. Libregraph extension not present in MS Graph. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**kind** | **string** | The reducer applied to the field values of all matches. Required.  &#x60;avg&#x60; is not a simple reducer (averages of averages are not averages): the backend carries &#x60;(sum, count)&#x60; internally and emits only the final value on the outermost merge.  | [default to undefined]

## Example

```typescript
import { MetricDefinition } from './api';

const instance: MetricDefinition = {
    kind,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
