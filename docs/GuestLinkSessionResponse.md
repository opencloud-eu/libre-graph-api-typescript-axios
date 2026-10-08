# GuestLinkSessionResponse

Response body for a successful guest link authentication: the share (permission) id the guest was invited to. A session cookie is set via the Set-Cookie header.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**permissionId** | **string** | Identifier of the share (permission) the guest was invited to. | [default to undefined]

## Example

```typescript
import { GuestLinkSessionResponse } from './api';

const instance: GuestLinkSessionResponse = {
    permissionId,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
