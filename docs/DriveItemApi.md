# DriveItemApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createChildDriveItem**](#createchilddriveitem) | **POST** /v1beta1/drives/{drive-id}/items/{item-id}/children | Create a new DriveItem under a parent item|
|[**deleteDriveItem**](#deletedriveitem) | **DELETE** /v1beta1/drives/{drive-id}/items/{item-id} | Delete a DriveItem.|
|[**getDriveItem**](#getdriveitem) | **GET** /v1beta1/drives/{drive-id}/items/{item-id} | Get a DriveItem.|
|[**getDriveItemChildren**](#getdriveitemchildren) | **GET** /v1.0/drives/{drive-id}/items/{item-id}/children | List children of a DriveItem|
|[**getDriveItemContent**](#getdriveitemcontent) | **GET** /v1beta1/drives/{drive-id}/items/{item-id}/content | Download the content of a DriveItem|
|[**updateDriveItem**](#updatedriveitem) | **PATCH** /v1beta1/drives/{drive-id}/items/{item-id} | Update a DriveItem.|

# **createChildDriveItem**
> DriveItem createChildDriveItem(driveItem)

Create a new folder or DriveItem in a Drive with the specified parent item. The parent must exist and be a folder.  Modeled on the MS Graph create driveItem endpoint (https://learn.microsoft.com/en-us/graph/api/driveitem-post-children). Identical request and response shape to the [drive-root variant](#/drives.root/CreateDriveItem), just with an explicit parent item id rather than the drive root.  The request body must specify exactly one of `folder` (set to `{}` to create a folder) or `file` (to create a file item). Requests with none of these, or with both, return 400. The `@libre.graph.conflictBehavior` query parameter controls what happens if a child with the same name already exists.  This endpoint also accepts the MS Graph colon-syntax URL form:      POST /v1beta1/drives/{drive-id}/items/{item-id}:/{path}:/children  OpenAPI cannot express the colon-delimited path segment, so this URL form is not represented as a separate operation in this specification. The server still accepts it, resolves `:/{path}:` as the parent of the new item (relative to `item-id`), and applies `@libre.graph.missingParentsBehavior` to decide whether to create missing intermediate folders. 

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
let driveItem: DriveItem; //In the request body, provide a JSON object describing the new driveItem. Must specify exactly one of `folder` or `file`.
let libreGraphConflictBehavior: 'fail' | 'replace'; //Controls what happens when a child with the same name already exists. `fail` (default) returns 409; `replace` overwrites the existing item. MS Graph\'s `rename` value is not supported.  (optional) (default to 'fail')
let libreGraphMissingParentsBehavior: 'fail' | 'create'; //Controls what happens when a colon-syntax URL refers to a path whose intermediate folders don\'t all exist yet. `fail` (default) returns 404; `create` creates the missing intermediate folders before creating the final item. Only meaningful for colon-syntax URLs; ignored otherwise.  (optional) (default to 'fail')

const { status, data } = await apiInstance.createChildDriveItem(
    driveId,
    itemId,
    driveItem,
    libreGraphConflictBehavior,
    libreGraphMissingParentsBehavior
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveItem** | **DriveItem**| In the request body, provide a JSON object describing the new driveItem. Must specify exactly one of &#x60;folder&#x60; or &#x60;file&#x60;. | |
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **itemId** | [**string**] | key: id of item | defaults to undefined|
| **libreGraphConflictBehavior** | [**&#39;fail&#39; | &#39;replace&#39;**]**Array<&#39;fail&#39; &#124; &#39;replace&#39;>** | Controls what happens when a child with the same name already exists. &#x60;fail&#x60; (default) returns 409; &#x60;replace&#x60; overwrites the existing item. MS Graph\&#39;s &#x60;rename&#x60; value is not supported.  | (optional) defaults to 'fail'|
| **libreGraphMissingParentsBehavior** | [**&#39;fail&#39; | &#39;create&#39;**]**Array<&#39;fail&#39; &#124; &#39;create&#39;>** | Controls what happens when a colon-syntax URL refers to a path whose intermediate folders don\&#39;t all exist yet. &#x60;fail&#x60; (default) returns 404; &#x60;create&#x60; creates the missing intermediate folders before creating the final item. Only meaningful for colon-syntax URLs; ignored otherwise.  | (optional) defaults to 'fail'|


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
|**200** | The created DriveItem. |  -  |
|**400** | error |  -  |
|**403** | error |  -  |
|**404** | error |  -  |
|**409** | error |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

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
let $select: Set<'@microsoft.graph.downloadUrl' | '@libre.graph.permissions.actions.allowedValues'>; //Select additional properties to be returned. (optional) (default to undefined)

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
| **$select** | **Array<&#39;@microsoft.graph.downloadUrl&#39; &#124; &#39;@libre.graph.permissions.actions.allowedValues&#39;>** | Select additional properties to be returned. | (optional) defaults to undefined|


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

# **getDriveItemChildren**
> CollectionOfDriveItems getDriveItemChildren()

List the children of the item identified by `item-id` in the drive identified by `drive-id`. The item must exist and be a folder.  Modeled on the MS Graph list driveItem children endpoint (https://learn.microsoft.com/en-us/graph/api/driveitem-list-children).  This endpoint also accepts the MS Graph colon-syntax URL forms:      GET /v1.0/drives/{drive-id}/root:/{path}:/children     GET /v1.0/drives/{drive-id}/items/{item-id}:/{path}:/children  OpenAPI cannot express the colon-delimited path segment, so these URL forms are not represented as separate operations in this specification. The server still accepts them, resolves `:/{path}:` as the parent item, and lists its children. 

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

const { status, data } = await apiInstance.getDriveItemChildren(
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

**CollectionOfDriveItems**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Retrieved resource list |  -  |
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

