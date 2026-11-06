# Lockally.SDK.Model.CreateApiKeyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Label** | **string** | Free-text identifier shown in the dashboard. | 
**Scopes** | **List&lt;CreateApiKeyRequest.ScopesEnum&gt;** | Allowed scopes on this key. | 
**Test** | **bool** | Issue a test key (&#x60;lk_test_&#x60; prefix). A test key accepts sends, records them and fires a simulated delivery webhook without sending mail, and counts against no limit or allowance.  | [optional] [default to false]
**ExpiresAt** | **DateTime** | Optional. When the key stops authenticating. Omit it for a key that does not expire. Must be in the future: an expiry already past would mint a key that fails its first request.  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

