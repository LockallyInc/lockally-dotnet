# Lockally.SDK.Model.V1ApiKeysPost201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**TenantId** | **Guid** |  | 
**Prefix** | **string** | 8-char public prefix; safe to store and display. | 
**Scopes** | **List&lt;string&gt;** |  | 
**Label** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**Secret** | **string** | The full &#x60;lk_live_&lt;prefix&gt;_&lt;secret&gt;&#x60; token. Shown ONCE. | 
**LastUsedAt** | **DateTime** |  | [optional] 
**RevokedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

