# Lockally.SDK.Model.V1SendPostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**From** | **string** |  | 
**To** | **List&lt;string&gt;** |  | 
**Cc** | **List&lt;string&gt;** |  | [optional] 
**Bcc** | **List&lt;string&gt;** |  | [optional] 
**Subject** | **string** |  | [optional] 
**Text** | **string** | Plain-text body. Required if &#x60;html&#x60; is absent. | [optional] 
**Html** | **string** | HTML body. Required if &#x60;text&#x60; is absent. | [optional] 
**Headers** | **Dictionary&lt;string, string&gt;** |  | [optional] 
**Unsubscribe** | **bool** | Mark as opt-in/broadcast: skips suppressed recipients and adds a managed one-click List-Unsubscribe header. | [optional] 
**TemplateId** | **Guid** | Render subject/text/html from a stored template (GET /v1/templates). Mutually exclusive with inline subject/text/html. | [optional] 
**Variables** | **Dictionary&lt;string, string&gt;** | Values substituted into the template&#39;s {{variable}} placeholders. | [optional] 
**SendAt** | **DateTime** | Schedule delivery for a future RFC3339 time (≤ 30 days out). Omit or past &#x3D; send now. Cancel with DELETE /v1/messages/{id} while scheduled. | [optional] 
**Attachments** | [**List&lt;V1SendPostRequestAttachmentsInner&gt;**](V1SendPostRequestAttachmentsInner.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

