# Created with Openapi Generator

<a id="cli"></a>
## Creating the library
Create a config.yaml file similar to what is below, then run the following powershell command to generate the library `java -jar "<path>/openapi-generator/modules/openapi-generator-cli/target/openapi-generator-cli.jar" generate -c config.yaml`

```yaml
generatorName: csharp
inputSpec: ../docs/openapi.yaml
outputDir: out

# https://openapi-generator.tech/docs/generators/csharp
additionalProperties:
  packageGuid: '{4B5C9ED2-0F26-435C-98BC-00B8992B4652}'

# https://openapi-generator.tech/docs/integrations/#github-integration
# gitHost:
# gitUserId:
# gitRepoId:

# https://openapi-generator.tech/docs/globals
# globalProperties:

# https://openapi-generator.tech/docs/customization/#inline-schema-naming
# inlineSchemaOptions:

# https://openapi-generator.tech/docs/customization/#name-mapping
# modelNameMappings:
# nameMappings:

# https://openapi-generator.tech/docs/customization/#openapi-normalizer
# openapiNormalizer:

# templateDir: https://openapi-generator.tech/docs/templating/#modifying-templates

# releaseNote:
```

<a id="usage"></a>
## Using the library in your project

```cs
using Microsoft.Extensions.Hosting;
using Microsoft.Extensions.DependencyInjection;
using Lockally.SDK.Api;
using Lockally.SDK.Client;
using Lockally.SDK.Model;
using Org.OpenAPITools.Extensions;

namespace YourProject
{
    public class Program
    {
        public static async Task Main(string[] args)
        {
            var host = CreateHostBuilder(args).Build();
            var api = host.Services.GetRequiredService<IAddOnsApi>();
            IActivateAddOnApiResponse apiResponse = await api.ActivateAddOnAsync("todo");
            ActivateAddOn200Response? model = apiResponse.Ok();
        }

        public static IHostBuilder CreateHostBuilder(string[] args) => Host.CreateDefaultBuilder(args)
          .ConfigureApi((context, services, options) =>
          {
              // The type of token here depends on the api security specifications
              // Available token types are ApiKeyToken, BasicToken, BearerToken, HttpSigningToken, and OAuthToken.
              BearerToken token = new("<your token>");
              options.AddTokens(token);

              // optionally choose the method the tokens will be provided with, default is RateLimitProvider
              options.UseProvider<RateLimitProvider<BearerToken>, BearerToken>();

              options.ConfigureJsonOptions((jsonOptions) =>
              {
                  // your custom converters if any
              });

              options.AddApiHttpClients(client =>
              {
                  // client configuration
              }, builder =>
              {
                  builder
                      .AddRetryPolicy(2)
                      .AddTimeoutPolicy(TimeSpan.FromSeconds(5))
                      .AddCircuitBreakerPolicy(10, TimeSpan.FromSeconds(30));
                      // add whatever middleware you prefer
                  }
              );
          });
    }
}
```
<a id="questions"></a>
## Questions

- What about HttpRequest failures and retries?
  Configure Polly in the IHttpClientBuilder
- How are tokens used?
  Tokens are provided by a TokenProvider class. The default is RateLimitProvider which will perform client side rate limiting.
  Other providers can be used with the UseProvider method.
- Does an HttpRequest throw an error when the server response is not Ok?
  It depends how you made the request. If the return type is ApiResponse<T> no error will be thrown, though the Content property will be null.
  StatusCode and ReasonPhrase will contain information about the error.
  If the return type is T, then it will throw. If the return type is TOrDefault, it will return null.
- How do I validate requests and process responses?
  Use the provided On and After partial methods in the api classes.

## Api Information
- appName: lockally control plane
- appVersion: 0.1.0
- appDescription: The lockally control plane lets integrators and direct customers manage everything except actual mail data flow (which uses standard JMAP / IMAP / SMTP-submission against the data plane endpoints).  **Authentication.** All &#x60;/v1/_*&#x60; endpoints require a Bearer API key in the &#x60;Authorization&#x60; header. Keys are formatted &#x60;lk_live_&lt;8-char-prefix&gt;_&lt;32-char-secret&gt;&#x60;, or &#x60;lk_test_&lt;...&gt;&#x60; for a test key. Create keys in the dashboard, or with &#x60;POST /v1/api-keys&#x60; using a key that holds &#x60;tenant:admin&#x60;.  The key&#39;s plan is checked on every request, so a key stops working if the account moves to a plan without API access, and works again if it moves back.  **Errors.** Failures return [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457) &#x60;application/problem+json&#x60; documents.  **Scopes.** Each endpoint requires a specific scope on the presented key. Insufficient scope returns &#x60;403&#x60; with the required scope name in &#x60;detail&#x60;. 

## Build
This C# SDK is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project.

- SDK version: 0.3.2
- Generator version: 7.23.0
- Build package: org.openapitools.codegen.languages.CSharpClientCodegen
