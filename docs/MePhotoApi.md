# MePhotoApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**deleteOwnUserPhoto**](#deleteownuserphoto) | **DELETE** /v1.0/me/photo/$value | Delete the current user\&#39;s profile photo|
|[**getOwnUserPhoto**](#getownuserphoto) | **GET** /v1.0/me/photo/$value | Get the current user\&#39;s profile photo|
|[**updateOwnUserPhotoPatch**](#updateownuserphotopatch) | **PATCH** /v1.0/me/photo/$value | Update the current user\&#39;s profile photo|
|[**updateOwnUserPhotoPut**](#updateownuserphotoput) | **PUT** /v1.0/me/photo/$value | Update the current user\&#39;s profile photo|

# **deleteOwnUserPhoto**
> deleteOwnUserPhoto()


### Example

```typescript
import {
    MePhotoApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MePhotoApi(configuration);

const { status, data } = await apiInstance.deleteOwnUserPhoto();
```

### Parameters
This endpoint does not have any parameters.


### Return type

void (empty response body)

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**204** | Success |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getOwnUserPhoto**
> File getOwnUserPhoto()


### Example

```typescript
import {
    MePhotoApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MePhotoApi(configuration);

const { status, data } = await apiInstance.getOwnUserPhoto();
```

### Parameters
This endpoint does not have any parameters.


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
|**200** | Retrieved profile photo |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateOwnUserPhotoPatch**
> updateOwnUserPhotoPatch()


### Example

```typescript
import {
    MePhotoApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MePhotoApi(configuration);

let body: File; //New user photo (optional)

const { status, data } = await apiInstance.updateOwnUserPhotoPatch(
    body
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **body** | **File**| New user photo | |


### Return type

void (empty response body)

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: image/jpeg
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**204** | Success |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateOwnUserPhotoPut**
> updateOwnUserPhotoPut()


### Example

```typescript
import {
    MePhotoApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MePhotoApi(configuration);

let body: File; //New user photo (optional)

const { status, data } = await apiInstance.updateOwnUserPhotoPut(
    body
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **body** | **File**| New user photo | |


### Return type

void (empty response body)

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: image/jpeg
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**204** | Success |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

