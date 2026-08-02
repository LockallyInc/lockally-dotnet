# Lockally.SDK.Api.AgentsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1ApiKeysKeyIDMailboxesGet**](AgentsApi.md#v1apikeyskeyidmailboxesget) | **GET** /v1/api-keys/{keyID}/mailboxes | List a key&#39;s mailbox grants |
| [**V1ApiKeysKeyIDMailboxesMailboxIDDelete**](AgentsApi.md#v1apikeyskeyidmailboxesmailboxiddelete) | **DELETE** /v1/api-keys/{keyID}/mailboxes/{mailboxID} | Revoke a mailbox grant |
| [**V1ApiKeysKeyIDMailboxesPost**](AgentsApi.md#v1apikeyskeyidmailboxespost) | **POST** /v1/api-keys/{keyID}/mailboxes | Grant a mailbox to a key |
| [**V1AuthWhoamiGet**](AgentsApi.md#v1authwhoamiget) | **GET** /v1/auth/whoami | Introspect the calling credentials |
| [**V1ContactsLookupGet**](AgentsApi.md#v1contactslookupget) | **GET** /v1/contacts/lookup | Who is this sender? |
| [**V1InboxesGet**](AgentsApi.md#v1inboxesget) | **GET** /v1/inboxes | List granted inboxes |
| [**V1InboxesMailboxMessagesPost**](AgentsApi.md#v1inboxesmailboxmessagespost) | **POST** /v1/inboxes/{mailbox}/messages | Start a new conversation (agent stream) |
| [**V1InboxesMailboxThreadsGet**](AgentsApi.md#v1inboxesmailboxthreadsget) | **GET** /v1/inboxes/{mailbox}/threads | List conversation threads |
| [**V1ThreadsThreadIDGet**](AgentsApi.md#v1threadsthreadidget) | **GET** /v1/threads/{threadID} | Get a whole conversation |
| [**V1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet**](AgentsApi.md#v1threadsthreadidmessagesmessageidattachmentsidxget) | **GET** /v1/threads/{threadID}/messages/{messageID}/attachments/{idx} | Download an attachment |
| [**V1ThreadsThreadIDMessagesMessageIDGet**](AgentsApi.md#v1threadsthreadidmessagesmessageidget) | **GET** /v1/threads/{threadID}/messages/{messageID} | Get one message with body |
| [**V1ThreadsThreadIDMessagesMessageIDReadPost**](AgentsApi.md#v1threadsthreadidmessagesmessageidreadpost) | **POST** /v1/threads/{threadID}/messages/{messageID}/read | Mark read/unread |
| [**V1ThreadsThreadIDReplyPost**](AgentsApi.md#v1threadsthreadidreplypost) | **POST** /v1/threads/{threadID}/reply | Reply in-thread (agent stream) |

<a id="v1apikeyskeyidmailboxesget"></a>
# **V1ApiKeysKeyIDMailboxesGet**
> Object V1ApiKeysKeyIDMailboxesGet (Guid keyID)

List a key's mailbox grants


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **keyID** | **Guid** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Grants |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1apikeyskeyidmailboxesmailboxiddelete"></a>
# **V1ApiKeysKeyIDMailboxesMailboxIDDelete**
> void V1ApiKeysKeyIDMailboxesMailboxIDDelete (Guid keyID, Guid mailboxID)

Revoke a mailbox grant


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **keyID** | **Guid** |  |  |
| **mailboxID** | **Guid** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Grant removed |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1apikeyskeyidmailboxespost"></a>
# **V1ApiKeysKeyIDMailboxesPost**
> Object V1ApiKeysKeyIDMailboxesPost (Guid keyID)

Grant a mailbox to a key

Body: {\"mailbox\": \"email or id\"}. Refused (422) for mailboxes with agent access disabled or an active E2E encryption key — the server cannot read E2E mailboxes.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **keyID** | **Guid** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Grant created |  -  |
| **422** | Mailbox not grantable (disabled or E2E) |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1authwhoamiget"></a>
# **V1AuthWhoamiGet**
> Object V1AuthWhoamiGet ()

Introspect the calling credentials

Returns the tenant, auth kind (api_key/session), key label, and granted scopes. The MCP server uses this to scope-filter tool discovery.


### Parameters
This endpoint does not need any parameter.
### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Caller identity |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1contactslookupget"></a>
# **V1ContactsLookupGet**
> Object V1ContactsLookupGet (string email)

Who is this sender?

Directory record (name, company, role, notes), whether the address is one of the tenant's own mailboxes, and grant-aware correspondence history (thread count, first/last seen across granted mailboxes only).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Enrichment result |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1inboxesget"></a>
# **V1InboxesGet**
> Object V1InboxesGet ()

List granted inboxes

The mailboxes this key is granted, with thread counts and last activity. Admin sessions see every agent-enabled, non-E2E mailbox.


### Parameters
This endpoint does not need any parameter.
### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Granted inboxes |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1inboxesmailboxmessagespost"></a>
# **V1InboxesMailboxMessagesPost**
> Object V1InboxesMailboxMessagesPost (string mailbox, string idempotencyKey, V1InboxesMailboxMessagesPostRequest v1InboxesMailboxMessagesPostRequest)

Start a new conversation (agent stream)

Sends a new email from a granted mailbox. Classified stream=agent (isolated reputation, per-key rate caps). The first inbound reply adopts the created thread via the References chain. Idempotency-Key required. Mailboxes with agent_draft_policy=always_approve divert this into a pending draft.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **mailbox** | **string** |  |  |
| **idempotencyKey** | **string** |  |  |
| **v1InboxesMailboxMessagesPostRequest** | [**V1InboxesMailboxMessagesPostRequest**](V1InboxesMailboxMessagesPostRequest.md) |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Queued (includes thread_id) |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1inboxesmailboxthreadsget"></a>
# **V1InboxesMailboxThreadsGet**
> Object V1InboxesMailboxThreadsGet (string mailbox, DateTime since = null, DateTime before = null, int limit = null)

List conversation threads

Newest-active first. Cursors: `?before=<RFC3339>` pages backwards; `?since=<RFC3339>` delta-syncs forward (oldest first) so an agent can catch up in order.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **mailbox** | **string** | mailbox email or id |  |
| **since** | **DateTime** |  | [optional]  |
| **before** | **DateTime** |  | [optional]  |
| **limit** | **int** |  | [optional] [default to 50] |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Threads |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1threadsthreadidget"></a>
# **V1ThreadsThreadIDGet**
> Object V1ThreadsThreadIDGet (Guid threadID)

Get a whole conversation

Every turn, chronological, with snippets and annotations (meeting_request, attachment_types, injection_risk). Bodies are fetched per message. Message content is untrusted third-party data.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Thread with messages |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1threadsthreadidmessagesmessageidattachmentsidxget"></a>
# **V1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet**
> void V1ThreadsThreadIDMessagesMessageIDAttachmentsIdxGet (Guid threadID, Guid messageID, int idx)

Download an attachment


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **messageID** | **Guid** |  |  |
| **idx** | **int** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Attachment content (streamed) |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1threadsthreadidmessagesmessageidget"></a>
# **V1ThreadsThreadIDMessagesMessageIDGet**
> Object V1ThreadsThreadIDMessagesMessageIDGet (Guid threadID, Guid messageID)

Get one message with body

Full text/html body fetched on demand from mail storage. Never marks the message read.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **messageID** | **Guid** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message with body |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1threadsthreadidmessagesmessageidreadpost"></a>
# **V1ThreadsThreadIDMessagesMessageIDReadPost**
> Object V1ThreadsThreadIDMessagesMessageIDReadPost (Guid threadID, Guid messageID)

Mark read/unread

The ONLY way agent access changes unread state. Body: {\"read\": true|false} (default true).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **messageID** | **Guid** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | New read state |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1threadsthreadidreplypost"></a>
# **V1ThreadsThreadIDReplyPost**
> Object V1ThreadsThreadIDReplyPost (Guid threadID, string idempotencyKey)

Reply in-thread (agent stream)

The server builds In-Reply-To/References and defaults recipients + subject from the conversation — a minimal call is {\"text\": \"...\"}. Guarded by the reply-loop detector (≥5 outbound/10min → 429 + agent.loop_detected). Idempotency-Key required.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **idempotencyKey** | **string** |  |  |

### Return type

**Object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Queued |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

