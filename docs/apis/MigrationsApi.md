# Lockally.SDK.Api.MigrationsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelMigration**](MigrationsApi.md#cancelmigration) | **POST** /v1/migrations/{id}/cancel | Cancel a running migration |
| [**CheckMigrationDNS**](MigrationsApi.md#checkmigrationdns) | **GET** /v1/migrations/{id}/dns-check | Check DNS readiness for cutover |
| [**CreateMigration**](MigrationsApi.md#createmigration) | **POST** /v1/migrations | Create a migration |
| [**CreateMigrationCredential**](MigrationsApi.md#createmigrationcredential) | **POST** /v1/migrations/credentials | Store a migration credential |
| [**DeleteMigration**](MigrationsApi.md#deletemigration) | **DELETE** /v1/migrations/{id} | Delete a migration |
| [**DeleteMigrationCredential**](MigrationsApi.md#deletemigrationcredential) | **DELETE** /v1/migrations/credentials/{id} | Delete a migration credential |
| [**DeltaSyncMigration**](MigrationsApi.md#deltasyncmigration) | **POST** /v1/migrations/{id}/delta-sync | Run a delta sync |
| [**DiscoverMigration**](MigrationsApi.md#discovermigration) | **POST** /v1/migrations/{id}/discover | Discover source mailboxes |
| [**FinalSyncMigration**](MigrationsApi.md#finalsyncmigration) | **POST** /v1/migrations/{id}/final-sync | Run the final sync before cutover |
| [**GetMigration**](MigrationsApi.md#getmigration) | **GET** /v1/migrations/{id} | Get a migration |
| [**GetMigrationProgress**](MigrationsApi.md#getmigrationprogress) | **GET** /v1/migrations/{id}/progress | Get migration progress |
| [**ListMigrationCredentials**](MigrationsApi.md#listmigrationcredentials) | **GET** /v1/migrations/credentials | List migration credentials |
| [**ListMigrationEvents**](MigrationsApi.md#listmigrationevents) | **GET** /v1/migrations/{id}/events | List migration events |
| [**ListMigrationMailboxes**](MigrationsApi.md#listmigrationmailboxes) | **GET** /v1/migrations/{id}/mailboxes | List migration mailboxes |
| [**ListMigrations**](MigrationsApi.md#listmigrations) | **GET** /v1/migrations | List migrations |
| [**MapMigration**](MigrationsApi.md#mapmigration) | **POST** /v1/migrations/{id}/map | Map source to destination mailboxes |
| [**RetryMigration**](MigrationsApi.md#retrymigration) | **POST** /v1/migrations/{id}/retry | Retry a failed or cancelled migration |
| [**StartMigration**](MigrationsApi.md#startmigration) | **POST** /v1/migrations/{id}/start | Start the migration |
| [**UpdateMigration**](MigrationsApi.md#updatemigration) | **PATCH** /v1/migrations/{id} | Update a migration |
| [**UpdateMigrationMailbox**](MigrationsApi.md#updatemigrationmailbox) | **PATCH** /v1/migrations/{id}/mailboxes/{mbxId} | Update a migration mailbox |
| [**ValidateMigration**](MigrationsApi.md#validatemigration) | **POST** /v1/migrations/{id}/validate | Validate migrated data |

<a id="cancelmigration"></a>
# **CancelMigration**
> DiscoverMigration202Response CancelMigration (Guid id)

Cancel a running migration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration cancelled |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Cannot cancel migration from its current status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="checkmigrationdns"></a>
# **CheckMigrationDNS**
> Object CheckMigrationDNS (Guid id)

Check DNS readiness for cutover


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

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
| **200** | DNS readiness check results |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createmigration"></a>
# **CreateMigration**
> Migration CreateMigration (CreateMigrationRequest createMigrationRequest)

Create a migration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createMigrationRequest** | [**CreateMigrationRequest**](CreateMigrationRequest.md) |  |  |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Migration created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createmigrationcredential"></a>
# **CreateMigrationCredential**
> MigrationCredential CreateMigrationCredential (CreateMigrationCredentialRequest createMigrationCredentialRequest)

Store a migration credential


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createMigrationCredentialRequest** | [**CreateMigrationCredentialRequest**](CreateMigrationCredentialRequest.md) |  |  |

### Return type

[**MigrationCredential**](MigrationCredential.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Credential stored |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletemigration"></a>
# **DeleteMigration**
> void DeleteMigration (Guid id)

Delete a migration


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
| **204** | Migration deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Can only delete migrations in draft, completed, failed, or cancelled status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletemigrationcredential"></a>
# **DeleteMigrationCredential**
> void DeleteMigrationCredential (Guid id)

Delete a migration credential


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
| **204** | Credential deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deltasyncmigration"></a>
# **DeltaSyncMigration**
> StartMigration202Response DeltaSyncMigration (Guid id)

Run a delta sync


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Delta sync started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in staged status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="discovermigration"></a>
# **DiscoverMigration**
> DiscoverMigration202Response DiscoverMigration (Guid id)

Discover source mailboxes


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Discovery started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in draft status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="finalsyncmigration"></a>
# **FinalSyncMigration**
> StartMigration202Response FinalSyncMigration (Guid id)

Run the final sync before cutover


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Final sync started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in cutover_pending status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getmigration"></a>
# **GetMigration**
> Migration GetMigration (Guid id)

Get a migration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getmigrationprogress"></a>
# **GetMigrationProgress**
> MigrationProgress GetMigrationProgress (Guid id)

Get migration progress


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**MigrationProgress**](MigrationProgress.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration progress |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listmigrationcredentials"></a>
# **ListMigrationCredentials**
> ListMigrationCredentials200Response ListMigrationCredentials ()

List migration credentials


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListMigrationCredentials200Response**](ListMigrationCredentials200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Credential list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listmigrationevents"></a>
# **ListMigrationEvents**
> ListMigrationEvents200Response ListMigrationEvents (Guid id)

List migration events


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**ListMigrationEvents200Response**](ListMigrationEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration event list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listmigrationmailboxes"></a>
# **ListMigrationMailboxes**
> ListMigrationMailboxes200Response ListMigrationMailboxes (Guid id)

List migration mailboxes


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**ListMigrationMailboxes200Response**](ListMigrationMailboxes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration mailbox list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listmigrations"></a>
# **ListMigrations**
> ListMigrations200Response ListMigrations ()

List migrations


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListMigrations200Response**](ListMigrations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="mapmigration"></a>
# **MapMigration**
> DiscoverMigration202Response MapMigration (Guid id, MapMigrationRequest mapMigrationRequest)

Map source to destination mailboxes


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **mapMigrationRequest** | [**MapMigrationRequest**](MapMigrationRequest.md) |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mappings applied |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="retrymigration"></a>
# **RetryMigration**
> DiscoverMigration202Response RetryMigration (Guid id)

Retry a failed or cancelled migration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**DiscoverMigration202Response**](DiscoverMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration retried |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in failed or cancelled status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="startmigration"></a>
# **StartMigration**
> StartMigration202Response StartMigration (Guid id)

Start the migration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Migration started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in mapped or pilot_complete status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatemigration"></a>
# **UpdateMigration**
> Migration UpdateMigration (Guid id, UpdateMigrationRequest updateMigrationRequest)

Update a migration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **updateMigrationRequest** | [**UpdateMigrationRequest**](UpdateMigrationRequest.md) |  |  |

### Return type

[**Migration**](Migration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Migration updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatemigrationmailbox"></a>
# **UpdateMigrationMailbox**
> void UpdateMigrationMailbox (Guid id, Guid mbxId, UpdateMigrationMailboxRequest updateMigrationMailboxRequest)

Update a migration mailbox


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **mbxId** | **Guid** |  |  |
| **updateMigrationMailboxRequest** | [**UpdateMigrationMailboxRequest**](UpdateMigrationMailboxRequest.md) |  |  |

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
| **204** | Mailbox updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="validatemigration"></a>
# **ValidateMigration**
> StartMigration202Response ValidateMigration (Guid id)

Validate migrated data


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**StartMigration202Response**](StartMigration202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Validation started |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Migration is not in final_syncing status. |  -  |
| **503** | Service is temporarily unable to handle the request (e.g. database unreachable). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

