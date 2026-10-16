# Lockally.SDK.Model.SendEmail200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** |  | 
**Id** | **Guid** | Present on a test-mode send; absent when suppressed. | [optional] 
**MessageId** | **string** | RFC 5322 Message-ID. On a test send the domain is test.lockally.com. Absent when suppressed. | [optional] 
**Warning** | **string** | On a suppressed send, explains that nothing was sent. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

