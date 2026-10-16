# Lockally.SDK.Model.Mailbox

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**TenantId** | **Guid** |  | 
**DomainId** | **Guid** |  | 
**Email** | **string** |  | 
**QuotaBytes** | **long** |  | 
**Disabled** | **bool** |  | 
**CreatedAt** | **DateTime** |  | 
**DisabledAt** | **DateTime** |  | [optional] 
**SoftDeletedAt** | **DateTime** |  | [optional] 
**HardDeleteAfter** | **DateTime** |  | [optional] 
**Password** | **string** | ONLY present on POST response when lockally generated the password. Shown once. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

