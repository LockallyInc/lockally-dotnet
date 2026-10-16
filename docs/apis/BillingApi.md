# Lockally.SDK.Api.BillingApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateBillingCheckout**](BillingApi.md#createbillingcheckout) | **POST** /v1/billing/checkout | Create a plan checkout session |
| [**CreateUnitsCheckout**](BillingApi.md#createunitscheckout) | **POST** /v1/billing/units/checkout | Create a send-units checkout session |
| [**GetBilling**](BillingApi.md#getbilling) | **GET** /v1/billing | Get billing status |

<a id="createbillingcheckout"></a>
# **CreateBillingCheckout**
> CreateBillingCheckout200Response CreateBillingCheckout (CreateBillingCheckoutRequest createBillingCheckoutRequest)

Create a plan checkout session


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createBillingCheckoutRequest** | [**CreateBillingCheckoutRequest**](CreateBillingCheckoutRequest.md) |  |  |

### Return type

[**CreateBillingCheckout200Response**](CreateBillingCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Checkout URL for payment. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createunitscheckout"></a>
# **CreateUnitsCheckout**
> CreateUnitsCheckout200Response CreateUnitsCheckout (CreateUnitsCheckoutRequest createUnitsCheckoutRequest)

Create a send-units checkout session


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createUnitsCheckoutRequest** | [**CreateUnitsCheckoutRequest**](CreateUnitsCheckoutRequest.md) |  |  |

### Return type

[**CreateUnitsCheckout200Response**](CreateUnitsCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Checkout URL for the selected unit bundle. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getbilling"></a>
# **GetBilling**
> BillingStatus GetBilling ()

Get billing status


### Parameters
This endpoint does not need any parameter.
### Return type

[**BillingStatus**](BillingStatus.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Current billing status. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

