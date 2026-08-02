# Lockally.SDK.Api.WebhooksApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1WebhooksGet**](WebhooksApi.md#v1webhooksget) | **GET** /v1/webhooks | List webhooks |
| [**V1WebhooksIdDelete**](WebhooksApi.md#v1webhooksiddelete) | **DELETE** /v1/webhooks/{id} | Delete a webhook |
| [**V1WebhooksIdPatch**](WebhooksApi.md#v1webhooksidpatch) | **PATCH** /v1/webhooks/{id} | Update a webhook |
| [**V1WebhooksPost**](WebhooksApi.md#v1webhookspost) | **POST** /v1/webhooks | Create a webhook |

<a id="v1webhooksget"></a>
# **V1WebhooksGet**
> V1WebhooksGet200Response V1WebhooksGet ()

List webhooks

Returns the calling tenant's webhook subscriptions. Never returns the signing secret — only metadata. 


### Parameters
This endpoint does not need any parameter.
### Return type

[**V1WebhooksGet200Response**](V1WebhooksGet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook list. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1webhooksiddelete"></a>
# **V1WebhooksIdDelete**
> void V1WebhooksIdDelete (Guid id)

Delete a webhook

Hard-delete; cascades to `webhook_deliveries` history.


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
| **204** | Deleted. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1webhooksidpatch"></a>
# **V1WebhooksIdPatch**
> Webhook V1WebhooksIdPatch (Guid id, V1WebhooksIdPatchRequest v1WebhooksIdPatchRequest)

Update a webhook

Supply at least one of `url`, `events`, `paused`. Setting `paused` to `false` ALSO resets `consecutive_failures` to 0 — re-arms the 50-failure auto-pause counter. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **v1WebhooksIdPatchRequest** | [**V1WebhooksIdPatchRequest**](V1WebhooksIdPatchRequest.md) |  |  |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated webhook. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1webhookspost"></a>
# **V1WebhooksPost**
> Webhook V1WebhooksPost (V1WebhooksPostRequest v1WebhooksPostRequest)

Create a webhook

Subscribes a URL to one or more event types. Returns the `signing_secret` ONCE in the response — store it immediately. The dispatcher signs every outbound POST per design L3:      X-Lockally-Signature: t=<unix>,v1=<hex(hmac_sha256(secret, t + \".\" + body))>  Verify on your end using HMAC-SHA256 with a 5-minute timestamp window (replay protection). A reference verifier ships in [internal/webhook](https://github.com/ucheigwedinma/lockally/blob/main/internal/webhook/sign.go).  Event names: see the [event catalogue](https://github.com/ucheigwedinma/lockally/blob/main/docs/v1-design.md#64-webhook-event-catalogue-v1). 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **v1WebhooksPostRequest** | [**V1WebhooksPostRequest**](V1WebhooksPostRequest.md) |  |  |

### Return type

[**Webhook**](Webhook.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. &#x60;signing_secret&#x60; is in the response ONLY here. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

