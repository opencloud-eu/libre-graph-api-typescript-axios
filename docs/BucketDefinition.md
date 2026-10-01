# BucketDefinition

Provides the details of how to generate the aggregation buckets in the response. Follows the [MS Graph bucketAggregationDefinition](https://learn.microsoft.com/en-us/graph/api/resources/bucketaggregationdefinition) resource type. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**sortBy** | **string** | The possible values are &#x60;count&#x60; to sort by the number of matches in the aggregation, &#x60;keyAsString&#x60; to sort alphabetically based on the key in the aggregation, and &#x60;keyAsNumber&#x60; to sort numerically based on the key in the aggregation. Required.  | [default to undefined]
**isDescending** | **boolean** | Set to &#x60;true&#x60; to specify the sort order as descending. Optional, defaults to &#x60;false&#x60; (ascending).  | [optional] [default to false]
**minimumCount** | **number** | The minimum number of items that should be present in the aggregation for the bucket to be returned in the response. Optional, default is 0.  | [optional] [default to 0]
**ranges** | [**Array&lt;BucketAggregationRange&gt;**](BucketAggregationRange.md) | Specifies the manual ranges to compute the aggregation buckets. This is only valid for non-string facets of date or numeric type. Optional. Follows the [MS Graph bucketAggregationRange](https://learn.microsoft.com/en-us/graph/api/resources/bucketaggregationrange) resource type.  | [optional] [default to undefined]

## Example

```typescript
import { BucketDefinition } from './api';

const instance: BucketDefinition = {
    sortBy,
    isDescending,
    minimumCount,
    ranges,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
