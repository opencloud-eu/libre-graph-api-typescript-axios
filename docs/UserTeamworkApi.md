# UserTeamworkApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**sendActivityNotification**](#sendactivitynotification) | **POST** /v1.0/users/{user-id}/teamwork/sendActivityNotification | Send an activity notification to a user|

# **sendActivityNotification**
> sendActivityNotification(activityNotification)

Sends a notification about an activity to a user. The sender is the caller, the recipient is the user in the path, `activityType` says what happened and `topic` says what it happened on. 

### Example

```typescript
import {
    UserTeamworkApi,
    Configuration,
    ActivityNotification
} from './api';

const configuration = new Configuration();
const apiInstance = new UserTeamworkApi(configuration);

let userId: string; //key: id or name of user (default to undefined)
let activityNotification: ActivityNotification; //The activity the user is notified about.

const { status, data } = await apiInstance.sendActivityNotification(
    userId,
    activityNotification
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **activityNotification** | **ActivityNotification**| The activity the user is notified about. | |
| **userId** | [**string**] | key: id or name of user | defaults to undefined|


### Return type

void (empty response body)

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**202** | Accepted |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

