# Lockally.SDK.Api.TemplatesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1TemplatesGet**](TemplatesApi.md#v1templatesget) | **GET** /v1/templates | List templates |
| [**V1TemplatesIdDelete**](TemplatesApi.md#v1templatesiddelete) | **DELETE** /v1/templates/{id} | Delete a template |
| [**V1TemplatesIdGet**](TemplatesApi.md#v1templatesidget) | **GET** /v1/templates/{id} | Get a template |
| [**V1TemplatesIdPut**](TemplatesApi.md#v1templatesidput) | **PUT** /v1/templates/{id} | Update a template |
| [**V1TemplatesPost**](TemplatesApi.md#v1templatespost) | **POST** /v1/templates | Create a template |

<a id="v1templatesget"></a>
# **V1TemplatesGet**
> V1TemplatesGet200Response V1TemplatesGet ()

List templates


### Parameters
This endpoint does not need any parameter.
### Return type

[**V1TemplatesGet200Response**](V1TemplatesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Templates. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1templatesiddelete"></a>
# **V1TemplatesIdDelete**
> void V1TemplatesIdDelete (Guid id)

Delete a template


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

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
| **204** | Deleted. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1templatesidget"></a>
# **V1TemplatesIdGet**
> Template V1TemplatesIdGet (Guid id)

Get a template


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Template. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1templatesidput"></a>
# **V1TemplatesIdPut**
> Template V1TemplatesIdPut (Guid id, TemplateInput templateInput)

Update a template


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **templateInput** | [**TemplateInput**](TemplateInput.md) |  |  |

### Return type

[**Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated. |  -  |
| **400** | Malformed request. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1templatespost"></a>
# **V1TemplatesPost**
> Template V1TemplatesPost (TemplateInput templateInput)

Create a template


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **templateInput** | [**TemplateInput**](TemplateInput.md) |  |  |

### Return type

[**Template**](Template.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

