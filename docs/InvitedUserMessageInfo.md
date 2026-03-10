# InvitedUserMessageInfo

Additional information about the invitation message.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ccRecipients** | [**Array&lt;Recipient&gt;**](Recipient.md) | Additional recipients who will receive a copy of the invitation message. | [optional] [default to undefined]
**customizedMessageBody** | **string** | The customized message body that will be included in the invitation message. | [optional] [default to undefined]
**messageLanguage** | **string** | The language of the invitation message. | [optional] [default to undefined]

## Example

```typescript
import { InvitedUserMessageInfo } from './api';

const instance: InvitedUserMessageInfo = {
    ccRecipients,
    customizedMessageBody,
    messageLanguage,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
