# GuestLinkRenewRequest

Request body for renewing a guest link. Only the share (permission) id is sent; the request is authorized by the guest session cookie when one is present.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**permissionId** | **string** | Identifier of the share (permission) the guest was invited to. | [default to undefined]

## Example

```typescript
import { GuestLinkRenewRequest } from './api';

const instance: GuestLinkRenewRequest = {
    permissionId,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
