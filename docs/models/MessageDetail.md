# Lockally.SDK.Model.MessageDetail
A single message with the content captured at send time. Returned only by GET /v1/messages/{id} (the list stays summary-only). Attachments are not returned. 

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
**From** | **string** |  | [optional] 
**To** | **List&lt;string&gt;** |  | [optional] 
**Cc** | **List&lt;string&gt;** |  | [optional] 
**Bcc** | **List&lt;string&gt;** |  | [optional] 
**Text** | **string** |  | [optional] 
**Html** | **string** |  | [optional] 
**Headers** | **Dictionary&lt;string, string&gt;** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

