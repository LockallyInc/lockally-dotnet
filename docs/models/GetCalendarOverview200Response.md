# Lockally.SDK.Model.GetCalendarOverview200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**TotalCalendars** | **int** |  | [optional] 
**ActiveCalendars** | **int** | Calendars with an event created, edited or held in the last 30 days. | [optional] 
**SharedCalendars** | **int** | Calendars visible to the whole organization. | [optional] 
**EventsThisMonth** | **int** | Events on every calendar, in the account&#39;s own timezone. | [optional] 
**UpcomingOrgEvents** | **int** | Future events on organization-visible calendars. | [optional] 
**BookableResources** | **int** | Resources that are not disabled. | [optional] 
**AccessGranted** | **int** | People who own a calendar or are named on one. | [optional] 
**AccessOrgWide** | **int** | Everyone who can see an organization calendar; 0 when none exists. | [optional] 
**Activity** | [**List&lt;GetCalendarOverview200ResponseActivityInner&gt;**](GetCalendarOverview200ResponseActivityInner.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

