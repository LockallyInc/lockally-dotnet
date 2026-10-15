# Lockally.SDK.Api.DistributionListsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDistributionList**](DistributionListsApi.md#createdistributionlist) | **POST** /v1/distribution-lists | Create a distribution list |
| [**DeleteDistributionList**](DistributionListsApi.md#deletedistributionlist) | **DELETE** /v1/distribution-lists/{address} | Delete a distribution list |
| [**GetDistributionList**](DistributionListsApi.md#getdistributionlist) | **GET** /v1/distribution-lists/{address} | Get a distribution list |
| [**ListDistributionLists**](DistributionListsApi.md#listdistributionlists) | **GET** /v1/distribution-lists | List distribution lists |
| [**ReplaceDistributionListMembers**](DistributionListsApi.md#replacedistributionlistmembers) | **PUT** /v1/distribution-lists/{address}/members | Replace distribution list members |

<a id="createdistributionlist"></a>
# **CreateDistributionList**
> DistributionListDetail CreateDistributionList (CreateDistributionListRequest createDistributionListRequest)

Create a distribution list


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createDistributionListRequest** | [**CreateDistributionListRequest**](CreateDistributionListRequest.md) |  |  |

### Return type

[**DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Distribution list created. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | List address already exists. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletedistributionlist"></a>
# **DeleteDistributionList**
> void DeleteDistributionList (string address)

Delete a distribution list


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **address** | **string** | Distribution list email address |  |

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

<a id="getdistributionlist"></a>
# **GetDistributionList**
> DistributionListDetail GetDistributionList (string address)

Get a distribution list


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **address** | **string** | Distribution list email address |  |

### Return type

[**DistributionListDetail**](DistributionListDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Distribution list with full member list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listdistributionlists"></a>
# **ListDistributionLists**
> ListDistributionLists200Response ListDistributionLists ()

List distribution lists


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListDistributionLists200Response**](ListDistributionLists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | All distribution lists for the tenant. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="replacedistributionlistmembers"></a>
# **ReplaceDistributionListMembers**
> ReplaceDistributionListMembers200Response ReplaceDistributionListMembers (string address, ReplaceDistributionListMembersRequest replaceDistributionListMembersRequest)

Replace distribution list members


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **address** | **string** | Distribution list email address |  |
| **replaceDistributionListMembersRequest** | [**ReplaceDistributionListMembersRequest**](ReplaceDistributionListMembersRequest.md) |  |  |

### Return type

[**ReplaceDistributionListMembers200Response**](ReplaceDistributionListMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated member list. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

