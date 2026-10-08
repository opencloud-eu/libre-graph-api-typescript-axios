# GuestLinkVerifyPinRequest

Request body for verifying a guest link PIN.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**pin** | **string** | One-time PIN received from the renewed guest link. | [default to undefined]
**permissionId** | **string** | Identifier of the share (permission) the guest was invited to. | [default to undefined]

## Example

```typescript
import { GuestLinkVerifyPinRequest } from './api';

const instance: GuestLinkVerifyPinRequest = {
    pin,
    permissionId,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
