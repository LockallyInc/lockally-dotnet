# Lockally.SDK.Api.DraftsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ApproveDraft**](DraftsApi.md#approvedraft) | **POST** /v1/drafts/{draftID}/approve | Approve a pending draft (human) |
| [**CancelDraft**](DraftsApi.md#canceldraft) | **POST** /v1/drafts/{draftID}/cancel | Withdraw a pending draft |
| [**CreateConversationDraft**](DraftsApi.md#createconversationdraft) | **POST** /v1/inboxes/{mailbox}/drafts | Propose a new conversation as a draft |
| [**CreateReplyDraft**](DraftsApi.md#createreplydraft) | **POST** /v1/threads/{threadID}/drafts | Propose a reply as a draft |
| [**GetDraft**](DraftsApi.md#getdraft) | **GET** /v1/drafts/{draftID} | Get a draft |
| [**ListDrafts**](DraftsApi.md#listdrafts) | **GET** /v1/drafts | List drafts |
| [**RejectDraft**](DraftsApi.md#rejectdraft) | **POST** /v1/drafts/{draftID}/reject | Reject a pending draft (human) |

<a id="approvedraft"></a>
# **ApproveDraft**
> DraftResult ApproveDraft (Guid draftID)

Approve a pending draft (human)

Sends the draft exactly as reviewed, through the agent stream (loop detector included). Fires draft.approved.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **draftID** | **Guid** |  |  |

### Return type

[**DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sent |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="canceldraft"></a>
# **CancelDraft**
> Draft CancelDraft (Guid draftID)

Withdraw a pending draft

Only the API key that created the draft may cancel it.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **draftID** | **Guid** |  |  |

### Return type

[**Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Cancelled |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createconversationdraft"></a>
# **CreateConversationDraft**
> DraftResult CreateConversationDraft (string mailbox, string idempotencyKey)

Propose a new conversation as a draft

New-conversation drafts ALWAYS require human approval (policy flag new_thread). Idempotency-Key required.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **mailbox** | **string** |  |  |
| **idempotencyKey** | **string** |  |  |

### Return type

[**DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Draft outcome (pending_approval) |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createreplydraft"></a>
# **CreateReplyDraft**
> DraftResult CreateReplyDraft (Guid threadID, string idempotencyKey)

Propose a reply as a draft

The safe default over /reply: the deterministic policy engine auto-sends clean in-thread replies and holds anything risky (PII, new recipients, injection-flagged threads, always-approve mailboxes) for human approval. Fires draft.pending_approval when held. Idempotency-Key required.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **idempotencyKey** | **string** |  |  |

### Return type

[**DraftResult**](DraftResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Outcome (sent | pending_approval) with policy_flags |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getdraft"></a>
# **GetDraft**
> Draft GetDraft (Guid draftID)

Get a draft


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **draftID** | **Guid** |  |  |

### Return type

[**Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Draft |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listdrafts"></a>
# **ListDrafts**
> DraftList ListDrafts (string status = null, int limit = null)

List drafts

Filter with ?status=pending_approval|sent|rejected|cancelled. Keys see drafts of granted mailboxes; admin sessions see all.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **status** | **string** |  | [optional]  |
| **limit** | **int** |  | [optional] [default to 50] |

### Return type

[**DraftList**](DraftList.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Drafts |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="rejectdraft"></a>
# **RejectDraft**
> Draft RejectDraft (Guid draftID)

Reject a pending draft (human)

Body: {\"reason\": \"...\"} (optional). Fires draft.rejected.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **draftID** | **Guid** |  |  |

### Return type

[**Draft**](Draft.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Rejected |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

