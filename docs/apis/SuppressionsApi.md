# Lockally.SDK.Api.SuppressionsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateSuppression**](SuppressionsApi.md#createsuppression) | **POST** /v1/suppressions | Add a suppression |
| [**DeleteSuppression**](SuppressionsApi.md#deletesuppression) | **DELETE** /v1/suppressions/{email} | Remove a suppression |
| [**GetSuppression**](SuppressionsApi.md#getsuppression) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed |
| [**ListSuppressions**](SuppressionsApi.md#listsuppressions) | **GET** /v1/suppressions | List suppressed recipients |

<a id="createsuppression"></a>
# **CreateSuppression**
> Suppression CreateSuppression (CreateSuppressionRequest createSuppressionRequest)

Add a suppression


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createSuppressionRequest** | [**CreateSuppressionRequest**](CreateSuppressionRequest.md) |  |  |

### Return type

[**Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Added. |  -  |
| **400** | Malformed request. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletesuppression"></a>
# **DeleteSuppression**
> void DeleteSuppression (string email)

Remove a suppression


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

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
| **204** | Removed. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsuppression"></a>
# **GetSuppression**
> Suppression GetSuppression (string email)

Check whether an address is suppressed


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

[**Suppression**](Suppression.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Suppressed. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listsuppressions"></a>
# **ListSuppressions**
> ListSuppressions200Response ListSuppressions (string reason = null, string cursor = null, int limit = null)

List suppressed recipients


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **reason** | **string** |  | [optional]  |
| **cursor** | **string** |  | [optional]  |
| **limit** | **int** |  | [optional] [default to 50] |

### Return type

[**ListSuppressions200Response**](ListSuppressions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Suppressions. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

