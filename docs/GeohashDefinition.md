# GeohashDefinition

Provides the details of how to compute a geohash-grid aggregation over `field`, which must resolve to a geo-point field (e.g. `location`). When set on an `aggregationOption`, each `searchBucket` of the corresponding `searchAggregation` carries a geohash cell as its `key`, with `count` holding the number of matches in the cell, suitable for density/heatmap rendering. `size` limits the buckets to the top N cells by count. Libregraph extension not present in MS Graph. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**precision** | **number** | The geohash length of the returned cells (1-12); higher means finer cells. Required.  | [default to undefined]

## Example

```typescript
import { GeohashDefinition } from './api';

const instance: GeohashDefinition = {
    precision,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
