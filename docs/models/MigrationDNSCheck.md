# Lockally.SDK.Model.MigrationDNSCheck
Live DNS readiness of the destination domains, for deciding when to cut over. `ready` is true only when every domain's MX points at Lockally and its SPF authorises it.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Ready** | **bool** |  | 
**Domains** | [**List&lt;MigrationDomainDNS&gt;**](MigrationDomainDNS.md) |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

