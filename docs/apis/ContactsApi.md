# Lockally.SDK.Api.ContactsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkUpsertExternalContacts**](ContactsApi.md#bulkupsertexternalcontacts) | **PUT** /v1/contacts/external/{system} | Create or update up to 500 contacts by their ids in another system |
| [**CreateContact**](ContactsApi.md#createcontact) | **POST** /v1/contacts | Create a contact |
| [**DeleteContact**](ContactsApi.md#deletecontact) | **DELETE** /v1/contacts/{id} | Delete a contact |
| [**DeleteExternalContact**](ContactsApi.md#deleteexternalcontact) | **DELETE** /v1/contacts/external/{system}/{external_id} | Delete a contact by its id in another system |
| [**GetContact**](ContactsApi.md#getcontact) | **GET** /v1/contacts/{id} | Get a contact |
| [**GetContactLists**](ContactsApi.md#getcontactlists) | **GET** /v1/contacts/{id}/lists | Get lists a contact belongs to |
| [**GetExternalContact**](ContactsApi.md#getexternalcontact) | **GET** /v1/contacts/external/{system}/{external_id} | Get a contact by its id in another system |
| [**ListContacts**](ContactsApi.md#listcontacts) | **GET** /v1/contacts | List contacts |
| [**UpdateContact**](ContactsApi.md#updatecontact) | **PATCH** /v1/contacts/{id} | Update a contact |
| [**UpsertExternalContact**](ContactsApi.md#upsertexternalcontact) | **PUT** /v1/contacts/external/{system}/{external_id} | Create or update a contact by its id in another system |

<a id="bulkupsertexternalcontacts"></a>
# **BulkUpsertExternalContacts**
> BulkUpsertExternalContacts200Response BulkUpsertExternalContacts (string varSystem, BulkUpsertExternalContactsRequest bulkUpsertExternalContactsRequest)

Create or update up to 500 contacts by their ids in another system

For a sync. Each row stands alone: a bad row is reported in `results` with its index and the rest are stored, so the response is 200 whenever the request itself is well formed. Read `failed` and `results`. Two rows with the same `external_id` in one request are refused (the later one), because which is current cannot be known. Rerunning the same payload updates rather than duplicates.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **varSystem** | **string** |  |  |
| **bulkUpsertExternalContactsRequest** | [**BulkUpsertExternalContactsRequest**](BulkUpsertExternalContactsRequest.md) |  |  |

### Return type

[**BulkUpsertExternalContacts200Response**](BulkUpsertExternalContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-row results |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createcontact"></a>
# **CreateContact**
> Contact CreateContact (CreateContactRequest createContactRequest)

Create a contact


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createContactRequest** | [**CreateContactRequest**](CreateContactRequest.md) |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Contact created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletecontact"></a>
# **DeleteContact**
> void DeleteContact (Guid id)

Delete a contact


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
| **204** | Contact deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deleteexternalcontact"></a>
# **DeleteExternalContact**
> void DeleteExternalContact (string varSystem, string externalId)

Delete a contact by its id in another system


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **varSystem** | **string** | Your label for the system the record comes from, for example &#x60;salesforce&#x60;, &#x60;hubspot&#x60; or &#x60;odoo&#x60;. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). |  |
| **externalId** | **string** | The record&#39;s id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. |  |

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
| **204** | Contact deleted |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getcontact"></a>
# **GetContact**
> Contact GetContact (Guid id)

Get a contact


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getcontactlists"></a>
# **GetContactLists**
> GetContactLists200Response GetContactLists (Guid id)

Get lists a contact belongs to


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**GetContactLists200Response**](GetContactLists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Lists containing this contact |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getexternalcontact"></a>
# **GetExternalContact**
> Contact GetExternalContact (string varSystem, string externalId)

Get a contact by its id in another system


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **varSystem** | **string** | Your label for the system the record comes from, for example &#x60;salesforce&#x60;, &#x60;hubspot&#x60; or &#x60;odoo&#x60;. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). |  |
| **externalId** | **string** | The record&#39;s id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcontacts"></a>
# **ListContacts**
> ListContacts200Response ListContacts (string q = null, string type = null, string department = null, string status = null, string source = null)

List contacts


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **q** | **string** | Free-text search across name, email, company | [optional]  |
| **type** | **string** | Filter by contact_type | [optional]  |
| **department** | **string** | Filter by department | [optional]  |
| **status** | **string** | Filter by status | [optional]  |
| **source** | **string** | Filter by source | [optional]  |

### Return type

[**ListContacts200Response**](ListContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of contacts |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatecontact"></a>
# **UpdateContact**
> Contact UpdateContact (Guid id, UpdateContactRequest updateContactRequest)

Update a contact


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **updateContactRequest** | [**UpdateContactRequest**](UpdateContactRequest.md) |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="upsertexternalcontact"></a>
# **UpsertExternalContact**
> Contact UpsertExternalContact (string varSystem, string externalId, ExternalContactInput externalContactInput)

Create or update a contact by its id in another system

Idempotent: the path is the identity, so sending the same request twice cannot create a second contact, and you never need to store our id. Returns 201 when the contact was created and 200 when it already existed. The body is the full representation: a field you leave out is cleared. Email is an ordinary attribute, not a key, so changing it updates the same contact. `mailboxes:write` is also accepted.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **varSystem** | **string** | Your label for the system the record comes from, for example &#x60;salesforce&#x60;, &#x60;hubspot&#x60; or &#x60;odoo&#x60;. 1 to 64 characters: lowercase letters, digits, dot, underscore or hyphen (upper case is folded). |  |
| **externalId** | **string** | The record&#39;s id in that system, kept exactly as given (case matters). 1 to 255 characters, no spaces. URL-encode it. |  |
| **externalContactInput** | [**ExternalContactInput**](ExternalContactInput.md) |  |  |

### Return type

[**Contact**](Contact.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The contact already existed and was updated |  -  |
| **201** | The contact was created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

