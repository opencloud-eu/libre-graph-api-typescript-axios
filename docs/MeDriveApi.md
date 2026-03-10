# MeDriveApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**followDriveItem**](#followdriveitem) | **POST** /v1.0/me/drive/items/{item-id}/follow | Follow a DriveItem|
|[**getHome**](#gethome) | **GET** /v1.0/me/drive | Get personal space for user|
|[**listSharedByMe**](#listsharedbyme) | **GET** /v1beta1/me/drive/sharedByMe | Get a list of driveItem objects shared by the current user.|
|[**listSharedWithMe**](#listsharedwithme) | **GET** /v1beta1/me/drive/sharedWithMe | Get a list of driveItem objects shared with the owner of a drive.|
|[**unfollowDriveItem**](#unfollowdriveitem) | **DELETE** /v1.0/me/drive/following/{item-id} | Unfollow a DriveItem|

# **followDriveItem**
> DriveItem followDriveItem()

Follow a DriveItem.

### Example

```typescript
import {
    MeDriveApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MeDriveApi(configuration);

let itemId: string; //key: id of item (default to undefined)

const { status, data } = await apiInstance.followDriveItem(
    itemId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **itemId** | [**string**] | key: id of item | defaults to undefined|


### Return type

**DriveItem**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Created |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getHome**
> Drive getHome()


### Example

```typescript
import {
    MeDriveApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MeDriveApi(configuration);

const { status, data } = await apiInstance.getHome();
```

### Parameters
This endpoint does not have any parameters.


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
|**200** | Retrieved personal space |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listSharedByMe**
> CollectionOfDriveItems1 listSharedByMe()

The `driveItems` returned from the `sharedByMe` method always include the `permissions` relation that indicates they are shared items. 

### Example

```typescript
import {
    MeDriveApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MeDriveApi(configuration);

let $expand: Set<'thumbnails'>; //Expand related entities (optional) (default to undefined)

const { status, data } = await apiInstance.listSharedByMe(
    $expand
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **$expand** | **Array<&#39;thumbnails&#39;>** | Expand related entities | (optional) defaults to undefined|


### Return type

**CollectionOfDriveItems1**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | OK |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listSharedWithMe**
> CollectionOfDriveItems1 listSharedWithMe()

The `driveItems` returned from the `sharedWithMe` method always include the `remoteItem` facet that indicates they are items from a different drive. 

### Example

```typescript
import {
    MeDriveApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MeDriveApi(configuration);

let $expand: Set<'thumbnails'>; //Expand related entities (optional) (default to undefined)

const { status, data } = await apiInstance.listSharedWithMe(
    $expand
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **$expand** | **Array<&#39;thumbnails&#39;>** | Expand related entities | (optional) defaults to undefined|


### Return type

**CollectionOfDriveItems1**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | OK |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **unfollowDriveItem**
> unfollowDriveItem()

Unfollow a DriveItem.

### Example

```typescript
import {
    MeDriveApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MeDriveApi(configuration);

let itemId: string; //key: id of item (default to undefined)

const { status, data } = await apiInstance.unfollowDriveItem(
    itemId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **itemId** | [**string**] | key: id of item | defaults to undefined|


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
|**204** | No Content |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

