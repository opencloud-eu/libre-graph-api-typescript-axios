# GuestLinkError

Error returned by a guest link endpoint.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**errorType** | **string** | Machine-readable error identifier. | [default to undefined]
**message** | **string** | Human-readable error message. | [default to undefined]
**permissionId** | **string** | Permission (share) identifier related to the error, when known. | [default to undefined]
**retryAfter** | **number** | Number of seconds the client should wait before retrying. Present on rate-limited (429) responses and mirrored in the Retry-After response header. | [optional] [default to undefined]

## Example

```typescript
import { GuestLinkError } from './api';

const instance: GuestLinkError = {
    errorType,
    message,
    permissionId,
    retryAfter,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
