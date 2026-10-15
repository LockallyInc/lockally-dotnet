# Lockally.SDK.Model.GetUserInsights200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**RecentlyAdded** | [**List&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] 
**RecentlySuspended** | [**List&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] 
**Inactive30d** | [**List&lt;UserEvent&gt;**](UserEvent.md) |  | [optional] 
**SeatsUsed** | **int** |  | [optional] 
**SeatsAlloc** | **int** |  | [optional] 
**SeatsCapped** | **bool** | True only on tiers with a hard seat cap (Free, Founder). On unlimited/per-seat tiers seats_alloc merely tracks the live mailbox count, so seats_used &#x3D;&#x3D; seats_alloc is normal and must not be read as &#39;at capacity&#39;. | [optional] 
**GeneratedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

