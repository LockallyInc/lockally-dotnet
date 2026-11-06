# Lockally.SDK.Api.ApiKeysApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateApiKey**](ApiKeysApi.md#createapikey) | **POST** /v1/api-keys | Create an API key |
| [**ListApiKeys**](ApiKeysApi.md#listapikeys) | **GET** /v1/api-keys | List API keys |
| [**RevokeApiKey**](ApiKeysApi.md#revokeapikey) | **DELETE** /v1/api-keys/{id} | Revoke an API key |
| [**RotateApiKey**](ApiKeysApi.md#rotateapikey) | **POST** /v1/api-keys/{id}/rotate | Rotate an API key |
| [**UpdateApiKey**](ApiKeysApi.md#updateapikey) | **PATCH** /v1/api-keys/{id} | Update an API key |

<a id="createapikey"></a>
# **CreateApiKey**
> CreateApiKey201Response CreateApiKey (CreateApiKeyRequest createApiKeyRequest)

Create an API key

Provisions a fresh API key for the calling tenant.  **The full `secret` is included in this response ONLY**, store it immediately. The cleartext secret is not recoverable from the argon2id hash kept server-side; rotate by creating a new key and revoking the old one. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createApiKeyRequest** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md) |  |  |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Key created, &#x60;secret&#x60; is in the response and shown only here. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listapikeys"></a>
# **ListApiKeys**
> ListApiKeys200Response ListApiKeys (string sort = null, string order = null)

List API keys

Returns all API keys (active and revoked) belonging to the calling tenant. The `secret` is **never** returned, only prefix + metadata. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **sort** | **string** | Field to order by. This list holds tens of rows per account, so every column is offered and none needs an index. | [optional] [default to created_at] |
| **order** | **string** | Defaults to desc for the default field and asc for any other. Always tie-broken on id, so the order is total. | [optional]  |

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)

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

<a id="revokeapikey"></a>
# **RevokeApiKey**
> void RevokeApiKey (Guid id)

Revoke an API key

Soft-deletes (sets `revoked_at`) on the named key. The row stays for audit purposes; the key no longer authenticates.  You **cannot revoke the key currently being used** to make this call, that would lock you out. Use a different `tenant:admin` key. 


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
| **409** | Refused, key is the one in use for this request. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="rotateapikey"></a>
# **RotateApiKey**
> CreateApiKey201Response RotateApiKey (Guid id, RotateApiKeyRequest rotateApiKeyRequest = null)

Rotate an API key

Issues a successor key and puts a short expiry on this one, so **both work until the overlap ends**. That window is the point: without it, rotation is revocation with extra steps and every caller has to swap credentials in the same instant.  The successor inherits this key's scopes, its label (the label names the integration, and the integration has not changed) and its test flag. Its full `secret` is in this response and nowhere else.  The response's `expires_at` is the **predecessor's** deadline, so you can see from the rotation itself how long you have to cut over.  A key that has already been rotated cannot be rotated again: chaining overlaps would leave several live keys for one integration, which is the opposite of the intent. Rotate the successor instead. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **rotateApiKeyRequest** | [**RotateApiKeyRequest**](RotateApiKeyRequest.md) |  | [optional]  |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The successor key. Its &#x60;secret&#x60; is shown only here; &#x60;expires_at&#x60; is the predecessor&#39;s deadline. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | The key is revoked, or was already rotated. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateapikey"></a>
# **UpdateApiKey**
> APIKey UpdateApiKey (Guid id, UpdateApiKeyRequest updateApiKeyRequest)

Update an API key

Changes a key's label, scopes or expiry in place, without reissuing the secret.  **Every field is optional and absent means unchanged.** Renaming a key does not clear its expiry. For `expires_at` there are three distinct requests: omit the field to leave the expiry alone, send a timestamp to set one, and send an explicit `null` to remove one.  Scopes are replaced wholesale, not merged. This endpoint does not restrict which scopes you may grant, because `POST /v1/api-keys` never has either: a key with `tenant:admin` can already mint a key with any scope, so `tenant:admin` is root-equivalent for key management.  A revoked key cannot be updated. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **updateApiKeyRequest** | [**UpdateApiKeyRequest**](UpdateApiKeyRequest.md) |  |  |

### Return type

[**APIKey**](APIKey.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated key. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | The key is revoked and cannot be changed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

