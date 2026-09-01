# PendingOperationsPendingContentUpdate

An update to the item\'s content has not completed, for example post-processing such as virus scanning after an upload. MS Graph does not specify how reads behave while this is present; in OpenCloud content requests fail. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**queuedDateTime** | **string** | Time the operation was queued. May be absent. Read-only. | [optional] [readonly] [default to undefined]

## Example

```typescript
import { PendingOperationsPendingContentUpdate } from './api';

const instance: PendingOperationsPendingContentUpdate = {
    queuedDateTime,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
