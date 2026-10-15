# Lockally.SDK.Api.SendApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelMessage**](SendApi.md#cancelmessage) | **DELETE** /v1/messages/{id} | Cancel a scheduled send |
| [**GetMessage**](SendApi.md#getmessage) | **GET** /v1/messages/{id} | Get message status |
| [**GetMessageStats**](SendApi.md#getmessagestats) | **GET** /v1/messages/stats | Aggregate delivery stats |
| [**ListMessages**](SendApi.md#listmessages) | **GET** /v1/messages | List outbound messages |
| [**SendEmail**](SendApi.md#sendemail) | **POST** /v1/send | Send an email |
| [**SendEmailBatch**](SendApi.md#sendemailbatch) | **POST** /v1/send/batch | Send a batch of emails |

<a id="cancelmessage"></a>
# **CancelMessage**
> void CancelMessage (Guid id)

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

<a id="getmessage"></a>
# **GetMessage**
> MessageDetail GetMessage (Guid id)

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

<a id="getmessagestats"></a>
# **GetMessageStats**
> MessageStats GetMessageStats (DateTime from = null, DateTime to = null, string domain = null)

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

<a id="listmessages"></a>
# **ListMessages**
> ListMessages200Response ListMessages (string status = null, string sender = null, string q = null, DateTime since = null, string cursor = null, int limit = null)

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

[**ListMessages200Response**](ListMessages200Response.md)

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

<a id="sendemail"></a>
# **SendEmail**
> SendEmail200Response SendEmail (string idempotencyKey, SendEmailRequest sendEmailRequest)

Send an email

Submits an email for delivery via lockally. Returns 202 immediately once the message is accepted into lockally's queue; the actual SMTP submission to the recipient is async. Track delivery via `GET /v1/messages/{id}` or webhook subscriptions for `delivery.delivered` / `delivery.bounced` / `delivery.complaint`.  **Idempotency-Key required.** Per design L7 — any unique string per send, 24-hour dedupe window. Repeated calls with the same key return byte-exact the original response and do NOT create a duplicate message.  **Sender authorisation.** `from` must be an address the calling tenant owns on a verified domain. A mailbox always qualifies. On business and combined accounts an **alias** qualifies too, so a send-only address such as `no-reply@` need not be a billed seat. An alias on an unverified domain, or one belonging to another account, is refused with `403`. A catch-all creates no aliases and so grants no sending rights.  **Rate cap.** Per-tenant `rate_cap_per_min` (returned on `/v1/tenant`) is enforced — 429 with `Retry-After: 60` once tripped.  **Recipient warning.** Over 25 total recipients (To+Cc+Bcc) sets a `warning` field in the response — large fan-outs queue noticeably at scale. Hard cap is 100/send.  **Not every success is a 202.** Check the status code, not just the body. A `200` means nothing was queued: either every recipient was already suppressed, or the call used a test key and the send was simulated. Both are successes, and neither produces a real delivery. See the `200` response below.  **Warm-up headers.** While the platform is in its outbound warm-up ramp, accepted sends carry `X-Warmup-Day`, `X-Warmup-Daily-Cap` and `X-Warmup-Used-Today`. They describe a platform-wide cap shared by every tenant, not your own allowance, and they disappear once the ramp finishes. Hitting the cap returns 429. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **idempotencyKey** | **string** |  |  |
| **sendEmailRequest** | [**SendEmailRequest**](SendEmailRequest.md) |  |  |

### Return type

[**SendEmail200Response**](SendEmail200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Accepted, but nothing was queued for real delivery. Two cases, told apart by &#x60;status&#x60;:  - &#x60;suppressed&#x60; — every recipient was on your suppression list, so   the send was dropped. Deliberately a success, not a retryable   error: retrying cannot change the outcome. There is no &#x60;id&#x60; or   &#x60;message_id&#x60;, because no message was created. Complaint and   bounce suppressions block every send; unsubscribe and manual   suppressions block only opt-in sends (&#x60;unsubscribe: true&#x60;). - &#x60;delivered&#x60; — the call used a test key (&#x60;lk_test_&#x60;). The message   is recorded and a &#x60;delivery.delivered&#x60; webhook fires with a   simulated &#x60;250 OK&#x60;, but nothing leaves the platform. Test sends   count against nothing: not your rate cap, allowance, send units,   the warm-up ramp, or your reputation.  |  -  |
| **202** | Queued for delivery. |  * Idempotent-Replay - \&quot;true\&quot; when the response is replayed from the idempotency cache. <br>  * X-Warmup-Day - Present only during the platform&#39;s outbound warm-up ramp: which day of the ramp this send landed on. <br>  * X-Warmup-Daily-Cap - Warm-up ramp only: total messages the whole platform may send today, shared across all tenants. <br>  * X-Warmup-Used-Today - Warm-up ramp only: how much of that platform-wide cap was already used when this send was accepted. <br>  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **429** | Rate limited. Either your per-tenant &#x60;rate_cap_per_min&#x60;, or the platform-wide warm-up cap for the day (which resets at UTC midnight, so &#x60;Retry-After&#x60; can be hours rather than 60 seconds).  |  * Retry-After - 60 for the per-tenant cap; seconds until UTC midnight when the warm-up cap is what was hit. <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="sendemailbatch"></a>
# **SendEmailBatch**
> SendEmailBatch200Response SendEmailBatch (string idempotencyKey, SendEmailBatchRequest sendEmailBatchRequest)

Send a batch of emails

Sends up to 500 messages in one call. Each is validated and enqueued independently — a bad message fails only its own slot (partial success, HTTP 200). One `Idempotency-Key` header covers the batch; per-message keys are derived as `<key>:<index>`. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **idempotencyKey** | **string** |  |  |
| **sendEmailBatchRequest** | [**SendEmailBatchRequest**](SendEmailBatchRequest.md) |  |  |

### Return type

[**SendEmailBatch200Response**](SendEmailBatch200Response.md)

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

