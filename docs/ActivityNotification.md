# ActivityNotification

An activity someone is notified about. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**topic** | [**ActivityTopic**](ActivityTopic.md) |  | [default to undefined]
**activityType** | **string** | What happened. Only &#x60;mentioned&#x60; is supported at the time of writing.  | [default to undefined]
**teamsAppId** | **string** | The app the activity happened in, as an id the server knows.  | [default to undefined]

## Example

```typescript
import { ActivityNotification } from './api';

const instance: ActivityNotification = {
    topic,
    activityType,
    teamsAppId,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
