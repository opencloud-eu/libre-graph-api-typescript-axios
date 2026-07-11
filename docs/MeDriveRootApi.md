# MeDriveRootApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**homeGetRoot**](#homegetroot) | **GET** /v1.0/me/drive/root | Get root from personal space|

# **homeGetRoot**
> DriveItem homeGetRoot()


### Example

```typescript
import {
    MeDriveRootApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new MeDriveRootApi(configuration);

let $select: Set<'@microsoft.graph.downloadUrl' | '@libre.graph.permissions.actions.allowedValues'>; //Select additional properties to be returned. (optional) (default to undefined)

const { status, data } = await apiInstance.homeGetRoot(
    $select
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
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
|**200** | Retrieved resource |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

