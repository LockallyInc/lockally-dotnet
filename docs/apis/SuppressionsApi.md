# Lockally.SDK.Api.SuppressionsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1SuppressionsEmailDelete**](SuppressionsApi.md#v1suppressionsemaildelete) | **DELETE** /v1/suppressions/{email} | Remove a suppression |
| [**V1SuppressionsEmailGet**](SuppressionsApi.md#v1suppressionsemailget) | **GET** /v1/suppressions/{email} | Check whether an address is suppressed |
| [**V1SuppressionsGet**](SuppressionsApi.md#v1suppressionsget) | **GET** /v1/suppressions | List suppressed recipients |
| [**V1SuppressionsPost**](SuppressionsApi.md#v1suppressionspost) | **POST** /v1/suppressions | Add a suppression |

<a id="v1suppressionsemaildelete"></a>
# **V1SuppressionsEmailDelete**
> void V1SuppressionsEmailDelete (string email)

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

<a id="v1suppressionsemailget"></a>
# **V1SuppressionsEmailGet**
> Suppression V1SuppressionsEmailGet (string email)

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

<a id="v1suppressionsget"></a>
# **V1SuppressionsGet**
> V1SuppressionsGet200Response V1SuppressionsGet (string reason = null, string cursor = null, int limit = null)

List suppressed recipients


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **reason** | **string** |  | [optional]  |
| **cursor** | **string** |  | [optional]  |
| **limit** | **int** |  | [optional] [default to 50] |

### Return type

[**V1SuppressionsGet200Response**](V1SuppressionsGet200Response.md)

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

<a id="v1suppressionspost"></a>
# **V1SuppressionsPost**
> Suppression V1SuppressionsPost (V1SuppressionsPostRequest v1SuppressionsPostRequest)

Add a suppression


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **v1SuppressionsPostRequest** | [**V1SuppressionsPostRequest**](V1SuppressionsPostRequest.md) |  |  |

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

