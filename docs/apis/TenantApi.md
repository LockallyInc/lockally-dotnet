# Lockally.SDK.Api.TenantApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetTenant**](TenantApi.md#gettenant) | **GET** /v1/tenant | Get the calling tenant |
| [**GetUsage**](TenantApi.md#getusage) | **GET** /v1/usage | Usage snapshot |

<a id="gettenant"></a>
# **GetTenant**
> Tenant GetTenant ()

Get the calling tenant

Returns the tenant the presented API key belongs to.


### Parameters
This endpoint does not need any parameter.
### Return type

[**Tenant**](Tenant.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tenant info |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getusage"></a>
# **GetUsage**
> GetUsage200Response GetUsage ()

Usage snapshot

Returns the tenant's current usage + cap consumption. Designed for poll-based alerting on the integrator side (e.g. \"warn when daily quota is 80% used\"). Refreshed live from Postgres — there is no cache, so callers should poll at most once per minute. 


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetUsage200Response**](GetUsage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Usage snapshot |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

