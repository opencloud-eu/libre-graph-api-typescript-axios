# LockInfo

Read-only lock metadata for a file, matching the MS Graph beta lockInfo resource. Indicates whether the file is locked, the kind of lock, when it was created, when it expires and who holds it. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**lockType** | **string** | The type of lock currently held on the file. OpenCloud currently only issues exclusive locks, same as MS Graph, even if it defines more. Read-only. | [optional] [readonly] [default to undefined]
**createdDateTime** | **string** | The date and time when the lock was created, in UTC. Read-only. | [optional] [readonly] [default to undefined]
**expirationDateTime** | **string** | The date and time when the lock expires, in UTC. Read-only. | [optional] [readonly] [default to undefined]
**owners** | [**Array&lt;Identity&gt;**](Identity.md) | The collection of users that currently hold the lock on the file. Read-only. | [optional] [readonly] [default to undefined]
**libre_graph_appName** | **string** | Name of the application holding the lock, for example an office application. Not part of MS Graph. Read-only. | [optional] [readonly] [default to undefined]

## Example

```typescript
import { LockInfo } from './api';

const instance: LockInfo = {
    lockType,
    createdDateTime,
    expirationDateTime,
    owners,
    libre_graph_appName,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
