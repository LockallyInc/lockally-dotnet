# Lockally.SDK.Api.DomainsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDomain**](DomainsApi.md#createdomain) | **POST** /v1/domains | Register a domain |
| [**DeleteDomain**](DomainsApi.md#deletedomain) | **DELETE** /v1/domains/{domain} | Delete a domain |
| [**DisableReturnPath**](DomainsApi.md#disablereturnpath) | **DELETE** /v1/domains/{domain}/return-path | Turn off the custom Return-Path |
| [**EnableReturnPath**](DomainsApi.md#enablereturnpath) | **POST** /v1/domains/{domain}/return-path | Turn on the custom Return-Path |
| [**GetDomain**](DomainsApi.md#getdomain) | **GET** /v1/domains/{domain} | Get a domain |
| [**GetReturnPath**](DomainsApi.md#getreturnpath) | **GET** /v1/domains/{domain}/return-path | Get the custom Return-Path |
| [**ListDomains**](DomainsApi.md#listdomains) | **GET** /v1/domains | List domains |
| [**VerifyDomain**](DomainsApi.md#verifydomain) | **POST** /v1/domains/{domain}/verify | Force-poll DNS verification |
| [**VerifyReturnPath**](DomainsApi.md#verifyreturnpath) | **POST** /v1/domains/{domain}/return-path/verify | Check the custom Return-Path records |

<a id="createdomain"></a>
# **CreateDomain**
> Domain CreateDomain (CreateDomainRequest createDomainRequest)

Register a domain

Registers a new domain for the calling tenant. Generates a DKIM keypair and verification token. Returns DNS instructions the tenant must publish under their own DNS (verification TXT, SPF include, DKIM TXT, MX records to `mx1`/`mx2.lockally.com`, DMARC seed).  **Idempotent** — re-posting the same domain returns the existing record with the same DKIM keys and token (regenerating would break the tenant's published DNS). Returns 200 on idempotent hit, 201 on first create.  Returns 409 if the domain is already claimed by a different tenant. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createDomainRequest** | [**CreateDomainRequest**](CreateDomainRequest.md) |  |  |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Domain already registered to the calling tenant (idempotent). |  -  |
| **201** | Domain created. |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **409** | Domain claimed by another tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletedomain"></a>
# **DeleteDomain**
> void DeleteDomain (string domain)

Delete a domain

Removes the domain registration. Refuses with 409 if any mailbox is still attached — delete the mailboxes first. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |

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
| **409** | Domain still has mailboxes attached. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="disablereturnpath"></a>
# **DisableReturnPath**
> void DisableReturnPath (string domain)

Turn off the custom Return-Path

API mail uses the sender's own address as the envelope sender again, from the next message. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |

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
| **204** | Turned off. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="enablereturnpath"></a>
# **EnableReturnPath**
> ReturnPath EnableReturnPath (string domain)

Turn on the custom Return-Path

Moves it to `pending` and returns the two records to publish on `bounces.<domain>`. Nothing changes for mail until they are confirmed with the verify call. The domain must be verified. Available on every plan except Free. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |

### Return type

[**ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Return-Path, now pending (or already active). |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | The domain is not verified. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getdomain"></a>
# **GetDomain**
> Domain GetDomain (string domain)

Get a domain


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Domain record including the DNS instructions to publish. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getreturnpath"></a>
# **GetReturnPath**
> ReturnPath GetReturnPath (string domain)

Get the custom Return-Path

A custom Return-Path moves the envelope sender of mail sent through the API from this domain onto `bounces.<domain>`. Bounce reports then come back to Lockally instead of the sending mailbox, and a bounce that arrives after delivery marks the message bounced, suppresses the address and fires `delivery.bounced`. Mail sent from webmail or mail apps is not affected. DKIM stays signed by the domain itself. `status` is `off`, `pending` (records not confirmed yet) or `active`. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |

### Return type

[**ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Current state and the two DNS records to publish. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listdomains"></a>
# **ListDomains**
> ListDomains200Response ListDomains ()

List domains

Returns every domain registered under the calling tenant.


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListDomains200Response**](ListDomains200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Domain list |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="verifydomain"></a>
# **VerifyDomain**
> Domain VerifyDomain (string domain)

Force-poll DNS verification

Synchronously checks the `_lockally-verify.<domain>` TXT record against the stored verification token. Returns 200 either way: the returned `verified` boolean tells you whether DNS now confirms. Caller polls until `verified: true`. In v2 a background worker auto-polls and fires a `domain.verified` webhook. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |

### Return type

[**Domain**](Domain.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Current domain state (possibly newly verified). |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **502** | Upstream DNS error (timeout, server unreachable). Retry. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="verifyreturnpath"></a>
# **VerifyReturnPath**
> ReturnPath VerifyReturnPath (string domain)

Check the custom Return-Path records

Looks up the MX and SPF records on `bounces.<domain>`. Returns 200 either way: while a record is missing the status stays `pending` and `check` says which one. Once both are found the Return-Path becomes `active` and the send path starts using it. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **domain** | **string** |  |  |

### Return type

[**ReturnPath**](ReturnPath.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Return-Path with the result of the check. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |
| **409** | The custom Return-Path is off. Turn it on first. |  -  |
| **502** | The mail server could not be updated. Nothing changed; retry. |  -  |
| **503** | The records are correct but the feature is not available yet. Nothing changed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

