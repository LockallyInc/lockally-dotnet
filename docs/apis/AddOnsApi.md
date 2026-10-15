# Lockally.SDK.Api.AddOnsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ActivateAddOn**](AddOnsApi.md#activateaddon) | **POST** /v1/add-ons/{name}/activate | Activate an add-on |
| [**CancelAddOn**](AddOnsApi.md#canceladdon) | **POST** /v1/add-ons/{name}/cancel | Cancel an add-on |
| [**GetAddOnStatus**](AddOnsApi.md#getaddonstatus) | **GET** /v1/add-ons/{name} | Get add-on status |
| [**ListAddOns**](AddOnsApi.md#listaddons) | **GET** /v1/add-ons | List add-ons |

<a id="activateaddon"></a>
# **ActivateAddOn**
> ActivateAddOn200Response ActivateAddOn (string name)

Activate an add-on


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **name** | **string** | Add-on key |  |

### Return type

[**ActivateAddOn200Response**](ActivateAddOn200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Add-on activated. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="canceladdon"></a>
# **CancelAddOn**
> void CancelAddOn (string name)

Cancel an add-on


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **name** | **string** | Add-on key |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getaddonstatus"></a>
# **GetAddOnStatus**
> GetAddOnStatus200Response GetAddOnStatus (string name)

Get add-on status


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **name** | **string** | Add-on key |  |

### Return type

[**GetAddOnStatus200Response**](GetAddOnStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Add-on eligibility and activation state. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listaddons"></a>
# **ListAddOns**
> ListAddOns200Response ListAddOns ()

List add-ons


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListAddOns200Response**](ListAddOns200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Available add-ons and their activation state. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

