# GuestLinksApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**renewGuestLink**](#renewguestlink) | **POST** /v1beta1/extensions/org.libregraph/guestLinks/renew | Renew a guest link|
|[**verifyGuestLinkPin**](#verifyguestlinkpin) | **POST** /v1beta1/extensions/org.libregraph/guestLinks/verify/pin | Verify a guest link PIN|
|[**verifyGuestLinkToken**](#verifyguestlinktoken) | **POST** /v1beta1/extensions/org.libregraph/guestLinks/verify/token | Verify a guest link token|

# **renewGuestLink**
> renewGuestLink(guestLinkRenewRequest)

Generate a new guest link token and PIN for an existing guest link and publish the renewal event so the guest can be notified.

### Example

```typescript
import {
    GuestLinksApi,
    Configuration,
    GuestLinkRenewRequest
} from './api';

const configuration = new Configuration();
const apiInstance = new GuestLinksApi(configuration);

let guestLinkRenewRequest: GuestLinkRenewRequest; //

const { status, data } = await apiInstance.renewGuestLink(
    guestLinkRenewRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **guestLinkRenewRequest** | **GuestLinkRenewRequest**|  | |


### Return type

void (empty response body)

### Authorization

[openId](../README.md#openId), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Success. The response has an empty body. |  -  |
|**400** | The request body is malformed. |  -  |
|**401** | The credentials are missing or do not belong to the guest link. |  -  |
|**404** | The guest link record or the referenced share could not be found. |  -  |
|**410** | The referenced share has expired. |  -  |
|**500** | An internal error occurred. |  -  |
|**503** | The service is unable to publish the renewal event. |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **verifyGuestLinkPin**
> GuestLinkSessionResponse verifyGuestLinkPin(guestLinkVerifyPinRequest)

Exchange a PIN and a share id for a guest session.

### Example

```typescript
import {
    GuestLinksApi,
    Configuration,
    GuestLinkVerifyPinRequest
} from './api';

const configuration = new Configuration();
const apiInstance = new GuestLinksApi(configuration);

let guestLinkVerifyPinRequest: GuestLinkVerifyPinRequest; //

const { status, data } = await apiInstance.verifyGuestLinkPin(
    guestLinkVerifyPinRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **guestLinkVerifyPinRequest** | **GuestLinkVerifyPinRequest**|  | |


### Return type

**GuestLinkSessionResponse**

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
|**401** | The PIN is invalid or has expired. |  -  |
|**404** | The referenced share could not be found. |  -  |
|**410** | The referenced share has expired. |  -  |
|**500** | An internal error occurred. |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **verifyGuestLinkToken**
> GuestLinkSessionResponse verifyGuestLinkToken(guestLinkVerifyTokenRequest)

Verify a guest link token to obtain a guest session.

### Example

```typescript
import {
    GuestLinksApi,
    Configuration,
    GuestLinkVerifyTokenRequest
} from './api';

const configuration = new Configuration();
const apiInstance = new GuestLinksApi(configuration);

let guestLinkVerifyTokenRequest: GuestLinkVerifyTokenRequest; //

const { status, data } = await apiInstance.verifyGuestLinkToken(
    guestLinkVerifyTokenRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **guestLinkVerifyTokenRequest** | **GuestLinkVerifyTokenRequest**|  | |


### Return type

**GuestLinkSessionResponse**

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

