# PendingOperations

Present while operations affecting the item\'s content have not completed, whether still queued or already running. While present, requests for the item\'s content fail, the content is withheld until processing completes and the facet disappears. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**pendingContentUpdate** | [**PendingOperationsPendingContentUpdate**](PendingOperationsPendingContentUpdate.md) |  | [optional] [default to undefined]

## Example

```typescript
import { PendingOperations } from './api';

const instance: PendingOperations = {
    pendingContentUpdate,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
