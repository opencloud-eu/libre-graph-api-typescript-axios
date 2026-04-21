# DriveItemApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**deleteDriveItem**](#deletedriveitem) | **DELETE** /v1beta1/drives/{drive-id}/items/{item-id} | Delete a DriveItem.|
|[**getDriveItem**](#getdriveitem) | **GET** /v1beta1/drives/{drive-id}/items/{item-id} | Get a DriveItem.|
|[**getDriveItemContent**](#getdriveitemcontent) | **GET** /v1beta1/drives/{drive-id}/items/{item-id}/content | Download the content of a DriveItem|
|[**updateDriveItem**](#updatedriveitem) | **PATCH** /v1beta1/drives/{drive-id}/items/{item-id} | Update a DriveItem.|

# **deleteDriveItem**
> deleteDriveItem()

Delete a DriveItem by using its ID.  Deleting items using this method moves the items to the recycle bin instead of permanently deleting the item.  Mounted shares in the share jail are unmounted. The `@client.synchronize` property of the `driveItem` in the [sharedWithMe](#/me.drive/ListSharedWithMe) endpoint will change to false. 

### Example

```typescript
import {
    DriveItemApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new DriveItemApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let itemId: string; //key: id of item (default to undefined)

const { status, data } = await apiInstance.deleteDriveItem(
    driveId,
    itemId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
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
|**204** | Success |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getDriveItem**
> DriveItem getDriveItem()

Get a DriveItem by using its ID. 

### Example

```typescript
import {
    DriveItemApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new DriveItemApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let itemId: string; //key: id of item (default to undefined)
let $select: Set<'@microsoft.graph.downloadUrl'>; //Select additional properties to be returned. (optional) (default to undefined)

const { status, data } = await apiInstance.getDriveItem(
    driveId,
    itemId,
    $select
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **itemId** | [**string**] | key: id of item | defaults to undefined|
| **$select** | **Array<&#39;@microsoft.graph.downloadUrl&#39;>** | Select additional properties to be returned. | (optional) defaults to undefined|


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
|**200** | Retrieved driveItem |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getDriveItemContent**
> OdataError getDriveItemContent()

Download the contents of the primary stream (file) of a driveItem. Only driveItem objects with a `file` facet can be downloaded.  The response is a `302 Found` redirecting to a pre-authenticated download URL for the file. This is the same URL that is returned via the `@microsoft.graph.downloadUrl` instance annotation on the driveItem when requested via `$select`. Choose between the two based on whether you want to call the redirecting `/content` endpoint directly (for example, with a client that follows redirects automatically) or you want to inspect / schedule / prefetch the URL yourself via the annotation.  The pre-authenticated URL is short-lived and does not require an `Authorization` header.  To download a partial range of bytes, apply the `Range` header to the redirect target (the pre-authenticated URL), not to the `/content` request. 

### Example

```typescript
import {
    DriveItemApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new DriveItemApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let itemId: string; //key: id of item (default to undefined)

const { status, data } = await apiInstance.getDriveItemContent(
    driveId,
    itemId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **itemId** | [**string**] | key: id of item | defaults to undefined|


### Return type

**OdataError**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**302** | Pre-authenticated redirect to the file content. |  * Location - The pre-authenticated URL where the content can be downloaded. <br>  |
|**404** | The driveItem was not found or is not a file. |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateDriveItem**
> DriveItem updateDriveItem(driveItem)

Update a DriveItem.  The request body must include a JSON object with the properties to update. Only the properties that are provided will be updated.  Currently it supports updating the following properties:  * `@UI.Hidden` - Hides the item from the UI. 

### Example

```typescript
import {
    DriveItemApi,
    Configuration,
    DriveItem
} from './api';

const configuration = new Configuration();
const apiInstance = new DriveItemApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let itemId: string; //key: id of item (default to undefined)
let driveItem: DriveItem; //DriveItem properties to update

const { status, data } = await apiInstance.updateDriveItem(
    driveId,
    itemId,
    driveItem
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveItem** | **DriveItem**| DriveItem properties to update | |
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **itemId** | [**string**] | key: id of item | defaults to undefined|


### Return type

**DriveItem**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Success |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

