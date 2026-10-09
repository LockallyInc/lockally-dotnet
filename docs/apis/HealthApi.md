# Lockally.SDK.Api.HealthApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**HealthzGet**](HealthApi.md#healthzget) | **GET** /healthz | Liveness check |

<a id="healthzget"></a>
# **HealthzGet**
> HealthzGet200Response HealthzGet ()

Liveness check

Returns 200 if the process is up and the database pings cleanly. No authentication required.


### Parameters
This endpoint does not need any parameter.
### Return type

[**HealthzGet200Response**](HealthzGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Healthy |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

