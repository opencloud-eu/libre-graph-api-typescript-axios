# DrivesApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createDrive**](#createdrive) | **POST** /v1.0/drives | Create a new drive of a specific type|
|[**createDriveBeta**](#createdrivebeta) | **POST** /v1beta1/drives | Alias for creating a drive with \&#39;/v1.0/drives\&#39;, but the new drive is returned in the v1beta1 format, with grantedToV2 and unified role IDs in its permissions|
|[**deleteDrive**](#deletedrive) | **DELETE** /v1.0/drives/{drive-id} | Delete a specific space|
|[**deleteDriveBeta**](#deletedrivebeta) | **DELETE** /v1beta1/drives/{drive-id} | Alias for deleting a drive with \&#39;/v1.0/drives/{drive-id}\&#39;|
|[**getDrive**](#getdrive) | **GET** /v1.0/drives/{drive-id} | Get drive by id|
|[**getDriveBeta**](#getdrivebeta) | **GET** /v1beta1/drives/{drive-id} | Alias for \&#39;/v1.0/drives/{drive-id}\&#39;, but the drive is returned in the v1beta1 format, with grantedToV2 and unified role IDs in its permissions|
|[**updateDrive**](#updatedrive) | **PATCH** /v1.0/drives/{drive-id} | Update the drive|
|[**updateDriveBeta**](#updatedrivebeta) | **PATCH** /v1beta1/drives/{drive-id} | Alias for updating a drive with \&#39;/v1.0/drives/{drive-id}\&#39;, but the updated drive is returned in the v1beta1 format, with grantedToV2 and unified role IDs in its permissions|

# **createDrive**
> Drive createDrive(drive)


### Example

```typescript
import {
    DrivesApi,
    Configuration,
    Drive
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let drive: Drive; //New space property values

const { status, data } = await apiInstance.createDrive(
    drive
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **drive** | **Drive**| New space property values | |


### Return type

**Drive**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Created |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **createDriveBeta**
> Drive createDriveBeta(drive)


### Example

```typescript
import {
    DrivesApi,
    Configuration,
    Drive
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let drive: Drive; //New space property values

const { status, data } = await apiInstance.createDriveBeta(
    drive
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **drive** | **Drive**| New space property values | |


### Return type

**Drive**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Created |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteDrive**
> deleteDrive()


### Example

```typescript
import {
    DrivesApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let ifMatch: string; //ETag (optional) (default to undefined)

const { status, data } = await apiInstance.deleteDrive(
    driveId,
    ifMatch
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **ifMatch** | [**string**] | ETag | (optional) defaults to undefined|


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

# **deleteDriveBeta**
> deleteDriveBeta()


### Example

```typescript
import {
    DrivesApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let ifMatch: string; //ETag (optional) (default to undefined)

const { status, data } = await apiInstance.deleteDriveBeta(
    driveId,
    ifMatch
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **ifMatch** | [**string**] | ETag | (optional) defaults to undefined|


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

# **getDrive**
> Drive getDrive()


### Example

```typescript
import {
    DrivesApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let $select: Set<'@libre.graph.hasTrashedItems'>; //Select properties to be returned. By default all properties are returned. (optional) (default to undefined)

const { status, data } = await apiInstance.getDrive(
    driveId,
    $select
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **$select** | **Array<&#39;@libre.graph.hasTrashedItems&#39;>** | Select properties to be returned. By default all properties are returned. | (optional) defaults to undefined|


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

# **getDriveBeta**
> Drive getDriveBeta()


### Example

```typescript
import {
    DrivesApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let $expand: string; //Expand related entities (optional) (default to undefined)
let $select: Set<'@libre.graph.hasTrashedItems'>; //Select properties to be returned. By default all properties are returned. (optional) (default to undefined)

const { status, data } = await apiInstance.getDriveBeta(
    driveId,
    $expand,
    $select
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveId** | [**string**] | key: id of drive | defaults to undefined|
| **$expand** | [**string**] | Expand related entities | (optional) defaults to undefined|
| **$select** | **Array<&#39;@libre.graph.hasTrashedItems&#39;>** | Select properties to be returned. By default all properties are returned. | (optional) defaults to undefined|


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

# **updateDrive**
> Drive updateDrive(driveUpdate)


### Example

```typescript
import {
    DrivesApi,
    Configuration,
    DriveUpdate
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let driveUpdate: DriveUpdate; //New space values

const { status, data } = await apiInstance.updateDrive(
    driveId,
    driveUpdate
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveUpdate** | **DriveUpdate**| New space values | |
| **driveId** | [**string**] | key: id of drive | defaults to undefined|


### Return type

**Drive**

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

# **updateDriveBeta**
> Drive updateDriveBeta(driveUpdate)


### Example

```typescript
import {
    DrivesApi,
    Configuration,
    DriveUpdate
} from './api';

const configuration = new Configuration();
const apiInstance = new DrivesApi(configuration);

let driveId: string; //key: id of drive (default to undefined)
let driveUpdate: DriveUpdate; //New space values

const { status, data } = await apiInstance.updateDriveBeta(
    driveId,
    driveUpdate
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **driveUpdate** | **DriveUpdate**| New space values | |
| **driveId** | [**string**] | key: id of drive | defaults to undefined|


### Return type

**Drive**

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

