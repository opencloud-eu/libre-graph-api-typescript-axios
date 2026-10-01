# SearchMetric

The result of a metric aggregation, the counterpart of `buckets` for aggregations requested with a `@libre.graph.metricDefinition`. Absent for terms, range and geohash aggregations. Libregraph extension not present in MS Graph. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**kind** | **string** | Echoes the &#x60;kind&#x60; of the corresponding &#x60;metricDefinition&#x60;, allowing consumers (and the search service\&#39;s cross-space merge layer) to pick the right reducer when combining results.  | [optional] [default to undefined]
**value** | **number** | The scalar result of the metric. | [optional] [default to undefined]

## Example

```typescript
import { SearchMetric } from './api';

const instance: SearchMetric = {
    kind,
    value,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
