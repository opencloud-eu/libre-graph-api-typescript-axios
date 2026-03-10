# Invitation

Represents an invitation to a drive item. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**invitedUserDisplayName** | **string** | The display name of the user being invited. | [optional] [default to undefined]
**invitedUserEmailAddress** | **string** | The email address of the user being invited. Required. | [optional] [default to undefined]
**invitedUserMessageInfo** | [**InvitedUserMessageInfo**](InvitedUserMessageInfo.md) |  | [optional] [default to undefined]
**sendInvitationMessage** | **boolean** | Indicates whether an invitation message should be sent to the user. | [optional] [default to undefined]
**inviteRedirectUrl** | **string** | The URL to which the user is redirected after accepting the invitation. Required. | [optional] [default to undefined]
**inviteRedeemUrl** | **string** | The URL that the user can use to redeem the invitation. Read-only. | [optional] [readonly] [default to undefined]
**status** | **string** | The status of the invitation. Read-only. | [optional] [readonly] [default to undefined]
**invitedUser** | [**User**](User.md) |  | [optional] [default to undefined]
**invitedUserType** | **string** | The type of user being invited. | [optional] [default to undefined]

## Example

```typescript
import { Invitation } from './api';

const instance: Invitation = {
    invitedUserDisplayName,
    invitedUserEmailAddress,
    invitedUserMessageInfo,
    sendInvitationMessage,
    inviteRedirectUrl,
    inviteRedeemUrl,
    status,
    invitedUser,
    invitedUserType,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
