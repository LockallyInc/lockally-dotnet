# Lockally.SDK.Model.APIKey

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**TenantId** | **Guid** |  | 
**Prefix** | **string** | 8-char public prefix; safe to store and display. | 
**Scopes** | **List&lt;string&gt;** |  | 
**Label** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**LastUsedAt** | **DateTime** |  | [optional] 
**RevokedAt** | **DateTime** |  | [optional] 
**Test** | **bool** | True for an lk_test_* key: the whole request path runs but a send never reaches the mail server and nothing counts against the account. | [optional] 
**ExpiresAt** | **DateTime** | When the key stops authenticating. Null means it does not expire, which is how every key behaved before expiry existed. Enforced at authentication, so the key fails the first request after this moment rather than whenever a sweep runs.  | [optional] 
**RotatedTo** | **Guid** | The successor issued by &#x60;POST /v1/api-keys/{id}/rotate&#x60;. Set on the PREDECESSOR, so you can see which key replaced this one while both still work through the overlap window.  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

