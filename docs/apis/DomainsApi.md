# Lockally.SDK.Api.DomainsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**V1DomainsDomainDelete**](DomainsApi.md#v1domainsdomaindelete) | **DELETE** /v1/domains/{domain} | Delete a domain |
| [**V1DomainsDomainGet**](DomainsApi.md#v1domainsdomainget) | **GET** /v1/domains/{domain} | Get a domain |
| [**V1DomainsDomainVerifyPost**](DomainsApi.md#v1domainsdomainverifypost) | **POST** /v1/domains/{domain}/verify | Force-poll DNS verification |
| [**V1DomainsGet**](DomainsApi.md#v1domainsget) | **GET** /v1/domains | List domains |
| [**V1DomainsPost**](DomainsApi.md#v1domainspost) | **POST** /v1/domains | Register a domain |

<a id="v1domainsdomaindelete"></a>
# **V1DomainsDomainDelete**
> void V1DomainsDomainDelete (string domain)

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

<a id="v1domainsdomainget"></a>
# **V1DomainsDomainGet**
> Domain V1DomainsDomainGet (string domain)

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

<a id="v1domainsdomainverifypost"></a>
# **V1DomainsDomainVerifyPost**
> Domain V1DomainsDomainVerifyPost (string domain)

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

<a id="v1domainsget"></a>
# **V1DomainsGet**
> V1DomainsGet200Response V1DomainsGet ()

List domains

Returns every domain registered under the calling tenant.


### Parameters
This endpoint does not need any parameter.
### Return type

[**V1DomainsGet200Response**](V1DomainsGet200Response.md)

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

<a id="v1domainspost"></a>
# **V1DomainsPost**
> Domain V1DomainsPost (V1DomainsPostRequest v1DomainsPostRequest)

Register a domain

Registers a new domain for the calling tenant. Generates a DKIM keypair and verification token. Returns DNS instructions the tenant must publish under their own DNS (verification TXT, SPF include, DKIM TXT, MX records to `mx1`/`mx2.lockally.com`, DMARC seed).  **Idempotent** — re-posting the same domain returns the existing record with the same DKIM keys and token (regenerating would break the tenant's published DNS). Returns 200 on idempotent hit, 201 on first create.  Returns 409 if the domain is already claimed by a different tenant. 


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **v1DomainsPostRequest** | [**V1DomainsPostRequest**](V1DomainsPostRequest.md) |  |  |

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

