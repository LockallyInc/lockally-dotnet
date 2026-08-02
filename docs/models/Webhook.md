# Lockally.SDK.Model.Webhook

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**TenantId** | **Guid** |  | 
**Url** | **string** |  | 
**Events** | **List&lt;string&gt;** |  | 
**Paused** | **bool** |  | 
**ConsecutiveFailures** | **int** |  | 
**CreatedAt** | **DateTime** |  | 
**PausedAt** | **DateTime** |  | [optional] 
**LastSuccessAt** | **DateTime** |  | [optional] 
**LastFailureAt** | **DateTime** |  | [optional] 
**SigningSecret** | **string** | Hex-encoded HMAC-SHA256 key. Present ONLY on POST response. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

