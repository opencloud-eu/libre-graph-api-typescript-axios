# ActivityTopic

What an activity happened on.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source** | **string** | How to read the value. Only &#x60;text&#x60; is supported at the time of writing. built from it.  | [default to 'text']
**value** | **string** | With the source &#x60;text&#x60;, the id of the resource the activity happened on. | [default to undefined]

## Example

```typescript
import { ActivityTopic } from './api';

const instance: ActivityTopic = {
    source,
    value,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
