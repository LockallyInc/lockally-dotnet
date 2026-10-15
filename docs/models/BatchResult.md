# Lockally.SDK.Model.BatchResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Index** | **int** |  | [optional] 
**Id** | **Guid** |  | [optional] 
**MessageId** | **string** |  | [optional] 
**Status** | **string** | \&quot;suppressed\&quot; means every recipient of that slot was on your suppression list, and it carries no id or message_id. \&quot;delivered\&quot; only appears on a test key: the send was simulated, not transmitted. | [optional] 
**Error** | **string** | Present when this message failed; the others are then absent. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

