# Lockally.SDK.Api.SignupApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**Signup**](SignupApi.md#signup) | **POST** /v1/signup | Sign up a new tenant |

<a id="signup"></a>
# **Signup**
> V1AdminLoginPost200Response Signup (SignupRequest signupRequest)

Sign up a new tenant


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **signupRequest** | [**SignupRequest**](SignupRequest.md) |  |  |

### Return type

[**V1AdminLoginPost200Response**](V1AdminLoginPost200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Tenant created with initial admin and API token. |  -  |
| **400** | Malformed request. |  -  |
| **409** | Slug or email already taken. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

