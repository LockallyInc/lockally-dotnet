# Lockally.SDK.Api.DirectoryApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetDirectoryActivity**](DirectoryApi.md#getdirectoryactivity) | **GET** /v1/directory-activity | Get recent directory activity |
| [**GetDirectoryPermissions**](DirectoryApi.md#getdirectorypermissions) | **GET** /v1/directory-permissions | Get directory permission settings |
| [**GetDirectoryStats**](DirectoryApi.md#getdirectorystats) | **GET** /v1/directory-stats | Get directory statistics |
| [**GetGALSettings**](DirectoryApi.md#getgalsettings) | **GET** /v1/gal-settings | Get Global Address List settings |
| [**RebuildGALIndex**](DirectoryApi.md#rebuildgalindex) | **POST** /v1/gal-settings/rebuild-index | Rebuild the GAL search index |
| [**SyncGAL**](DirectoryApi.md#syncgal) | **POST** /v1/gal-settings/sync | Sync GAL with external directory sources |
| [**UpdateDirectoryPermissions**](DirectoryApi.md#updatedirectorypermissions) | **PATCH** /v1/directory-permissions | Update directory permission settings |
| [**UpdateGALSettings**](DirectoryApi.md#updategalsettings) | **PATCH** /v1/gal-settings | Update GAL settings |

<a id="getdirectoryactivity"></a>
# **GetDirectoryActivity**
> GetDirectoryActivity200Response GetDirectoryActivity ()

Get recent directory activity


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetDirectoryActivity200Response**](GetDirectoryActivity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recent directory activity |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getdirectorypermissions"></a>
# **GetDirectoryPermissions**
> DirectoryPermissions GetDirectoryPermissions ()

Get directory permission settings


### Parameters
This endpoint does not need any parameter.
### Return type

[**DirectoryPermissions**](DirectoryPermissions.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Directory permissions |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getdirectorystats"></a>
# **GetDirectoryStats**
> GetDirectoryStats200Response GetDirectoryStats ()

Get directory statistics


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetDirectoryStats200Response**](GetDirectoryStats200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Directory statistics |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getgalsettings"></a>
# **GetGALSettings**
> GALSettings GetGALSettings ()

Get Global Address List settings


### Parameters
This endpoint does not need any parameter.
### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | GAL settings |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="rebuildgalindex"></a>
# **RebuildGALIndex**
> GALSettings RebuildGALIndex ()

Rebuild the GAL search index


### Parameters
This endpoint does not need any parameter.
### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | GAL settings after index rebuild |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="syncgal"></a>
# **SyncGAL**
> GALSettings SyncGAL ()

Sync GAL with external directory sources


### Parameters
This endpoint does not need any parameter.
### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | GAL settings after sync |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatedirectorypermissions"></a>
# **UpdateDirectoryPermissions**
> DirectoryPermissions UpdateDirectoryPermissions (UpdateDirectoryPermissionsRequest updateDirectoryPermissionsRequest)

Update directory permission settings


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateDirectoryPermissionsRequest** | [**UpdateDirectoryPermissionsRequest**](UpdateDirectoryPermissionsRequest.md) |  |  |

### Return type

[**DirectoryPermissions**](DirectoryPermissions.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Directory permissions updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updategalsettings"></a>
# **UpdateGALSettings**
> GALSettings UpdateGALSettings (UpdateGALSettingsRequest updateGALSettingsRequest)

Update GAL settings


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateGALSettingsRequest** | [**UpdateGALSettingsRequest**](UpdateGALSettingsRequest.md) |  |  |

### Return type

[**GALSettings**](GALSettings.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | GAL settings updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

