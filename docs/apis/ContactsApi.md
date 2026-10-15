# Lockally.SDK.Api.ContactsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateContact**](ContactsApi.md#createcontact) | **POST** /v1/contacts | Create a contact |
| [**DeleteContact**](ContactsApi.md#deletecontact) | **DELETE** /v1/contacts/{id} | Delete a contact |
| [**GetContact**](ContactsApi.md#getcontact) | **GET** /v1/contacts/{id} | Get a contact |
| [**GetContactLists**](ContactsApi.md#getcontactlists) | **GET** /v1/contacts/{id}/lists | Get lists a contact belongs to |
| [**ListContacts**](ContactsApi.md#listcontacts) | **GET** /v1/contacts | List contacts |
| [**UpdateContact**](ContactsApi.md#updatecontact) | **PATCH** /v1/contacts/{id} | Update a contact |

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

