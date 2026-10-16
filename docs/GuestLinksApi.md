# GuestLinksApi

All URIs are relative to *https://localhost:9200/graph*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**renewGuestLink**](#renewguestlink) | **POST** /v1beta1/extensions/org.libregraph/guestLinks/renew | Renew a guest link|
|[**verifyGuestLinkPin**](#verifyguestlinkpin) | **POST** /v1beta1/extensions/org.libregraph/guestLinks/verify/pin | Verify a guest link PIN|
|[**verifyGuestLinkToken**](#verifyguestlinktoken) | **POST** /v1beta1/extensions/org.libregraph/guestLinks/verify/token | Verify a guest link token|

# **renewGuestLink**
> renewGuestLink(guestLinkRenewRequest)

Renew a guest link. When the request carries a valid guest session cookie (possibly expired), a new link token and PIN are generated, the renewal event is published so the guest can be notified, and the nonce cookie that binds the PIN to the browser is set. Without a valid session the link token is rotated silently: no new PIN is generated, no nonce cookie is set, and the request is rate limited.

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
|**200** | Success. The response has an empty body. When a valid session authorized the renewal the renewed nonce is returned in the Set-Cookie header and must be sent back to the verify pin endpoint; a silent renewal (no session) sets no cookie. |  * Set-Cookie - Sets the guest session cookie &#x60;__Host-oc_guest_session&#x60; and clears the per-share nonce cookie &#x60;__Host-oc_guest_nonce_&lt;share-hash&gt;&#x60;. <br>  |
|**400** | The request body is malformed or a required field is missing. |  -  |
|**404** | The guest link record or the referenced share could not be found. |  -  |
|**409** | The guest link record was updated concurrently; the client should retry the renewal. |  -  |
|**410** | The referenced share has expired. |  -  |
|**429** | The renewal rate limit for this share has been reached. It applies to renewals without a valid session; a session-authorized renewal is not rate limited. |  * Retry-After - Number of seconds to wait before retrying. <br>  |
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

let hostOcGuestNonce: string; //Per-share nonce cookie set by the renew endpoint (`__Host-oc_guest_nonce_<share-hash>`), binding the PIN to the browser that renewed the link. (default to undefined)
let guestLinkVerifyPinRequest: GuestLinkVerifyPinRequest; //

const { status, data } = await apiInstance.verifyGuestLinkPin(
    hostOcGuestNonce,
    guestLinkVerifyPinRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **guestLinkVerifyPinRequest** | **GuestLinkVerifyPinRequest**|  | |
| **hostOcGuestNonce** | [**string**] | Per-share nonce cookie set by the renew endpoint (&#x60;__Host-oc_guest_nonce_&lt;share-hash&gt;&#x60;), binding the PIN to the browser that renewed the link. | defaults to undefined|


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
|**200** | Success. A guest session cookie is set and the nonce cookie is cleared via the Set-Cookie header. |  * Set-Cookie - Sets the guest session cookie &#x60;__Host-oc_guest_session&#x60; and clears the per-share nonce cookie &#x60;__Host-oc_guest_nonce_&lt;share-hash&gt;&#x60;. <br>  |
|**400** | The request body is malformed or the nonce cookie is missing. |  -  |
|**401** | The nonce or the PIN is invalid or has expired. |  -  |
|**404** | The guest link record or the referenced share could not be found. |  -  |
|**410** | The referenced share has expired. |  -  |
|**429** | Too many failed PIN attempts; the endpoint is rate limited. |  * Retry-After - Number of seconds to wait before retrying. <br>  |
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
|**200** | Success |  * Set-Cookie - Sets the guest session cookie &#x60;__Host-oc_guest_session&#x60; and clears the per-share nonce cookie &#x60;__Host-oc_guest_nonce_&lt;share-hash&gt;&#x60;. <br>  |
|**400** | The request body is malformed. |  -  |
|**401** | The token is invalid or has expired. |  -  |
|**404** | The token or the referenced share could not be found. |  -  |
|**409** | The token has already been redeemed. |  -  |
|**410** | The referenced share has expired. |  -  |
|**500** | An internal error occurred. |  -  |
|**0** | error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

