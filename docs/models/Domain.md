# Lockally.SDK.Model.Domain

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**TenantId** | **Guid** |  | 
**VarDomain** | **string** |  | 
**VerificationToken** | **string** |  | 
**Verified** | **bool** |  | 
**DkimSelector** | **string** |  | 
**DkimPublicRecord** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**VerifiedAt** | **DateTime** |  | [optional] 
**Records** | [**List&lt;DNSRecord&gt;**](DNSRecord.md) | DNS records the tenant must publish under their own DNS. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

