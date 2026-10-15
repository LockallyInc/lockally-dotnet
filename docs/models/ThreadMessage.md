# Lockally.SDK.Model.ThreadMessage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**Direction** | **string** |  | 
**RfcMessageId** | **string** | The Internet Message-ID | 
**From** | **string** |  | 
**To** | **List&lt;string&gt;** |  | 
**HasAttachments** | **bool** |  | 
**ReceivedAt** | **DateTime** |  | 
**InReplyTo** | **string** |  | [optional] 
**Subject** | **string** |  | [optional] 
**Snippet** | **string** |  | [optional] 
**Attachments** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** |  | [optional] 
**Annotations** | **Dictionary&lt;string, Object&gt;** | Signals computed at ingest | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

