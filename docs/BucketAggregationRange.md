# BucketAggregationRange

Specifies the lower and upper bound to compute a range aggregation bucket. At least one of `from` or `to` must be provided. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from** | **string** | Defines the lower bound from which to compute the aggregation. The value is always a string. Numeric bounds must be provided as their string representation (e.g. &#x60;\&quot;1980\&quot;&#x60;). Date bounds must use the &#x60;YYYY-MM-DDTHH:mm:ssZ&#x60; format. Optional if &#x60;to&#x60; is provided.  | [optional] [default to undefined]
**to** | **string** | Defines the upper bound up to which to compute the aggregation. The value is always a string. Numeric bounds must be provided as their string representation (e.g. &#x60;\&quot;2000\&quot;&#x60;). Date bounds must use the &#x60;YYYY-MM-DDTHH:mm:ssZ&#x60; format. Optional if &#x60;from&#x60; is provided.  | [optional] [default to undefined]

## Example

```typescript
import { BucketAggregationRange } from './api';

const instance: BucketAggregationRange = {
    from,
    to,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
