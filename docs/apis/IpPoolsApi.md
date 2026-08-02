# Lockally.SDK.Api.IpPoolsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDedicatedIPRequest**](IpPoolsApi.md#creatededicatediprequest) | **POST** /v1/dedicated-ip-requests | Request a dedicated IP |
| [**GetIPAssignment**](IpPoolsApi.md#getipassignment) | **GET** /v1/ip-assignment | Get current IP assignment |
| [**ListDedicatedIPRequests**](IpPoolsApi.md#listdedicatediprequests) | **GET** /v1/dedicated-ip-requests | List dedicated IP requests |

<a id="creatededicatediprequest"></a>
# **CreateDedicatedIPRequest**
> DedicatedIPRequest CreateDedicatedIPRequest (CreateDedicatedIPRequestRequest createDedicatedIPRequestRequest)

Request a dedicated IP


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createDedicatedIPRequestRequest** | [**CreateDedicatedIPRequestRequest**](CreateDedicatedIPRequestRequest.md) |  |  |

### Return type

[**DedicatedIPRequest**](DedicatedIPRequest.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Dedicated IP request submitted. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | A pending request already exists. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getipassignment"></a>
# **GetIPAssignment**
> GetIPAssignment200Response GetIPAssignment ()

Get current IP assignment


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetIPAssignment200Response**](GetIPAssignment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The tenant&#39;s current outbound IP assignment. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listdedicatediprequests"></a>
# **ListDedicatedIPRequests**
> ListDedicatedIPRequests200Response ListDedicatedIPRequests ()

List dedicated IP requests


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListDedicatedIPRequests200Response**](ListDedicatedIPRequests200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Dedicated IP request history. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

