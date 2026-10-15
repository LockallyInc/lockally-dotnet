# Lockally.SDK.Api.TemplatesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTemplate**](TemplatesApi.md#createtemplate) | **POST** /v1/templates | Create a template |
| [**DeleteTemplate**](TemplatesApi.md#deletetemplate) | **DELETE** /v1/templates/{id} | Delete a template |
| [**GetTemplate**](TemplatesApi.md#gettemplate) | **GET** /v1/templates/{id} | Get a template |
| [**ListTemplates**](TemplatesApi.md#listtemplates) | **GET** /v1/templates | List templates |
| [**UpdateTemplate**](TemplatesApi.md#updatetemplate) | **PUT** /v1/templates/{id} | Update a template |

<a id="createtemplate"></a>
# **CreateTemplate**
> Template CreateTemplate (TemplateInput templateInput)

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

<a id="deletetemplate"></a>
# **DeleteTemplate**
> void DeleteTemplate (Guid id)

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

<a id="gettemplate"></a>
# **GetTemplate**
> Template GetTemplate (Guid id)

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

<a id="listtemplates"></a>
# **ListTemplates**
> ListTemplates200Response ListTemplates ()

List templates


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListTemplates200Response**](ListTemplates200Response.md)

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

<a id="updatetemplate"></a>
# **UpdateTemplate**
> Template UpdateTemplate (Guid id, TemplateInput templateInput)

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

