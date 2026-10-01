# SearchHit

Represents an individual search result. Follows the [MS Graph searchHit](https://learn.microsoft.com/en-us/graph/api/resources/searchhit) resource type. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hitId** | **string** | The internal identifier for the item. | [optional] [readonly] [default to undefined]
**rank** | **number** | The rank or the order of the result. | [optional] [readonly] [default to undefined]
**summary** | **string** | A summary of the result, if a summary is available.  | [optional] [readonly] [default to undefined]
**resource** | [**DriveItem**](DriveItem.md) |  | [optional] [default to undefined]

## Example

```typescript
import { SearchHit } from './api';

const instance: SearchHit = {
    hitId,
    rank,
    summary,
    resource,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
