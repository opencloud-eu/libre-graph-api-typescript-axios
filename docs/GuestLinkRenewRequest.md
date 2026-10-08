# GuestLinkRenewRequest

Request body for renewing a guest link. Besides the share (permission) id, the previous guest link token or a (possibly expired) guest session cookie is required to authorize the renewal.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**permissionId** | **string** | Identifier of the share (permission) the guest was invited to. | [default to undefined]
**token** | **string** | Previous guest link token. Optional when the guest session cookie is sent instead. | [optional] [default to undefined]

## Example

```typescript
import { GuestLinkRenewRequest } from './api';

const instance: GuestLinkRenewRequest = {
    permissionId,
    token,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
