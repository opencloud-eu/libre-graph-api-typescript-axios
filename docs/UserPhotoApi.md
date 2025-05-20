# UserPhotoApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getUserPhoto**](#getuserphoto) | **GET** /v1.0/users/{user-id}/photo/$value | Get the photo of a user|

# **getUserPhoto**
> File getUserPhoto()


### Example

```typescript
import {
    UserPhotoApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new UserPhotoApi(configuration);

let userId: string; //key: id or name of user (default to undefined)

const { status, data } = await apiInstance.getUserPhoto(
    userId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **userId** | [**string**] | key: id or name of user | defaults to undefined|


### Return type

**File**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: image/jpeg, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Retrieved photo |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

