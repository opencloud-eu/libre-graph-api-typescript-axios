# GuestLinkError

Error returned by the guest link redeem endpoint.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**errorType** | **string** | Machine-readable error identifier. | [default to undefined]
**message** | **string** | Human-readable error message. | [default to undefined]
**permissionId** | **string** | Permission (share) identifier related to the error, when known. | [default to undefined]

## Example

```typescript
import { GuestLinkError } from './api';

const instance: GuestLinkError = {
    errorType,
    message,
    permissionId,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
