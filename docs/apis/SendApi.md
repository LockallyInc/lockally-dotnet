# Lockally.SDK.Api.SendApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1MessagesGet**](SendApi.md#v1messagesget) | **GET** /v1/messages | List outbound messages |
| [**V1MessagesIdDelete**](SendApi.md#v1messagesiddelete) | **DELETE** /v1/messages/{id} | Cancel a scheduled send |
| [**V1MessagesIdGet**](SendApi.md#v1messagesidget) | **GET** /v1/messages/{id} | Get message status |
| [**V1MessagesStatsGet**](SendApi.md#v1messagesstatsget) | **GET** /v1/messages/stats | Aggregate delivery stats |
| [**V1SendBatchPost**](SendApi.md#v1sendbatchpost) | **POST** /v1/send/batch | Send a batch of emails |
| [**V1SendPost**](SendApi.md#v1sendpost) | **POST** /v1/send | Send an email |

<a id="v1messagesget"></a>
# **V1MessagesGet**
> V1MessagesGet200Response V1MessagesGet (string status = null, string sender = null, string q = null, DateTime since = null, string cursor = null, int limit = null)

List outbound messages

Returns recent outbound messages for the calling tenant, sorted newest first. Backs the send-status pill in the SvelteKit /sends view and the outbound search box. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **status** | **string** |  | [optional]  |
| **sender** | **string** | Exact match against the &#x60;from&#x60; mailbox. | [optional]  |
| **q** | **string** | Free-text search across subject + sender. | [optional]  |
| **since** | **DateTime** | Only messages queued at or after this RFC 3339 instant. | [optional]  |
| **cursor** | **string** | queued_at of the prior page boundary. Pass back the &#x60;next_cursor&#x60; returned by the previous call. | [optional]  |
| **limit** | **int** |  | [optional] [default to 50] |

### Return type

[**V1MessagesGet200Response**](V1MessagesGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of messages + optional next-page cursor. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1messagesiddelete"></a>
# **V1MessagesIdDelete**
> void V1MessagesIdDelete (Guid id)

Cancel a scheduled send

Cancels a still-scheduled message (future queued_at). Already sending/sent → 409.


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
| **204** | Cancelled. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | Not cancellable (already sending or sent). |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1messagesidget"></a>
# **V1MessagesIdGet**
> MessageDetail V1MessagesIdGet (Guid id)

Get message status


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**MessageDetail**](MessageDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message record with the content captured at send time. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1messagesstatsget"></a>
# **V1MessagesStatsGet**
> MessageStats V1MessagesStatsGet (DateTime from = null, DateTime to = null, string domain = null)

Aggregate delivery stats

Counts by delivery outcome (delivered/bounced/deferred/complaint) plus rates over a window, from the delivery-event store. Privacy-first: this reflects what receiving servers reported, NOT whether a human opened the mail — Lockally does no open/click tracking. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **from** | **DateTime** | Window start (default 7 days ago). | [optional]  |
| **to** | **DateTime** | Window end (default now). | [optional]  |
| **domain** | **string** | Filter by sender domain. | [optional]  |

### Return type

[**MessageStats**](MessageStats.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Stats. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1sendbatchpost"></a>
# **V1SendBatchPost**
> V1SendBatchPost200Response V1SendBatchPost (string idempotencyKey, V1SendBatchPostRequest v1SendBatchPostRequest)

Send a batch of emails

Sends up to 500 messages in one call. Each is validated and enqueued independently — a bad message fails only its own slot (partial success, HTTP 200). One `Idempotency-Key` header covers the batch; per-message keys are derived as `<key>:<index>`. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **idempotencyKey** | **string** |  |  |
| **v1SendBatchPostRequest** | [**V1SendBatchPostRequest**](V1SendBatchPostRequest.md) |  |  |

### Return type

[**V1SendBatchPost200Response**](V1SendBatchPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-message results (partial success). |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1sendpost"></a>
# **V1SendPost**
> V1SendPost202Response V1SendPost (string idempotencyKey, V1SendPostRequest v1SendPostRequest)

Send an email

Submits an email for delivery via lockally. Returns 202 immediately once the message is accepted into lockally's queue; the actual SMTP submission to the recipient is async. Track delivery via `GET /v1/messages/{id}` or webhook subscriptions for `delivery.delivered` / `delivery.bounced` / `delivery.complaint`.  **Idempotency-Key required.** Per design L7 — any unique string per send, 24-hour dedupe window. Repeated calls with the same key return byte-exact the original response and do NOT create a duplicate message.  **Sender authorisation.** `from` must be a non-disabled mailbox owned by the calling tenant on a verified domain. Sending from aliases is not yet supported.  **Rate cap.** Per-tenant `rate_cap_per_min` (returned on `/v1/tenant`) is enforced — 429 with `Retry-After: 60` once tripped.  **Recipient warning.** Over 25 total recipients (To+Cc+Bcc) sets a `warning` field in the response — large fan-outs queue noticeably at scale. Hard cap is 100/send. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **idempotencyKey** | **string** |  |  |
| **v1SendPostRequest** | [**V1SendPostRequest**](V1SendPostRequest.md) |  |  |

### Return type

[**V1SendPost202Response**](V1SendPost202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Queued. |  * Idempotent-Replay - \&quot;true\&quot; when the response is replayed from the idempotency cache. <br>  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **429** | Per-tenant rate cap exceeded. |  * Retry-After -  <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

