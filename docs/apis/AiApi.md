# Lockally.SDK.Api.AiApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1AiConfigGet**](AiApi.md#v1aiconfigget) | **GET** /v1/ai-config | Read the tenant&#39;s AI configuration |
| [**V1AiConfigPut**](AiApi.md#v1aiconfigput) | **PUT** /v1/ai-config | Configure the AI tier |
| [**V1BillingAiUnitsCheckoutPost**](AiApi.md#v1billingaiunitscheckoutpost) | **POST** /v1/billing/ai-units/checkout | Buy prepaid AI units |
| [**V1ThreadsThreadIDClassifyPost**](AiApi.md#v1threadsthreadidclassifypost) | **POST** /v1/threads/{threadID}/classify | LLM-classify a thread |

<a id="v1aiconfigget"></a>
# **V1AiConfigGet**
> Object V1AiConfigGet ()

Read the tenant's AI configuration

Mode (off/byok/units), model, masked key hint, AI-unit balance, whether the units tier is available on this deployment.


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
| **200** | AI config |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1aiconfigput"></a>
# **V1AiConfigPut**
> Object V1AiConfigPut ()

Configure the AI tier

Body: {\"mode\": \"off|byok|units\", \"model\": \"...\", \"anthropic_key\": \"sk-ant-...\"}. BYOK keys are stored AES-256-GCM encrypted; the cleartext is never returned. Omit anthropic_key to keep the stored one.


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
| **200** | Applied |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1billingaiunitscheckoutpost"></a>
# **V1BillingAiUnitsCheckoutPost**
> Object V1BillingAiUnitsCheckoutPost ()

Buy prepaid AI units

Body: {\"bundle\": \"100|500|2000\"}. One classification = one unit; bundles expire after 6 months. Admin session required. 503 until Paystack billing is configured.


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
| **200** | Paystack authorization URL |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="v1threadsthreadidclassifypost"></a>
# **V1ThreadsThreadIDClassifyPost**
> Object V1ThreadsThreadIDClassifyPost (Guid threadID, bool refresh = null)

LLM-classify a thread

Returns {intent, urgency, summary, suggested_action} via the tenant's AI tier (BYOK or prepaid units — see /v1/ai-config). Cached per thread state: unchanged threads return the cache free; ?refresh=true forces a re-run. A failed model call charges nothing. 402 when the AI tier is off.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **refresh** | **bool** |  | [optional]  |

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
| **200** | Classification |  -  |
| **402** | AI tier not enabled / out of units |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

