# Lockally.SDK.Api.MailboxesApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddSharedMember**](MailboxesApi.md#addsharedmember) | **POST** /v1/mailboxes/{email}/members | Add a shared mailbox member |
| [**ListSharedMembers**](MailboxesApi.md#listsharedmembers) | **GET** /v1/mailboxes/{email}/members | List shared mailbox members |
| [**RemoveSharedMember**](MailboxesApi.md#removesharedmember) | **DELETE** /v1/mailboxes/{email}/members/{memberEmail} | Remove a shared mailbox member |
| [**V1MailboxesEmailDelete**](MailboxesApi.md#v1mailboxesemaildelete) | **DELETE** /v1/mailboxes/{email} | Soft-delete a mailbox |
| [**V1MailboxesEmailExportDownloadGet**](MailboxesApi.md#v1mailboxesemailexportdownloadget) | **GET** /v1/mailboxes/{email}/export/download | Download a previously-issued mailbox export |
| [**V1MailboxesEmailExportPost**](MailboxesApi.md#v1mailboxesemailexportpost) | **POST** /v1/mailboxes/{email}/export | Request a mailbox export |
| [**V1MailboxesEmailGet**](MailboxesApi.md#v1mailboxesemailget) | **GET** /v1/mailboxes/{email} | Get a mailbox |
| [**V1MailboxesEmailPatch**](MailboxesApi.md#v1mailboxesemailpatch) | **PATCH** /v1/mailboxes/{email} | Update a mailbox |
| [**V1MailboxesEmailVacationDelete**](MailboxesApi.md#v1mailboxesemailvacationdelete) | **DELETE** /v1/mailboxes/{email}/vacation | Remove the vacation responder |
| [**V1MailboxesEmailVacationGet**](MailboxesApi.md#v1mailboxesemailvacationget) | **GET** /v1/mailboxes/{email}/vacation | Get the vacation responder |
| [**V1MailboxesEmailVacationPut**](MailboxesApi.md#v1mailboxesemailvacationput) | **PUT** /v1/mailboxes/{email}/vacation | Set the vacation responder |
| [**V1MailboxesGet**](MailboxesApi.md#v1mailboxesget) | **GET** /v1/mailboxes | List mailboxes |
| [**V1MailboxesPost**](MailboxesApi.md#v1mailboxespost) | **POST** /v1/mailboxes | Create a mailbox |
| [**V1VacationGet**](MailboxesApi.md#v1vacationget) | **GET** /v1/vacation | List all vacation responders |

<a id="addsharedmember"></a>
# **AddSharedMember**
> SharedMember AddSharedMember (string email, AddSharedMemberRequest addSharedMemberRequest)

Add a shared mailbox member


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |
| **addSharedMemberRequest** | [**AddSharedMemberRequest**](AddSharedMemberRequest.md) |  |  |

### Return type

[**SharedMember**](SharedMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Member added. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Already a member of this mailbox. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listsharedmembers"></a>
# **ListSharedMembers**
> ListSharedMembers200Response ListSharedMembers (string email)

List shared mailbox members


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

[**ListSharedMembers200Response**](ListSharedMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Members of the shared mailbox. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="removesharedmember"></a>
# **RemoveSharedMember**
> void RemoveSharedMember (string email, string memberEmail)

Remove a shared mailbox member


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |
| **memberEmail** | **string** |  |  |

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
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemaildelete"></a>
# **V1MailboxesEmailDelete**
> void V1MailboxesEmailDelete (string email)

Soft-delete a mailbox

Sets `soft_deleted_at = now()` and `hard_delete_after = now() + 90d` per design D25. A background sweep (planned) will hard-delete after the window. The mailbox is also disabled immediately. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

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
| **204** | Soft-deleted. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemailexportdownloadget"></a>
# **V1MailboxesEmailExportDownloadGet**
> System.IO.Stream V1MailboxesEmailExportDownloadGet (string email, string token)

Download a previously-issued mailbox export

Public endpoint (no Authorization header). Validates the one-shot token from the URL, marks it used, and streams an mbox file. Second GET with the same token returns 404 — tokens are single-use. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |
| **token** | **string** |  |  |

### Return type

**System.IO.Stream**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/mbox, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | mbox stream. |  -  |
| **400** | Malformed request. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Token not found, already used, or expired. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemailexportpost"></a>
# **V1MailboxesEmailExportPost**
> V1MailboxesEmailExportPost201Response V1MailboxesEmailExportPost (string email)

Request a mailbox export

Issues a one-shot \"presigned\" download URL for the mailbox's content in mbox format. The URL works without an Authorization header — the token in the query string is the authz. TTL is 5 minutes; the token is consumed on first GET.  **v1 caveat:** the synthesized mbox only contains outbound mail (from `lockally.messages`). v2 swaps in Stalwart's export primitive for full inbox + folder structure + flags. The endpoint contract stays unchanged. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

[**V1MailboxesEmailExportPost201Response**](V1MailboxesEmailExportPost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Export token issued. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemailget"></a>
# **V1MailboxesEmailGet**
> Mailbox V1MailboxesEmailGet (string email)

Get a mailbox


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mailbox info. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemailpatch"></a>
# **V1MailboxesEmailPatch**
> Mailbox V1MailboxesEmailPatch (string email, V1MailboxesEmailPatchRequest v1MailboxesEmailPatchRequest)

Update a mailbox

Supply at least one of `password`, `quota_bytes`, `disabled`. Returns the updated mailbox. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |
| **v1MailboxesEmailPatchRequest** | [**V1MailboxesEmailPatchRequest**](V1MailboxesEmailPatchRequest.md) |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated mailbox. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemailvacationdelete"></a>
# **V1MailboxesEmailVacationDelete**
> void V1MailboxesEmailVacationDelete (string email)

Remove the vacation responder

Idempotent — 204 whether or not a row existed.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

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

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemailvacationget"></a>
# **V1MailboxesEmailVacationGet**
> VacationResponder V1MailboxesEmailVacationGet (string email)

Get the vacation responder

Returns the stored vacation rule or 404 if none is set.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

[**VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Vacation responder. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesemailvacationput"></a>
# **V1MailboxesEmailVacationPut**
> VacationResponder V1MailboxesEmailVacationPut (string email, V1MailboxesEmailVacationPutRequest v1MailboxesEmailVacationPutRequest)

Set the vacation responder

Upsert — same endpoint creates or replaces the rule. Clears `synced_at`; the rule is staged on lockally until a sync worker pushes it to the mail server. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |
| **v1MailboxesEmailVacationPutRequest** | [**V1MailboxesEmailVacationPutRequest**](V1MailboxesEmailVacationPutRequest.md) |  |  |

### Return type

[**VacationResponder**](VacationResponder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Saved. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxesget"></a>
# **V1MailboxesGet**
> V1MailboxesGet200Response V1MailboxesGet (int limit = null)

List mailboxes

Returns mailboxes under the calling tenant — active and soft-deleted. `?limit=N` between 1 and 200 (default 50). 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **limit** | **int** |  | [optional] [default to 50] |

### Return type

[**V1MailboxesGet200Response**](V1MailboxesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mailbox list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1mailboxespost"></a>
# **V1MailboxesPost**
> Mailbox V1MailboxesPost (V1MailboxesPostRequest v1MailboxesPostRequest)

Create a mailbox

Creates a mailbox on a tenant-verified domain. If `password` is omitted, lockally generates a 16-char password and returns it in the response — shown once.  **Gate.** The mailbox's domain must already be registered AND verified for this tenant (via `/v1/domains` + `/v1/domains/{domain}/verify`).  **Idempotent.** Re-posting the same email returns the existing mailbox UNTOUCHED — password is NOT regenerated. To change a password, use PATCH instead. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **v1MailboxesPostRequest** | [**V1MailboxesPostRequest**](V1MailboxesPostRequest.md) |  |  |

### Return type

[**Mailbox**](Mailbox.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Mailbox already existed for this tenant (idempotent). |  -  |
| **201** | Mailbox created. &#x60;password&#x60; is in the response ONLY if generated. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Email claimed by another tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1vacationget"></a>
# **V1VacationGet**
> V1VacationGet200Response V1VacationGet ()

List all vacation responders

Returns every vacation responder for the calling tenant.


### Parameters
This endpoint does not need any parameter.
### Return type

[**V1VacationGet200Response**](V1VacationGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

