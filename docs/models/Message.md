# Lockally.SDK.Model.Message

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**TenantId** | **Guid** |  | 
**MessageId** | **string** | RFC 5322 Message-ID header, including angle brackets. | 
**Sender** | **string** |  | 
**Recipients** | **List&lt;string&gt;** |  | 
**Status** | **string** |  | 
**QueuedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**Subject** | **string** |  | [optional] 
**BounceReason** | **string** |  | [optional] 
**SizeBytes** | **int** |  | [optional] 
**Metadata** | **Dictionary&lt;string, string&gt;** | The sender&#39;s own key/value from the send request. Always present; &#x60;{}&#x60; when none was set. | [optional] 
**Tags** | **List&lt;string&gt;** | Grouping labels, lowercased and deduplicated. Always present; &#x60;[]&#x60; when none were set. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

