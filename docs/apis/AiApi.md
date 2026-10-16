# Lockally.SDK.Api.AiApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ClassifyThread**](AiApi.md#classifythread) | **POST** /v1/threads/{threadID}/classify | LLM-classify a thread |
| [**CreateAiUnitsCheckout**](AiApi.md#createaiunitscheckout) | **POST** /v1/billing/ai-units/checkout | Buy prepaid AI units |
| [**GetAiConfig**](AiApi.md#getaiconfig) | **GET** /v1/ai-config | Read the tenant&#39;s AI configuration |
| [**UpdateAiConfig**](AiApi.md#updateaiconfig) | **PUT** /v1/ai-config | Configure the AI tier |

<a id="classifythread"></a>
# **ClassifyThread**
> ThreadClassification ClassifyThread (Guid threadID, bool refresh = null)

LLM-classify a thread

Returns {intent, urgency, summary, suggested_action} via the tenant's AI tier (BYOK or prepaid units, see /v1/ai-config). Cached per thread state: unchanged threads return the cache free; ?refresh=true forces a re-run. A failed model call charges nothing. 402 when the AI tier is off.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **threadID** | **Guid** |  |  |
| **refresh** | **bool** |  | [optional]  |

### Return type

[**ThreadClassification**](ThreadClassification.md)

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

<a id="createaiunitscheckout"></a>
# **CreateAiUnitsCheckout**
> CreateAiUnitsCheckout200Response CreateAiUnitsCheckout ()

Buy prepaid AI units

Body: {\"bundle\": \"100|500|2000\"}. One classification = one unit; bundles expire after 6 months. Admin session required. 503 until Paystack billing is configured.


### Parameters
This endpoint does not need any parameter.
### Return type

[**CreateAiUnitsCheckout200Response**](CreateAiUnitsCheckout200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paystack authorization URL for the selected AI unit bundle. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getaiconfig"></a>
# **GetAiConfig**
> AiConfig GetAiConfig ()

Read the tenant's AI configuration

Mode (off/byok/units), model, masked key hint, AI-unit balance, whether the units tier is available on this deployment.


### Parameters
This endpoint does not need any parameter.
### Return type

[**AiConfig**](AiConfig.md)

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

<a id="updateaiconfig"></a>
# **UpdateAiConfig**
> AiConfigUpdate UpdateAiConfig ()

Configure the AI tier

Body: {\"mode\": \"off|byok|units\", \"model\": \"...\", \"anthropic_key\": \"sk-ant-...\"}. BYOK keys are stored AES-256-GCM encrypted; the cleartext is never returned. Omit anthropic_key to keep the stored one.


### Parameters
This endpoint does not need any parameter.
### Return type

[**AiConfigUpdate**](AiConfigUpdate.md)

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

