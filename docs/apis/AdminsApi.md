# Lockally.SDK.Api.AdminsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1AdminsGet**](AdminsApi.md#v1adminsget) | **GET** /v1/admins | List tenant admins |
| [**V1AdminsIdDelete**](AdminsApi.md#v1adminsiddelete) | **DELETE** /v1/admins/{id} | Delete an admin |
| [**V1AdminsIdPatch**](AdminsApi.md#v1adminsidpatch) | **PATCH** /v1/admins/{id} | Update an admin |
| [**V1AdminsPost**](AdminsApi.md#v1adminspost) | **POST** /v1/admins | Invite a new admin |

<a id="v1adminsget"></a>
# **V1AdminsGet**
> V1AdminsGet200Response V1AdminsGet ()

List tenant admins


### Parameters
This endpoint does not need any parameter.
### Return type

[**V1AdminsGet200Response**](V1AdminsGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Admin list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1adminsiddelete"></a>
# **V1AdminsIdDelete**
> void V1AdminsIdDelete (Guid id)

Delete an admin

Hard-delete. Cascade-drops the admin's sessions (immediate revocation). Same safety rails as PATCH disabled=true. 


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
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Self-delete on session bearer, or last-admin safeguard. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1adminsidpatch"></a>
# **V1AdminsIdPatch**
> AdminFull V1AdminsIdPatch (Guid id, V1AdminsIdPatchRequest v1AdminsIdPatchRequest)

Update an admin

Supply at least one of `password`, `display_name`, `role`, `disabled`.  **Safety rails.** A session bearer (adm_sess_*) cannot disable itself — use another admin or an API key (which bypasses the self-rail). Disabling the last active admin returns 409 to prevent orphaning the tenant from its console. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **v1AdminsIdPatchRequest** | [**V1AdminsIdPatchRequest**](V1AdminsIdPatchRequest.md) |  |  |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated admin. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Self-disable on session bearer, or last-admin safeguard. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1adminspost"></a>
# **V1AdminsPost**
> AdminFull V1AdminsPost (V1AdminsPostRequest v1AdminsPostRequest)

Invite a new admin

Creates a new tenant admin. If `password` is omitted, lockally generates a 16-char password and returns it ONCE in the response. Email is case-insensitive and unique per tenant. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **v1AdminsPostRequest** | [**V1AdminsPostRequest**](V1AdminsPostRequest.md) |  |  |

### Return type

[**AdminFull**](AdminFull.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. &#x60;password&#x60; populated ONLY if generated. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Email already an admin on this tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

