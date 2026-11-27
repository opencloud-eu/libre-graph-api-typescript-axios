# UserDriveApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getUserDrive**](#getuserdrive) | **GET** /v1.0/users/{user-id}/drive | Get a user\&#39;s drive.|

# **getUserDrive**
> Drive getUserDrive()

Get the personal Drive of the user identified by `user-id`.  Modeled on the MS Graph get drive endpoint (https://learn.microsoft.com/en-us/graph/api/drive-get). 

### Example

```typescript
import {
    UserDriveApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new UserDriveApi(configuration);

let userId: string; //key: id or name of user (default to undefined)

const { status, data } = await apiInstance.getUserDrive(
    userId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **userId** | [**string**] | key: id or name of user | defaults to undefined|


### Return type

**Drive**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Retrieved drive |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

