# Lockally.SDK.Api.DashboardApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAuditSummary**](DashboardApi.md#getauditsummary) | **GET** /v1/audit-summary | Audit summary for the dashboard |
| [**GetDomainsStatus**](DashboardApi.md#getdomainsstatus) | **GET** /v1/domains/status | Domain health status for the dashboard |
| [**GetIntegrationsSummary**](DashboardApi.md#getintegrationssummary) | **GET** /v1/integrations-summary | Integrations summary for the dashboard |
| [**GetSecurity**](DashboardApi.md#getsecurity) | **GET** /v1/security | Security overview for the dashboard |
| [**GetStorage**](DashboardApi.md#getstorage) | **GET** /v1/storage | Storage usage for the dashboard |
| [**GetTenantHealth**](DashboardApi.md#gettenanthealth) | **GET** /v1/health | Full tenant health report |
| [**GetUserInsights**](DashboardApi.md#getuserinsights) | **GET** /v1/user-insights | User insights for the dashboard |

<a id="getauditsummary"></a>
# **GetAuditSummary**
> GetAuditSummary200Response GetAuditSummary ()

Audit summary for the dashboard


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetAuditSummary200Response**](GetAuditSummary200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Audit summary |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getdomainsstatus"></a>
# **GetDomainsStatus**
> GetDomainsStatus200Response GetDomainsStatus ()

Domain health status for the dashboard


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetDomainsStatus200Response**](GetDomainsStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Domain health status |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getintegrationssummary"></a>
# **GetIntegrationsSummary**
> GetIntegrationsSummary200Response GetIntegrationsSummary ()

Integrations summary for the dashboard


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetIntegrationsSummary200Response**](GetIntegrationsSummary200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Integrations summary |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsecurity"></a>
# **GetSecurity**
> GetSecurity200Response GetSecurity ()

Security overview for the dashboard


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetSecurity200Response**](GetSecurity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Security overview |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getstorage"></a>
# **GetStorage**
> GetStorage200Response GetStorage ()

Storage usage for the dashboard


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetStorage200Response**](GetStorage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Storage usage |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="gettenanthealth"></a>
# **GetTenantHealth**
> Object GetTenantHealth ()

Full tenant health report


### Parameters
This endpoint does not need any parameter.
### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Full tenant health report |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getuserinsights"></a>
# **GetUserInsights**
> GetUserInsights200Response GetUserInsights ()

User insights for the dashboard


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetUserInsights200Response**](GetUserInsights200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User insights |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

