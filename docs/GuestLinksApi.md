# GuestLinksApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**redeemGuestLink**](#redeemguestlink) | **POST** /v1beta1/extensions/org.libregraph/guestLinks/redeem | Redeem a guest link token|

# **redeemGuestLink**
> GuestLinkRedeemResponse redeemGuestLink(guestLinkRedeemRequest)

Redeem a guest link token to obtain a guest session.

### Example

```typescript
import {
    GuestLinksApi,
    Configuration,
    GuestLinkRedeemRequest
} from './api';

const configuration = new Configuration();
const apiInstance = new GuestLinksApi(configuration);

let guestLinkRedeemRequest: GuestLinkRedeemRequest; //

const { status, data } = await apiInstance.redeemGuestLink(
    guestLinkRedeemRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **guestLinkRedeemRequest** | **GuestLinkRedeemRequest**|  | |


### Return type

**GuestLinkRedeemResponse**

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Success |  * Set-Cookie - Host-only, HttpOnly and Secure guest session cookie (default name &#x60;__Host-oc_guest_session&#x60;). <br>  |
|**400** | The request body is malformed. |  -  |
|**401** | The token is invalid or has expired. |  -  |
|**404** | The token or the referenced share could not be found. |  -  |
|**409** | The token has already been redeemed. |  -  |
|**410** | The referenced share has expired. |  -  |
|**500** | An internal error occurred. |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

