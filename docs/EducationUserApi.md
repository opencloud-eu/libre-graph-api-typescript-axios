# EducationUserApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createEducationUser**](#createeducationuser) | **POST** /v1.0/education/users | Add new education user|
|[**deleteEducationUser**](#deleteeducationuser) | **DELETE** /v1.0/education/users/{user-id} | Delete educationUser|
|[**getEducationUser**](#geteducationuser) | **GET** /v1.0/education/users/{user-id} | Get properties of educationUser|
|[**listEducationUsers**](#listeducationusers) | **GET** /v1.0/education/users | Get entities from education users|
|[**updateEducationUser**](#updateeducationuser) | **PATCH** /v1.0/education/users/{user-id} | Update properties of educationUser|

# **createEducationUser**
> EducationUser createEducationUser(educationUser)


### Example

```typescript
import {
    EducationUserApi,
    Configuration,
    EducationUser
} from './api';

const configuration = new Configuration();
const apiInstance = new EducationUserApi(configuration);

let educationUser: EducationUser; //New entity

const { status, data } = await apiInstance.createEducationUser(
    educationUser
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **educationUser** | **EducationUser**| New entity | |


### Return type

**EducationUser**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Created entity |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteEducationUser**
> deleteEducationUser()

Deletes an education user by their internal ID.  **To delete by external ID:** If you only have an external ID, you must first retrieve the user\'s internal ID: 1. Call `GET /graph/v1.0/education/users?$filter=externalId eq \'{value}\'` 2. Extract the `id` from the response 3. Use that `id` in this DELETE endpoint  See the [ListEducationUsers](#/educationUser/ListEducationUsers) operation for query details. 

### Example

```typescript
import {
    EducationUserApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new EducationUserApi(configuration);

let userId: string; //key: internal user id (UUID format) or username of user.  **Note:** If you only have an external ID, first query the user with `GET /graph/v1.0/education/users?$filter=externalId eq \'{value}\'` to retrieve the internal ID.  (default to undefined)

const { status, data } = await apiInstance.deleteEducationUser(
    userId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **userId** | [**string**] | key: internal user id (UUID format) or username of user.  **Note:** If you only have an external ID, first query the user with &#x60;GET /graph/v1.0/education/users?$filter&#x3D;externalId eq \&#39;{value}\&#39;&#x60; to retrieve the internal ID.  | defaults to undefined|


### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**204** | Success |  -  |
|**404** | User not found |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getEducationUser**
> EducationUser getEducationUser()


### Example

```typescript
import {
    EducationUserApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new EducationUserApi(configuration);

let userId: string; //key: id or username of user (default to undefined)
let $expand: Set<'memberOf'>; //Expand related entities (optional) (default to undefined)

const { status, data } = await apiInstance.getEducationUser(
    userId,
    $expand
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **userId** | [**string**] | key: id or username of user | defaults to undefined|
| **$expand** | **Array<&#39;memberOf&#39;>** | Expand related entities | (optional) defaults to undefined|


### Return type

**EducationUser**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Retrieved entity |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listEducationUsers**
> CollectionOfEducationUser listEducationUsers()

Retrieves a collection of education users with optional filtering, ordering, and expansion.  **Filtering by external ID:** Use `$filter` to query users by their external identifier, for example: `$filter=externalId eq \'EX12345\'` 

### Example

```typescript
import {
    EducationUserApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new EducationUserApi(configuration);

let $filter: string; //Filter items by property values. Supports a subset of OData filter expressions.  **Supported filters:** - By external ID: `externalId eq \'ext_12345\'`  (optional) (default to undefined)
let $orderby: Set<'displayName' | 'displayName desc' | 'mail' | 'mail desc' | 'onPremisesSamAccountName' | 'onPremisesSamAccountName desc'>; //Order items by property values (optional) (default to undefined)
let $expand: Set<'memberOf'>; //Expand related entities (optional) (default to undefined)

const { status, data } = await apiInstance.listEducationUsers(
    $filter,
    $orderby,
    $expand
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **$filter** | [**string**] | Filter items by property values. Supports a subset of OData filter expressions.  **Supported filters:** - By external ID: &#x60;externalId eq \&#39;ext_12345\&#39;&#x60;  | (optional) defaults to undefined|
| **$orderby** | **Array<&#39;displayName&#39; &#124; &#39;displayName desc&#39; &#124; &#39;mail&#39; &#124; &#39;mail desc&#39; &#124; &#39;onPremisesSamAccountName&#39; &#124; &#39;onPremisesSamAccountName desc&#39;>** | Order items by property values | (optional) defaults to undefined|
| **$expand** | **Array<&#39;memberOf&#39;>** | Expand related entities | (optional) defaults to undefined|


### Return type

**CollectionOfEducationUser**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Retrieved entities |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateEducationUser**
> EducationUser updateEducationUser(educationUser)


### Example

```typescript
import {
    EducationUserApi,
    Configuration,
    EducationUser
} from './api';

const configuration = new Configuration();
const apiInstance = new EducationUserApi(configuration);

let userId: string; //key: id or username of user (default to undefined)
let educationUser: EducationUser; //New property values

const { status, data } = await apiInstance.updateEducationUser(
    userId,
    educationUser
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **educationUser** | **EducationUser**| New property values | |
| **userId** | [**string**] | key: id or username of user | defaults to undefined|


### Return type

**EducationUser**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Success |  -  |
|**204** | Success |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

