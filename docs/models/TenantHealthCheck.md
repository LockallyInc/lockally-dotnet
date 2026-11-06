# Lockally.SDK.Model.TenantHealthCheck

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Key** | **string** | Stable identifier, today one of &#x60;domain_verification&#x60;, &#x60;smtp&#x60;, &#x60;storage&#x60;, &#x60;security&#x60;. Treat unknown keys as new checks, not errors. | 
**Label** | **string** | Human-readable name for display. | 
**Status** | **string** | &#x60;healthy&#x60;, &#x60;warning&#x60; or &#x60;critical&#x60;. | 
**Detail** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

