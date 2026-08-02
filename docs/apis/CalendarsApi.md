# Lockally.SDK.Api.CalendarsApi

All URIs are relative to *https://api.lockally.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddCalendarMember**](CalendarsApi.md#addcalendarmember) | **POST** /v1/calendars/{id}/members | Add a member to a calendar |
| [**CreateCalendar**](CalendarsApi.md#createcalendar) | **POST** /v1/calendars | Create a calendar |
| [**CreateCalendarEvent**](CalendarsApi.md#createcalendarevent) | **POST** /v1/calendars/{id}/events | Create an event in a calendar |
| [**CreateCalendarIntegration**](CalendarsApi.md#createcalendarintegration) | **POST** /v1/calendar-integrations | Create a calendar integration |
| [**DeleteCalendar**](CalendarsApi.md#deletecalendar) | **DELETE** /v1/calendars/{id} | Delete a calendar |
| [**DeleteCalendarEvent**](CalendarsApi.md#deletecalendarevent) | **DELETE** /v1/calendars/{id}/events/{eventId} | Delete a calendar event |
| [**DeleteCalendarIntegration**](CalendarsApi.md#deletecalendarintegration) | **DELETE** /v1/calendar-integrations/{id} | Delete a calendar integration |
| [**GetCalendar**](CalendarsApi.md#getcalendar) | **GET** /v1/calendars/{id} | Get a calendar |
| [**GetCalendarPolicies**](CalendarsApi.md#getcalendarpolicies) | **GET** /v1/calendar-policies | Get calendar policies |
| [**GetCalendarSecurity**](CalendarsApi.md#getcalendarsecurity) | **GET** /v1/calendar-security | Get calendar security overview |
| [**ListCalendarEvents**](CalendarsApi.md#listcalendarevents) | **GET** /v1/calendars/{id}/events | List events in a calendar |
| [**ListCalendarIntegrations**](CalendarsApi.md#listcalendarintegrations) | **GET** /v1/calendar-integrations | List calendar integrations |
| [**ListCalendarMembers**](CalendarsApi.md#listcalendarmembers) | **GET** /v1/calendars/{id}/members | List calendar members |
| [**ListCalendars**](CalendarsApi.md#listcalendars) | **GET** /v1/calendars | List calendars |
| [**RemoveCalendarMember**](CalendarsApi.md#removecalendarmember) | **DELETE** /v1/calendars/{id}/members/{memberId} | Remove a member from a calendar |
| [**SyncCalendarIntegration**](CalendarsApi.md#synccalendarintegration) | **POST** /v1/calendar-integrations/{id}/sync | Trigger sync for a calendar integration |
| [**UpdateCalendar**](CalendarsApi.md#updatecalendar) | **PATCH** /v1/calendars/{id} | Update a calendar |
| [**UpdateCalendarEvent**](CalendarsApi.md#updatecalendarevent) | **PATCH** /v1/calendars/{id}/events/{eventId} | Update a calendar event |
| [**UpdateCalendarIntegration**](CalendarsApi.md#updatecalendarintegration) | **PATCH** /v1/calendar-integrations/{id} | Update a calendar integration |
| [**UpdateCalendarMember**](CalendarsApi.md#updatecalendarmember) | **PATCH** /v1/calendars/{id}/members/{memberId} | Update a calendar member&#39;s role |
| [**UpdateCalendarPolicies**](CalendarsApi.md#updatecalendarpolicies) | **PATCH** /v1/calendar-policies | Update calendar policies |

<a id="addcalendarmember"></a>
# **AddCalendarMember**
> CalendarMember AddCalendarMember (Guid id, AddCalendarMemberRequest addCalendarMemberRequest)

Add a member to a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **addCalendarMemberRequest** | [**AddCalendarMemberRequest**](AddCalendarMemberRequest.md) |  |  |

### Return type

[**CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Member added |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createcalendar"></a>
# **CreateCalendar**
> Calendar CreateCalendar (CreateCalendarRequest createCalendarRequest)

Create a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCalendarRequest** | [**CreateCalendarRequest**](CreateCalendarRequest.md) |  |  |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Calendar created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createcalendarevent"></a>
# **CreateCalendarEvent**
> CalendarEvent CreateCalendarEvent (Guid id, CreateCalendarEventRequest createCalendarEventRequest)

Create an event in a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **createCalendarEventRequest** | [**CreateCalendarEventRequest**](CreateCalendarEventRequest.md) |  |  |

### Return type

[**CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Event created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createcalendarintegration"></a>
# **CreateCalendarIntegration**
> CalendarIntegration CreateCalendarIntegration (CreateCalendarIntegrationRequest createCalendarIntegrationRequest)

Create a calendar integration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCalendarIntegrationRequest** | [**CreateCalendarIntegrationRequest**](CreateCalendarIntegrationRequest.md) |  |  |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Integration created |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletecalendar"></a>
# **DeleteCalendar**
> void DeleteCalendar (Guid id)

Delete a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletecalendarevent"></a>
# **DeleteCalendarEvent**
> void DeleteCalendarEvent (Guid id, Guid eventId)

Delete a calendar event


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **eventId** | **Guid** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletecalendarintegration"></a>
# **DeleteCalendarIntegration**
> void DeleteCalendarIntegration (Guid id)

Delete a calendar integration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getcalendar"></a>
# **GetCalendar**
> Calendar GetCalendar (Guid id)

Get a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar details |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getcalendarpolicies"></a>
# **GetCalendarPolicies**
> CalendarPolicies GetCalendarPolicies ()

Get calendar policies


### Parameters
This endpoint does not need any parameter.
### Return type

[**CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar policies |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getcalendarsecurity"></a>
# **GetCalendarSecurity**
> GetCalendarSecurity200Response GetCalendarSecurity ()

Get calendar security overview


### Parameters
This endpoint does not need any parameter.
### Return type

[**GetCalendarSecurity200Response**](GetCalendarSecurity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar security overview |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcalendarevents"></a>
# **ListCalendarEvents**
> ListCalendarEvents200Response ListCalendarEvents (Guid id, DateTime from = null, DateTime to = null)

List events in a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |

### Return type

[**ListCalendarEvents200Response**](ListCalendarEvents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendar events |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcalendarintegrations"></a>
# **ListCalendarIntegrations**
> ListCalendarIntegrations200Response ListCalendarIntegrations ()

List calendar integrations


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListCalendarIntegrations200Response**](ListCalendarIntegrations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendar integrations |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcalendarmembers"></a>
# **ListCalendarMembers**
> ListCalendarMembers200Response ListCalendarMembers (Guid id)

List calendar members


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**ListCalendarMembers200Response**](ListCalendarMembers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendar members |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcalendars"></a>
# **ListCalendars**
> ListCalendars200Response ListCalendars ()

List calendars


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListCalendars200Response**](ListCalendars200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of calendars |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="removecalendarmember"></a>
# **RemoveCalendarMember**
> void RemoveCalendarMember (Guid id, Guid memberId)

Remove a member from a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **memberId** | **Guid** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No content |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="synccalendarintegration"></a>
# **SyncCalendarIntegration**
> CalendarIntegration SyncCalendarIntegration (Guid id)

Trigger sync for a calendar integration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sync initiated |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatecalendar"></a>
# **UpdateCalendar**
> Calendar UpdateCalendar (Guid id, UpdateCalendarRequest updateCalendarRequest)

Update a calendar


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **updateCalendarRequest** | [**UpdateCalendarRequest**](UpdateCalendarRequest.md) |  |  |

### Return type

[**Calendar**](Calendar.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatecalendarevent"></a>
# **UpdateCalendarEvent**
> CalendarEvent UpdateCalendarEvent (Guid id, Guid eventId, UpdateCalendarEventRequest updateCalendarEventRequest)

Update a calendar event


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **eventId** | **Guid** |  |  |
| **updateCalendarEventRequest** | [**UpdateCalendarEventRequest**](UpdateCalendarEventRequest.md) |  |  |

### Return type

[**CalendarEvent**](CalendarEvent.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Event updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatecalendarintegration"></a>
# **UpdateCalendarIntegration**
> CalendarIntegration UpdateCalendarIntegration (Guid id, UpdateCalendarIntegrationRequest updateCalendarIntegrationRequest)

Update a calendar integration


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **updateCalendarIntegrationRequest** | [**UpdateCalendarIntegrationRequest**](UpdateCalendarIntegrationRequest.md) |  |  |

### Return type

[**CalendarIntegration**](CalendarIntegration.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Integration updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatecalendarmember"></a>
# **UpdateCalendarMember**
> CalendarMember UpdateCalendarMember (Guid id, Guid memberId, UpdateCalendarMemberRequest updateCalendarMemberRequest)

Update a calendar member's role


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **Guid** |  |  |
| **memberId** | **Guid** |  |  |
| **updateCalendarMemberRequest** | [**UpdateCalendarMemberRequest**](UpdateCalendarMemberRequest.md) |  |  |

### Return type

[**CalendarMember**](CalendarMember.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Member updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |
| **404** | Resource not found under the calling tenant. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatecalendarpolicies"></a>
# **UpdateCalendarPolicies**
> CalendarPolicies UpdateCalendarPolicies (UpdateCalendarPoliciesRequest updateCalendarPoliciesRequest)

Update calendar policies


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateCalendarPoliciesRequest** | [**UpdateCalendarPoliciesRequest**](UpdateCalendarPoliciesRequest.md) |  |  |

### Return type

[**CalendarPolicies**](CalendarPolicies.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json, application/problem+json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendar policies updated |  -  |
| **400** | Malformed request. |  -  |
| **401** | Missing, malformed, or invalid API key. |  -  |
| **403** | API key lacks the required scope. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

