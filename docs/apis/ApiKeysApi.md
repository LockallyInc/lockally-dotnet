# Lockally.SDK.Api.ApiKeysApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1ApiKeysGet**](ApiKeysApi.md#v1apikeysget) | **GET** /v1/api-keys | List API keys |
| [**V1ApiKeysIdDelete**](ApiKeysApi.md#v1apikeysiddelete) | **DELETE** /v1/api-keys/{id} | Revoke an API key |
| [**V1ApiKeysPost**](ApiKeysApi.md#v1apikeyspost) | **POST** /v1/api-keys | Create an API key |

<a id="v1apikeysget"></a>
# **V1ApiKeysGet**
> V1ApiKeysGet200Response V1ApiKeysGet ()

List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The `secret` is **never** returned — only prefix + metadata. 


### Parameters
This endpoint does not need any parameter.
### Return type

[**V1ApiKeysGet200Response**](V1ApiKeysGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Key list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1apikeysiddelete"></a>
# **V1ApiKeysIdDelete**
> void V1ApiKeysIdDelete (Guid id)

Revoke an API key

Soft-deletes (sets `revoked_at`) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call — that would lock you out. Use a different `tenant:admin` key. 


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
| **204** | Revoked. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Refused — key is the one in use for this request. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1apikeyspost"></a>
# **V1ApiKeysPost**
> V1ApiKeysPost201Response V1ApiKeysPost (V1ApiKeysPostRequest v1ApiKeysPostRequest)

Create an API key

Provisions a fresh API key for the calling tenant.  **The full `secret` is included in this response ONLY** — store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **v1ApiKeysPostRequest** | [**V1ApiKeysPostRequest**](V1ApiKeysPostRequest.md) |  |  |

### Return type

[**V1ApiKeysPost201Response**](V1ApiKeysPost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Key created — &#x60;secret&#x60; is in the response and shown only here. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

