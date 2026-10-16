<!-- lockally-brand-header -->
<p align="center">
  <a href="https://lockally.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/LockallyInc/community/main/brand/lockup-dark.png">
      <img alt="Lockally" src="https://raw.githubusercontent.com/LockallyInc/community/main/brand/lockup-light.png" width="260">
    </picture>
  </a>
</p>
<!-- /lockally-brand-header -->

# Lockally.SDK

The official .NET client for the [Lockally](https://lockally.com) API. Send
and receive email from your own domain, manage domains and mailboxes, and
subscribe to delivery webhooks.

```bash
dotnet add package Lockally.SDK
```

- API reference: <https://developers.lockally.com/api-reference/overview/>
- Code examples: <https://developers.lockally.com/code-examples/>
- Dashboard, where you create an API key: <https://app.lockally.com>

## This client wires up through dependency injection

Unlike most of the Lockally SDKs, the .NET client is generated in the
**generic host** style. You do not construct an api object directly with
`new SendApi(config)`. You register it on a host and resolve the interface.
This is the usual .NET shape, and it is the single thing worth knowing before
you start.

### Minimal console app

```csharp
using Lockally.SDK.Api;
using Lockally.SDK.Client;
using Lockally.SDK.Extensions;
using Lockally.SDK.Model;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Hosting;

var host = Host.CreateDefaultBuilder(args)
    .ConfigureApi((context, services, options) =>
    {
        var key = Environment.GetEnvironmentVariable("LOCKALLY_API_KEY")!;
        options.AddTokens(new BearerToken(key));
    })
    .Build();

var api = host.Services.GetRequiredService<ISendApi>();

var body = new SendEmailRequest(
    from: "hello@yourcompany.com",
    to: new List<string> { "customer@example.com" },
    subject: "Welcome aboard",
    text: "Thanks for signing up.");

// POST /v1/send requires an Idempotency-Key. Any unique string per send,
// with a 24 hour dedupe window.
var result = await api.SendEmailAsync("welcome-user-42", body);

Console.WriteLine(result.StatusCode);
```

### ASP.NET Core

Register on the service collection instead, and inject `ISendApi` wherever
you need it:

```csharp
builder.Services.AddApi(options =>
{
    var key = builder.Configuration["Lockally:ApiKey"]!;
    options.AddTokens(new BearerToken(key));
});
```

## Check the status code, not just that the call returned

A **202** means the message was queued. A **200** means nothing was queued:
either every recipient was already suppressed, or you used an `lk_test_` key
and the send was simulated. Both are successes, and neither produces a real
delivery. Code that only checks for a 2xx will report sends that never
happened.

## Keys and scopes

Keys look like `lk_live_<prefix>_<secret>`, or `lk_test_<...>` for a test key
whose sends are simulated. Each endpoint requires a scope on the presented
key, and an under-scoped key returns `403` with the required scope named in
the problem detail.

Never ship a key in a distributed binary. For desktop or mobile, mint
short-lived tokens from your own backend.

## Errors

Failures are [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457)
`application/problem+json`. A `429` carries `Retry-After` in seconds; honour
it rather than retrying immediately, because retrying into a rate cap extends
the window.

## Generated, and what that means

This client is produced by OpenAPI Generator from Lockally's spec, so it can
never drift from the API and a new endpoint appears in every language at
once. Classes are named for the API group (`ISendApi`, `IDomainsApi`) and
methods for what they do (`SendEmailAsync`, `GetMessageAsync`).

**Method names changed in 0.3.0.** They were previously derived from the
route, so sending was `V1SendPost`. If you are upgrading from 0.2.0, rename
the calls: there is no deprecation shim, because a generated client cannot
carry one. The [changelog](https://developers.lockally.com/changelog/) has
the mapping.

## Support

- Questions: <https://github.com/LockallyInc/community/discussions>
- Account-specific problems: <mailto:support@lockally.com>
- Security: <mailto:security@lockally.com>

## Licence

See [LICENSE](./LICENSE).
