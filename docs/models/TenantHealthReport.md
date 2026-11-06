# Lockally.SDK.Model.TenantHealthReport
The workspace health snapshot behind the console dashboard. DNS checks are live lookups, so a domain whose DNS cannot be read shows as a warning rather than an error.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**OverallScore** | **int** |  | 
**Checks** | [**List&lt;TenantHealthCheck&gt;**](TenantHealthCheck.md) |  | 
**GeneratedAt** | **DateTime** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

