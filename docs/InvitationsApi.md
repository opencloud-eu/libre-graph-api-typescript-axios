# InvitationsApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createInvitation**](#createinvitation) | **POST** /v1.0/invitations | Create a new invitation|
|[**getInvitation**](#getinvitation) | **GET** /v1.0/invitations/{invitation-id} | Get an invitation by key|
|[**listInvitations**](#listinvitations) | **GET** /v1.0/invitations | Get a list of invitations|

# **createInvitation**
> Invitation createInvitation()


### Example

```typescript
import {
    InvitationsApi,
    Configuration,
    Invitation
} from './api';

const configuration = new Configuration();
const apiInstance = new InvitationsApi(configuration);

let invitation: Invitation; //New invitation (optional)

const { status, data } = await apiInstance.createInvitation(
    invitation
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **invitation** | **Invitation**| New invitation | |


### Return type

**Invitation**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**201** | Invitation created successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getInvitation**
> Invitation getInvitation()


### Example

```typescript
import {
    InvitationsApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new InvitationsApi(configuration);

let invitationId: string; //key: id of invitation (default to undefined)

const { status, data } = await apiInstance.getInvitation(
    invitationId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **invitationId** | [**string**] | key: id of invitation | defaults to undefined|


### Return type

**Invitation**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Retrieved invitation |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listInvitations**
> CollectionOfInvitations listInvitations()


### Example

```typescript
import {
    InvitationsApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new InvitationsApi(configuration);

const { status, data } = await apiInstance.listInvitations();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**CollectionOfInvitations**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Retrieved invitations |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

