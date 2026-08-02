# Lockally.SDK.Model.V1UsageGet200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MailboxesActive** | **int** | Mailboxes that are neither disabled nor soft-deleted. | 
**GeneratedAt** | **DateTime** | When this snapshot was generated, RFC 3339 UTC. | 
**MailboxesTotal** | **int** | All mailboxes for this tenant, including disabled/soft-deleted. | [optional] 
**DomainsVerified** | **int** | Domains that have passed DNS verification. | [optional] 
**DomainsTotal** | **int** |  | [optional] 
**MessagesSentLast60s** | **int** | Sends in the 60-second window ending now. Used by the rate-cap check. | [optional] 
**MessagesSentTodayUtc** | **int** | Sends since 00:00 UTC. Compared against &#x60;daily_msg_quota&#x60;. | [optional] 
**MessagesSentLast30d** | **int** | Rolling 30-day send count (not calendar month). | [optional] 
**BytesStored** | **long** | Lifetime sum of &#x60;messages.size_bytes&#x60; for this tenant. | [optional] 
**RateCapPerMin** | **int** | Per-tenant outbound rate cap (sends per minute). | [optional] 
**DailyMsgQuota** | **int** | Per-tenant daily send quota (UTC day boundary). | [optional] 
**WebhooksTotal** | **int** |  | [optional] 
**WebhooksPaused** | **int** | Webhook subscriptions auto-paused after 50 consecutive failures (LT2). | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

