# Lockally.SDK.Api.EncryptionApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchLookupPublicKeys**](EncryptionApi.md#batchlookuppublickeys) | **GET** /v1/encryption/keys/lookup | Batch-lookup public keys by email |
| [**CreateEncryptionKey**](EncryptionApi.md#createencryptionkey) | **POST** /v1/encryption/keys | Upload an encryption key pair |
| [**CreateEncryptionRecovery**](EncryptionApi.md#createencryptionrecovery) | **POST** /v1/encryption/recovery | Store an encryption recovery blob |
| [**GetEncryptionKey**](EncryptionApi.md#getencryptionkey) | **GET** /v1/encryption/keys/{email} | Get encryption key for a mailbox |
| [**RotateEncryptionKey**](EncryptionApi.md#rotateencryptionkey) | **POST** /v1/encryption/keys/rotate | Rotate an encryption key |

<a id="batchlookuppublickeys"></a>
# **BatchLookupPublicKeys**
> BatchLookupPublicKeys200Response BatchLookupPublicKeys (string emails)

Batch-lookup public keys by email


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **emails** | **string** | Comma-separated list of email addresses |  |

### Return type

[**BatchLookupPublicKeys200Response**](BatchLookupPublicKeys200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Public keys for requested emails |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createencryptionkey"></a>
# **CreateEncryptionKey**
> CreateEncryptionKey201Response CreateEncryptionKey (CreateEncryptionKeyRequest createEncryptionKeyRequest)

Upload an encryption key pair


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createEncryptionKeyRequest** | [**CreateEncryptionKeyRequest**](CreateEncryptionKeyRequest.md) |  |  |

### Return type

[**CreateEncryptionKey201Response**](CreateEncryptionKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Key pair stored |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createencryptionrecovery"></a>
# **CreateEncryptionRecovery**
> void CreateEncryptionRecovery (CreateEncryptionRecoveryRequest createEncryptionRecoveryRequest)

Store an encryption recovery blob


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createEncryptionRecoveryRequest** | [**CreateEncryptionRecoveryRequest**](CreateEncryptionRecoveryRequest.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Recovery blob stored |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getencryptionkey"></a>
# **GetEncryptionKey**
> GetEncryptionKey200Response GetEncryptionKey (string email)

Get encryption key for a mailbox


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

[**GetEncryptionKey200Response**](GetEncryptionKey200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Encryption key details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="rotateencryptionkey"></a>
# **RotateEncryptionKey**
> void RotateEncryptionKey (RotateEncryptionKeyRequest rotateEncryptionKeyRequest)

Rotate an encryption key


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **rotateEncryptionKeyRequest** | [**RotateEncryptionKeyRequest**](RotateEncryptionKeyRequest.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Key rotated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

