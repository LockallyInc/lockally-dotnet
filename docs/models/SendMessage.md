# Lockally.SDK.Model.SendMessage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**From** | **string** |  | 
**To** | **List&lt;string&gt;** |  | 
**Cc** | **List&lt;string&gt;** |  | [optional] 
**Bcc** | **List&lt;string&gt;** |  | [optional] 
**Subject** | **string** |  | [optional] 
**Text** | **string** |  | [optional] 
**Html** | **string** |  | [optional] 
**Headers** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**ReplyTo** | **string** | Where replies go. Required when &#x60;from&#x60; has no mailbox behind it. The named form &#x60;Acme Support &lt;a@b.com&gt;&#x60; is also accepted. | [optional] 
**ReplyToName** | **string** | Display name shown on &#x60;Reply-To&#x60;. Ignored without &#x60;reply_to&#x60;. | [optional] 
**Unsubscribe** | **bool** |  | [optional] 
**TemplateId** | **Guid** |  | [optional] 
**Variables** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**SendAt** | **DateTime** |  | [optional] 
**Attachments** | [**List&lt;SendEmailRequestAttachmentsInner&gt;**](SendEmailRequestAttachmentsInner.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

