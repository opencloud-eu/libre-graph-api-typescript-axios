# AggregationOption

Specifies an aggregation that should be computed and returned alongside search results. Follows the [MS Graph aggregationOption](https://learn.microsoft.com/en-us/graph/api/resources/aggregationoption) resource type.  For string fields, terms aggregations return the distinct values and their counts. For numeric and date fields, range aggregations can be defined using the `ranges` property of `bucketDefinition`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**field** | **string** | Specifies the field in the schema of the specified entity type that the aggregation should be computed on. Required.  Examples: &#x60;audio.artist&#x60;, &#x60;audio.genre&#x60;, &#x60;audio.year&#x60;, &#x60;mimeType&#x60;.  | [default to undefined]
**size** | **number** | The number of &#x60;searchBucket&#x60; resources to be returned. This is optional and only applies to terms aggregations. Combined with &#x60;bucketDefinition.sortBy&#x60; and &#x60;bucketDefinition.isDescending&#x60; to produce the top N results by count or key. When not specified, all buckets are returned.  | [optional] [default to undefined]
**bucketDefinition** | [**BucketDefinition**](BucketDefinition.md) |  | [optional] [default to undefined]
**libre_graph_subAggregations** | [**Array&lt;AggregationOption&gt;**](AggregationOption.md) | Nested aggregations computed within each bucket of this aggregation. Libregraph extension not present in MS Graph.  Backends that don\&#39;t support native composite aggregations (e.g. bleve) emulate them by walking the matched result set; OpenSearch translates them to native composite aggregations.  | [optional] [default to undefined]
**libre_graph_metricDefinition** | [**MetricDefinition**](MetricDefinition.md) |  | [optional] [default to undefined]

## Example

```typescript
import { AggregationOption } from './api';

const instance: AggregationOption = {
    field,
    size,
    bucketDefinition,
    libre_graph_subAggregations,
    libre_graph_metricDefinition,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
