# Lockally.SDK.Model.ThreadMessageBody

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
**Attachments** | [**List&lt;Attachment&gt;**](Attachment.md) |  | [optional] 
**Annotations** | [**Annotations**](Annotations.md) |  | [optional] 
**Body** | [**ThreadMessageBodyAllOfBody**](ThreadMessageBodyAllOfBody.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

