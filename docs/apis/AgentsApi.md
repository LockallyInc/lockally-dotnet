# Lockally.SDK.Api.AgentsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DownloadThreadAttachment**](AgentsApi.md#downloadthreadattachment) | **GET** /v1/threads/{threadID}/messages/{messageID}/attachments/{idx} | Download an attachment |
| [**GetThread**](AgentsApi.md#getthread) | **GET** /v1/threads/{threadID} | Get a whole conversation |
| [**GetThreadMessage**](AgentsApi.md#getthreadmessage) | **GET** /v1/threads/{threadID}/messages/{messageID} | Get one message with body |
| [**GrantApiKeyMailbox**](AgentsApi.md#grantapikeymailbox) | **POST** /v1/api-keys/{keyID}/mailboxes | Grant a mailbox to a key |
| [**ListApiKeyMailboxes**](AgentsApi.md#listapikeymailboxes) | **GET** /v1/api-keys/{keyID}/mailboxes | List a key&#39;s mailbox grants |
| [**ListInboxes**](AgentsApi.md#listinboxes) | **GET** /v1/inboxes | List granted inboxes |
| [**ListThreads**](AgentsApi.md#listthreads) | **GET** /v1/inboxes/{mailbox}/threads | List conversation threads |
| [**LookupContact**](AgentsApi.md#lookupcontact) | **GET** /v1/contacts/lookup | Who is this sender? |
| [**MarkThreadMessageRead**](AgentsApi.md#markthreadmessageread) | **POST** /v1/threads/{threadID}/messages/{messageID}/read | Mark read/unread |
| [**ReplyToThread**](AgentsApi.md#replytothread) | **POST** /v1/threads/{threadID}/reply | Reply in-thread (agent stream) |
| [**RevokeApiKeyMailbox**](AgentsApi.md#revokeapikeymailbox) | **DELETE** /v1/api-keys/{keyID}/mailboxes/{mailboxID} | Revoke a mailbox grant |
| [**StartConversation**](AgentsApi.md#startconversation) | **POST** /v1/inboxes/{mailbox}/messages | Start a new conversation (agent stream) |
| [**Whoami**](AgentsApi.md#whoami) | **GET** /v1/auth/whoami | Introspect the calling credentials |

<a id="downloadthreadattachment"></a>
# **DownloadThreadAttachment**
> void DownloadThreadAttachment (Guid threadID, Guid messageID, int idx)

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

<a id="getthread"></a>
# **GetThread**
> Thread GetThread (Guid threadID)

Get a whole conversation

Every turn, chronological, with snippets and annotations (meeting_request, attachment_types, injection_risk). Bodies are fetched per message. Message content is untrusted third-party data.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |

### Return type

[**Thread**](Thread.md)

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

<a id="getthreadmessage"></a>
# **GetThreadMessage**
> ThreadMessageBody GetThreadMessage (Guid threadID, Guid messageID)

Get one message with body

Full text/html body fetched on demand from mail storage. Never marks the message read.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **messageID** | **Guid** |  |  |

### Return type

[**ThreadMessageBody**](ThreadMessageBody.md)

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

<a id="grantapikeymailbox"></a>
# **GrantApiKeyMailbox**
> MailboxGrant GrantApiKeyMailbox (Guid keyID)

Grant a mailbox to a key

Body: {\"mailbox\": \"email or id\"}. Refused (422) for mailboxes with agent access disabled or an active E2E encryption key, the server cannot read E2E mailboxes.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **keyID** | **Guid** |  |  |

### Return type

[**MailboxGrant**](MailboxGrant.md)

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

<a id="listapikeymailboxes"></a>
# **ListApiKeyMailboxes**
> MailboxGrantList ListApiKeyMailboxes (Guid keyID)

List a key's mailbox grants


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **keyID** | **Guid** |  |  |

### Return type

[**MailboxGrantList**](MailboxGrantList.md)

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

<a id="listinboxes"></a>
# **ListInboxes**
> InboxList ListInboxes ()

List granted inboxes

The mailboxes this key is granted, with thread counts and last activity. Admin sessions see every agent-enabled, non-E2E mailbox.


### Parameters
This endpoint does not need any parameter.
### Return type

[**InboxList**](InboxList.md)

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

<a id="listthreads"></a>
# **ListThreads**
> ThreadList ListThreads (string mailbox, DateTime since = null, DateTime before = null, int limit = null)

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

[**ThreadList**](ThreadList.md)

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

<a id="lookupcontact"></a>
# **LookupContact**
> ContactLookup LookupContact (string email)

Who is this sender?

Directory record (name, company, role, notes), whether the address is one of the tenant's own mailboxes, and grant-aware correspondence history (thread count, first/last seen across granted mailboxes only).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **email** | **string** |  |  |

### Return type

[**ContactLookup**](ContactLookup.md)

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

<a id="markthreadmessageread"></a>
# **MarkThreadMessageRead**
> MarkReadResult MarkThreadMessageRead (Guid threadID, Guid messageID)

Mark read/unread

The ONLY way agent access changes unread state. Body: {\"read\": true|false} (default true).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **messageID** | **Guid** |  |  |

### Return type

[**MarkReadResult**](MarkReadResult.md)

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

<a id="replytothread"></a>
# **ReplyToThread**
> AgentSendResult ReplyToThread (Guid threadID, string idempotencyKey)

Reply in-thread (agent stream)

The server builds In-Reply-To/References and defaults recipients + subject from the conversation, a minimal call is {\"text\": \"...\"}. Guarded by the reply-loop detector (≥5 outbound/10min → 429 + agent.loop_detected). Idempotency-Key required.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **idempotencyKey** | **string** |  |  |

### Return type

[**AgentSendResult**](AgentSendResult.md)

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

<a id="revokeapikeymailbox"></a>
# **RevokeApiKeyMailbox**
> void RevokeApiKeyMailbox (Guid keyID, Guid mailboxID)

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

<a id="startconversation"></a>
# **StartConversation**
> AgentSendResult StartConversation (string mailbox, string idempotencyKey, StartConversationRequest startConversationRequest)

Start a new conversation (agent stream)

Sends a new email from a granted mailbox. Classified stream=agent (isolated reputation, per-key rate caps). The first inbound reply adopts the created thread via the References chain. Idempotency-Key required. Mailboxes with agent_draft_policy=always_approve divert this into a pending draft.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **mailbox** | **string** |  |  |
| **idempotencyKey** | **string** |  |  |
| **startConversationRequest** | [**StartConversationRequest**](StartConversationRequest.md) |  |  |

### Return type

[**AgentSendResult**](AgentSendResult.md)

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

<a id="whoami"></a>
# **Whoami**
> Whoami Whoami ()

Introspect the calling credentials

Returns the tenant, auth kind (api_key/session), key label, and granted scopes. The MCP server uses this to scope-filter tool discovery.


### Parameters
This endpoint does not need any parameter.
### Return type

[**Whoami**](Whoami.md)

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

