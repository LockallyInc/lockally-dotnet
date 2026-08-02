# Lockally.SDK.Api.AliasesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1AliasesAddressDelete**](AliasesApi.md#v1aliasesaddressdelete) | **DELETE** /v1/aliases/{address} | Delete an alias |
| [**V1AliasesGet**](AliasesApi.md#v1aliasesget) | **GET** /v1/aliases | List aliases |
| [**V1AliasesPost**](AliasesApi.md#v1aliasespost) | **POST** /v1/aliases | Create an alias |

<a id="v1aliasesaddressdelete"></a>
# **V1AliasesAddressDelete**
> void V1AliasesAddressDelete (string address)

Delete an alias

Hard-delete (no soft-delete window — aliases are cheap to recreate).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **address** | **string** |  |  |

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
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1aliasesget"></a>
# **V1AliasesGet**
> V1AliasesGet200Response V1AliasesGet ()

List aliases


### Parameters
This endpoint does not need any parameter.
### Return type

[**V1AliasesGet200Response**](V1AliasesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Alias list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1aliasespost"></a>
# **V1AliasesPost**
> Alias V1AliasesPost (V1AliasesPostRequest v1AliasesPostRequest)

Create an alias

Creates an email alias. `alias_address` must be on a verified tenant-owned domain. `alias_target` can be any email — intra-tenant or external (forwarding to a Gmail account is a legitimate use). 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **v1AliasesPostRequest** | [**V1AliasesPostRequest**](V1AliasesPostRequest.md) |  |  |

### Return type

[**Alias**](Alias.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Alias created. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Alias address already exists. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

