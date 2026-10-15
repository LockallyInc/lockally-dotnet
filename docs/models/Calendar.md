# Lockally.SDK.Model.Calendar

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** |  | 
**TenantId** | **Guid** |  | 
**Name** | **string** |  | 
**Visibility** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**Color** | **string** |  | [optional] 
**OwnerEmail** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**CalendarType** | **string** | What the calendar is for. Separate from visibility, which is who may see it: a team calendar can be open to everyone and a department one restricted to named people. \&quot;personal\&quot; is a person&#39;s own and is not listed in the console&#39;s management table.  | [optional] 
**OwnerUnit** | **string** | The owning department or office. Empty on a personal calendar, which is owned by owner_email. | [optional] 
**AccessDepartment** | **string** | Which department may see it, when visibility is \&quot;department\&quot;. Matched against the department recorded on a user, so access follows a person between departments with no membership list to maintain.  | [optional] 
**Status** | **string** | Archived keeps the calendar, its events and its feed, and stops it taking new events. | [optional] 
**FeedUrl** | **string** |  | [optional] 
**EventCount** | **int** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

