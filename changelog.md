1.9.1
==========
### Bug Fixes:
**Microsoft.IdentityModel.* version="6.9" introduced a breaking change in the mapping of the User.Identity.Name claim**. Microsoft.Identity.Web 1.9, started leveraging Microsoft.IdentityModel 6.10 to improve resiliency. With this breaking change Microsoft Identity Web 1.9.1 has a temporary workaround in place until a new Microsoft.IdentityModel version is released with a fix. See issues [#1136](https://github.com/AzureAD/microsoft-identity-web/issues/1136) and [#1140](https://github.com/AzureAD/microsoft-identity-web/issues/1140) for details.

**Fix obsolete attribute and error message on `ReplyForbiddenWithWwwAuthenticateHeaderAsync`**. See issue [#1137](https://github.com/AzureAD/microsoft-identity-web/issues/1137) for details.

### Documentation:
**Fix Stackoverflow tags in ReadMe**. See issue [#1128](https://github.com/AzureAD/microsoft-identity-web/issues/1128).

1.9.0
==========
### New Features:
**Microsoft Identity Web now exposes a token provider that the Azure SDKs can use**. See [PR](https://github.com/AzureAD/microsoft-identity-web/pull/542) for details.

**Microsoft Identity Web now supports .NET Framework 4.6.2**. See issue [#1086](https://github.com/AzureAD/microsoft-identity-web/issues/1086).

**Microsoft Identity Web supports calls for regional STS for 1st party only**, this is due to MSAL.NET release [4.29](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/releases/tag/4.29.0), and `AzureRegion` is available via the `ConfidentialClientApplicationOptions`.

### Bug Fixes:
**Microsoft Identity Web now locks on the HttpContext, to better handle multi-threaded applications**. See issue [#1097](https://github.com/AzureAD/microsoft-identity-web/issues/1097) and [PR](https://github.com/AzureAD/microsoft-identity-web/pull/1082) and [PR](https://github.com/AzureAD/microsoft-identity-web/pull/1099).

### Fundamentals:
**Microsoft Identity Web now implements `LoggerMessage` for high performance logging**. See issue [#1105](https://github.com/AzureAD/microsoft-identity-web/issues/1105) for details.

**Performance improvements**. See PRs [#1089](https://github.com/AzureAD/microsoft-identity-web/pull/1089), [#1098](https://github.com/AzureAD/microsoft-identity-web/pull/1098), [#1092](https://github.com/AzureAD/microsoft-identity-web/pull/1092), and [#1085](https://github.com/AzureAD/microsoft-identity-web/pull/1085).

### Documentation:
**Documentation updated to show how to use `ClientCapabilities`**. See issue [#1071](https://github.com/AzureAD/microsoft-identity-web/issues/1071) and also the [wiki]( https://github.com/AzureAD/microsoft-identity-web/wiki/client-capabilities).

**Clear documentation on what is available in Microsoft Identity Web and when to use MSAL.NET, Microsoft Identity Web, or both**. See issue [#1057](https://github.com/AzureAD/microsoft-identity-web/issues/1057) and [Is MSAL.NET right for me?](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/Is-MSAL.NET-right-for-me%3F).

1.8.2
==========
Update to latest version of MSAL.NET 4.28.1.

1.8.1
==========
### Bug Fixes:
**With the L1/L2 cache updates in 1.8.0, if a cache item is found in the L1 cache, the L2 cache needs to be refreshed**. See issue [#1061](https://github.com/AzureAD/microsoft-identity-web/issues/1061) for details.

1.8.0
==========
### New Features:
**Microsoft Identity Web now provides a more sophisticated and performant L1/L2 (In Memory and Distributed) token cache**. See issue [#957](https://github.com/AzureAD/microsoft-identity-web/issues/957) for details.

**Related to the L1/L2 cache improvements, developers can determine how to proceed when the L2 (Distributed) cache fails, ex. the L2 cache is off-line**. See issue [#1042](https://github.com/AzureAD/microsoft-identity-web/issues/1042) for details.

**Related to the L1/L2 cache improvements, the `MemoryCacheOptions` are now exposed in the `MsalDistributedTokenCacheAdapterOptions` so developers can have control over the L1 (In Memory) cache, such as cache size**. See issue [#1048](https://github.com/AzureAD/microsoft-identity-web/issues/1048) for details.

**Microsoft Identity Web supports user assigned managed identity for certificate loading**. See issue [#1007](https://github.com/AzureAD/microsoft-identity-web/issues/1007) for details.

1.7.0
==========
### New Features:
**msidentity-app-sync is a command line tool that creates Microsoft identity platform applications in a tenant (AAD or B2C)** and updates the configuration code of your ASP.NET Core applications (mvc, webapp, blazorwasm, blazorwasm hosted, blazorserver). The tool can also be used to update code from an existing AAD/AAD B2C application. See https://aka.ms/msidentity-app-sync for details and [additional information on the experience in Visual Studio 16.9](https://github.com/AzureAD/microsoft-identity-web/blob/master/tools/app-provisioning-tool/vs2019-16.9-how-to-use.md). Get the tool via the [NuGet package](https://www.nuget.org/packages/msidentity-app-sync/). See issue [#954](https://github.com/AzureAD/microsoft-identity-web/issues/954), and [977](https://github.com/AzureAD/microsoft-identity-web/issues/977).

**Microsoft Identity Web now disables the ADAL cache lookup by default when calling into MSAL .NET**. If you have ADAL apps which share a cache with MSAL apps, you would want to set `LegacyCacheCompatibilityEnabled = true` in `appsettings.json`. Otherwise, there is a performance improvement when bypassing the ADAL cache lookup. See issue [#961](https://github.com/AzureAD/microsoft-identity-web/issues/961) for details.

**It's now possible to specify the X509KeyStorageFlags in the certificate description (both in the config file, or programmatically)**. This way if you want to use other storage flags than the default, it is possible.

### Bug Fixes:
**Remove obsolete attribute from `ValidateUserScopesAndAppRoles`**. See issue [#963](https://github.com/AzureAD/microsoft-identity-web/issues/963) and [#995](https://github.com/AzureAD/microsoft-identity-web/issues/995) for details.

1.6.0
==========
See [blog post](https://github.com/AzureAD/microsoft-identity-web/wiki/1.6.0) for details.

### New Features:
**Microsoft Identity Web templates now include a project template for Azure Functions**. See issue [#899](https://github.com/AzureAD/microsoft-identity-web/issues/899) for details.

**gRPC templates now include calling graph and downstream APIs**. See issue [#900](https://github.com/AzureAD/microsoft-identity-web/issues/900) for details.

**Microsoft Identity Web now exposes an AuthorizationFilter attribute to express accepted scopes on controllers, actions, or pages**. See issue [#849](https://github.com/AzureAD/microsoft-identity-web/issues/849) for details.

**When using the delegate override of `.EnableTokenAcquisitionToCallDownstreamApi`, you don't need to repeat the properties present in the Microsoft Identity Options ex. Instance, TenantId, ClientId, etc...**. See issue [#742](https://github.com/AzureAD/microsoft-identity-web/issues/742) for details.

**Microsoft Identity Web now exposes the `DefaultCertificateLoader`, which would be used when loading a certificate from a daemon application, or an ASP NET application, using MSAL .NET directly**. See issue [#952](https://github.com/AzureAD/microsoft-identity-web/issues/952) for details.

### Bug Fixes:
**Microsoft Identity Web now supports token decryption certificates rotation**. See issue [#905](https://github.com/AzureAD/microsoft-identity-web/issues/905) for details.

**Microsoft Identity Web now allows the AuthorizeForScopeAttribute to specify an alternate AuthenticationScheme**. See issue [#870](https://github.com/AzureAD/microsoft-identity-web/issues/870) for details.

1.5.1
==========
Update to the latest version of MSAL .NET (4.25), Microsoft Graph (3.22) and Microsoft Graph Beta (0.36.0-preview).

1.5.0
==========
### New Features:
**Microsoft Identity Web templates now include a project template for gRPC**. See issue [#628](https://github.com/AzureAD/microsoft-identity-web/issues/628) for details.

**Microsoft Identity Web now helps writing Azure Functions protected with Azure AD or Azure AD B2C**. See issue [#878](https://github.com/AzureAD/microsoft-identity-web/issues/878).

**The Microsoft Identity Web B2C templates now use the recommended `.b2clogin.com`** instead of `login.microsoftonline.com` by default. See issue [#792](https://github.com/AzureAD/microsoft-identity-web/issues/792) for details.

### Bug Fixes:
**In a Blazor server application, when the client app requests consent for the web API, the call would result in an infinite loop**. The consent screen is now correctly displayed. See issue [#847](https://github.com/AzureAD/microsoft-identity-web/issues/847) for details.

1.4.1
==========
### New Features:
**Microsoft Identity Web now leverages the logs available in MSAL .NET**. See the [wiki](https://github.com/AzureAD/microsoft-identity-web/wiki/Logging) for information on setting up the logs and how to enable Pii. See issue [#821](https://github.com/AzureAD/microsoft-identity-web/issues/821) for details.

1.4.0
==========
### New Features: 
**Starting in MSAL .NET 4.24, the `.WithForceRefresh()` parameter is passed to the on-behalf-of call**. Microsoft Identity Web now incudes it in the on-behalf-of call. It is false by default, as part of the `TokenAcquisitionOptions`. See issue [#811](https://github.com/AzureAD/microsoft-identity-web/issues/811) for details.

**Microsoft Identity Web now exposes the generic consent handler in Razor pages and MVC controllers in addition to Blazor pages (by registering it on a `IServiceCollection`)**. See issue [#805](https://github.com/AzureAD/microsoft-identity-web/issues/805) for details.

### Bug Fixes:
**Microsoft Identity Web was validating the issuer even when `ValidateIssuer` was set to false**. This is now fixed. See issue [#797](https://github.com/AzureAD/microsoft-identity-web/issues/797) for details.

**Microsoft Identity Web now uses the redirect URI if you provide it as part of the `ConfidentialClientApplicationOptions`**. See issue [#784](https://github.com/AzureAD/microsoft-identity-web/issues/784) for details.

**Microsoft Identity Web provides a better experience for app developers who use the legacy `login.microsoftonline.com/tfp/` authority for B2C applications**. See issue [#143](https://github.com/AzureAD/microsoft-identity-web/issues/143) for details.

**A tenanted authority must be used in the acquire token for app scenario**. If `common` or `organizations` is used, Microsoft Identity Web will throw an actionable exception. See issue [#793](https://github.com/AzureAD/microsoft-identity-web/issues/793) for details.

**The wrong constant values were used for LoginHint and DomainHint**. See issue [798](https://github.com/AzureAD/microsoft-identity-web/issues/798) and [PR](https://github.com/AzureAD/microsoft-identity-web/pull/812) for details.

**Microsoft Identity Web now supports individual auth with AAD external providers**. To enable this, you can now specify a null cookie scheme in `AddMicrosoftIdentityWebApp`. See issue [#133](https://github.com/AzureAD/microsoft-identity-web/issues/133) and issue [#809](https://github.com/AzureAD/microsoft-identity-web/issues/809).

1.3.0
==========
### New Features:
**Microsoft Identity Web now exposes token cache adapters for Memory and IDistributedCache for .NET 4.7.2**, so ASP .NET MVC developers can leverage the serializers. See issue [#741](https://github.com/AzureAD/microsoft-identity-web/issues/741) for details.

### Bug Fixes:
**Microsoft Identity Web now guards against an authority ending with `//`**. See issue [#747](https://github.com/AzureAD/microsoft-identity-web/issues/747) for details.

**During AJAX calls, Microsoft Identity Web ensures the redirect URI is a local redirect URI**. See issue [#746](https://github.com/AzureAD/microsoft-identity-web/issues/746).

**KeyVault flags are now included in the private key path for certificate fetching**. See issue [#762](https://github.com/AzureAD/microsoft-identity-web/issues/762) for details.

1.2.0
==========
### New Features:
**Microsoft Identity Web now supports App Services Authentication with Azure AD**. See https://aka.ms/ms-id-web/AppServicesAuth and issue [#8](https://github.com/AzureAD/microsoft-identity-web/issues/8) for details.

**Microsoft Identity Web now enables the usage of the `GraphServiceClient` to call the Graph APIs with app only permissions**. See https://aka.ms/ms-id-web/microsoftGraph and issue [#654](https://github.com/AzureAD/microsoft-identity-web/issues/654) for details.

**Microsoft Identity Web now supports a variety of generic extension methods for use with the downstream web API calls**. See issue [#537](https://github.com/AzureAD/microsoft-identity-web/issues/537) for details.

**To better support Conditional Access scenarios, `TokenAcquisitionOptions` now have a `Claims` property**. See issue [#677](https://github.com/AzureAD/microsoft-identity-web/issues/677) for details.

**Using AJAX to make calls to a .NET Core application is now possible with Microsoft Identity Web**. See issues [#642](https://github.com/AzureAD/microsoft-identity-web/issues/642) and [#603](https://github.com/AzureAD/microsoft-identity-web/issues/603).

**In order to enable web APIs called by daemon applications to handle tokens without a roles claim, Microsoft Identity Web now exposes a boolean property in `MicrosoftIdentityOptions`**. See issue [#707](https://github.com/AzureAD/microsoft-identity-web/issues/707) for details.

### Bug Fixes:
**The Microsoft.Identity.Web.UI DLL now includes strong name validation**. See issue [#682](https://github.com/AzureAD/microsoft-identity-web/issues/682).

**The `AadIssuerValidator` class no longer has a static `ConfigurationManager`, and is instead an injectable singleton**. See issue [#402](https://github.com/AzureAD/microsoft-identity-web/issues/402) for details.

**Microsoft Identity Web would try to add to the authorization header, at times, resulting in a format exception**. Now the existing header is removed and replaced with the current one. See issue [#673](https://github.com/AzureAD/microsoft-identity-web/issues/673) for details.

**In order to enable developers to use a backchannel proxy, Microsoft Identity Web now enables developers to configure the `IHttpClientFactory` to include a name option which will be passed to `CreateClient` via the `AadIssuerValidatorOptions`**. See https://aka.ms/ms-id-web/proxy and issue [#551](https://github.com/AzureAD/microsoft-identity-web/issues/551) for more details.

1.1.0
===========
### New Features:
**When using the InMemory token cache, Microsoft Identity Web enabled developers to `MemoryCacheOption`**, this can improve performance. See issue [#639](https://github.com/AzureAD/microsoft-identity-web/issues/639).

### Bug Fixes:
**The `.Clone()` in TokenValidationParameters has been removed as it is not needed**. See issue [#635](https://github.com/AzureAD/microsoft-identity-web/issues/635) for details.

**The `RequestContent` parameter in DownstreamWebApi is now being used as the `HttpRequestMessage.Content` if available**.See issue [#618](https://github.com/AzureAD/microsoft-identity-web/issues/618).

**Microsoft Identity Web now checks for the tenantId long-claim in AadIssuerValidator.GetTenantIdFromToken**. See issue [#617](https://github.com/AzureAD/microsoft-identity-web/issues/617) for details.

**In the blazorwasm-hosted templates, the Call Graph and Call Downstream Web Api options are now surfaced as separate pages and separate entries in the vertical menu**. See issue [509](https://github.com/AzureAD/microsoft-identity-web/issues/509).

**In `MicrosoftIdentityConsentAndConditionalAccessHandler.HandleException`, the redirect uri could be malformed, containing an extra `/`**. This has been fixed. See issue [#626](https://github.com/AzureAD/microsoft-identity-web/issues/626) for details.

### Fundamentals:
**Microsoft Identity Web has completed initial performance and load testing**. See [wiki article](https://github.com/AzureAD/microsoft-identity-web/wiki/performance) and issue [#88](https://github.com/AzureAD/microsoft-identity-web/issues/88) for details.

**Microsoft Identity Web dependencies are updated to the latest respective versions**. Also the blazorwasm template dependencies have been updated as well. See issues [#641](https://github.com/AzureAD/microsoft-identity-web/issues/641) and [#631](https://github.com/AzureAD/microsoft-identity-web/issues/631) for details.

1.0.0
===========
### New Features:
**Some constant values used in Microsoft Identity Web are available as public constants**. See feature request [#548](https://github.com/AzureAD/microsoft-identity-web/issues/548) for details.

**Microsoft Identity Web now sends basic telemetry data (sku and version) to AAD and AAD B2C**. See issue [#327](https://github.com/AzureAD/microsoft-identity-web/issues/327) for details.

**Implement `TokenAcquisitionOptions` which enable developers to customize the token aquisition integration with MSAL .NET**. Current options available are extra query parameters, force refresh, and correlation id. See issues [#561](https://github.com/AzureAD/microsoft-identity-web/issues/561), [#494](https://github.com/AzureAD/microsoft-identity-web/issues/494), and [#532](https://github.com/AzureAD/microsoft-identity-web/issues/532).

### Bug Fixes:
**Microsoft Identity Web now uses a scoped service for TokenAcquisitionServices when calling Microsoft Graph**. Previously a Singleton was used and this caused an infinite loop in Blazor ser_ver applications, as Blazor requires scoped services. See issues [#573](https://github.com/AzureAD/microsoft-identity-web/issues/573) and [#531](https://github.com/AzureAD/microsoft-identity-web/issues/531) for details.

**Now developers can specify the client secret in the web API scenario either in Microsoft Identity Options or in the Confidential Client Application Options**, previously it had to be set in both. See issue [#536](https://github.com/AzureAD/microsoft-identity-web/issues/536) for details.

**Web apps calling web APIs no longer require a `response_type` of `id_token`, so it no longer needs to be checked in the AAD portal app registration**. See issue [#589](https://github.com/AzureAD/microsoft-identity-web/issues/589).

### Fundamentals:
**Remove obsolete attributes for the 1.0.0 (GA) version**. See issue [#584](https://github.com/AzureAD/microsoft-identity-web/issues/584) for details.

0.4.0-preview
============
### New Features:
**`ITokenAcquisition` now exposes the `AuthenticationResult` for the user from MSAL**. See issue [#543](https://github.com/AzureAD/microsoft-identity-web/issues/543) for details.

**Now, to use Microsoft GraphServiceClient, you need to reference Microsoft.Identity.Web.MicrosoftGraph or Microsoft.Identity.Web.MicrosoftGraphBeta**. See issue [#506](https://github.com/AzureAD/microsoft-identity-web/issues/506) for details.

### Bug Fixes:
**`CallWebApiForUserAsync` handles a successful response better**. See issue [#503](https://github.com/AzureAD/microsoft-identity-web/issues/429) for details.

**Microsoft Identity Web can now handle two schemes in web APIs**. See issues [#429](https://github.com/AzureAD/microsoft-identity-web/issues/429), [#468](https://github.com/AzureAD/microsoft-identity-web/issues/468), and [#474](https://github.com/AzureAD/microsoft-identity-web/issues/474) for details.

### Fundamentals:
**Add integration test coverage for web app and web API scenarios**. Issues [#97](https://github.com/AzureAD/microsoft-identity-web/issues/97), [#95](https://github.com/AzureAD/microsoft-identity-web/issues/95), and [#102](https://github.com/AzureAD/microsoft-identity-web/issues/102).

0.3.1-preview
============
### Bug Fixes
**In B2C web app scenarios, only signing-in users, the password reset and edit profile redirects were not working**. Microsoft Identity Web now only sends the `response_type` of only `idToken` when in the web app scenario. See issue on [password reset](https://github.com/AzureAD/microsoft-identity-web/issues/467) and [edit profile](https://github.com/Azure-Samples/active-directory-aspnetcore-webapp-openidconnect-v2/issues/399) for details.

0.3.0-preview
============
### API Breaking Changes:
See https://aka.ms/ms-id-web/0.3.0-preview for more specific details.

Before | After
-- | --
services.AddMicrosoftWebAppAuthentication() | services.AddMicrosoftIdentityWebAppAuthentication()
services.AddAuthentication().AddMicrosoftWebApp() | services.AddAuthentication().AddMicrosoftIdentityWebApp()
services.AddMicrosoftWebApiAuthentication() | services.AddMicrosoftIdentityWebApiAuthentication()
services.AddAuthentication().AddMicrosoftWebApi() | services.AddAuthentication().AddMicrosoftIdentityWebApi()
services.AddAuthentication().AddMicrosoftWebApp().AddMicrosoftWebAppCallsWebApi() | services.AddAuthentication().AddMicrosoftIdentityWebApp().EnableTokenAcquisitionToCallDownstreamApi()
services.AddAuthentication().AddMicrosoftWebApi().AddMicrosoftWebApiCallsWebApi() | services.AddAuthentication().AddMicrosoftIdentityWebApi().EnableTokenAcquisitionToCallDownstreamApi()
services.AddInMemoryTokenCaches() | .EnableTokenAcquisitionToCallDownstreamApi().AddInMemoryTokenCaches()
services.AddDistributedTokenCaches() | .EnableTokenAcquisitionToCallDownstreamApi().AddDistributedTokenCaches()
services.AddSessionTokenCaches() | .EnableTokenAcquisitionToCallDownstreamApi().AddSessionTokenCaches()
services.AddMicrosoftGraph() | .EnableTokenAcquisitionToCallDownstreamApi().AddMicrosoftGraph()
services.AddDownstreamApiService() | .EnableTokenAcquisitionToCallDownstreamApi().AddDownstreamApi()

See issue [#378](https://github.com/AzureAD/microsoft-identity-web/issues/378) and the [wiki](https://github.com/AzureAD/microsoft-identity-web/wiki/0.3.0-preview) for more information on the new API.

**`AddInMemoryTokenCaches` method now accepts an optional `MsalMemoryTokenCacheOptions` delegate parameter**.  See issue for details: [#426](https://github.com/AzureAD/microsoft-identity-web/issues/426).

**`GetAccessTokenForAppAsync` method now accepts an optional `tenant` parameter**, which allows applications authorized in multiple tenants to request tokens.  See issue for details: [#413](https://github.com/AzureAD/microsoft-identity-web/issues/413).


### New Features:
**Microsoft Identity Web now provides methods that simplify calling Microsoft Graph and any downstream APIs**. See [wiki](https://github.com/AzureAD/microsoft-identity-web/wiki/0.3.0-preview) and issues for details: [#403](https://github.com/AzureAD/microsoft-identity-web/issues/403), [#427](https://github.com/AzureAD/microsoft-identity-web/issues/427).

**Project templates, samples, and dev apps were updated to use the new public API**.  See issues for details: [#453](https://github.com/AzureAD/microsoft-identity-web/issues/453), [#418](https://github.com/AzureAD/microsoft-identity-web/issues/418).

### Bug Fixes:
**Previously domain hint was added to the request only if the login hint was present also**. The presence of domain and login hints is now validated separately. See issue for details: [#415](https://github.com/AzureAD/microsoft-identity-web/issues/415).

**Fixed a `NullReferenceException` on `NavigationManager` that occurred on Blazor server with Azure SignalR when using a pre-rendering mode**. See issue for details: [#437](https://github.com/AzureAD/microsoft-identity-web/issues/437).

0.2.3-preview
============
### New features:
**`ReplyForbiddenWithWwwAuthenticateHeaderAsync` method in `ITokenAcquisition` now has an additional optional `HttpResponse` parameter**, which can be provided in cases when the current `HttpContext` is null.  See issue for details: [#414](https://github.com/AzureAD/microsoft-identity-web/issues/414).

**Enable Micorosoft.Identity.Web to work with any version of .NET 5.0** by setting dependencies version to `5.0.0-*` for `JwtBearer` and `OpenIdConnect` dependencies**. See issue for details: [#380](https://github.com/AzureAD/microsoft-identity-web/issues/380).

0.2.2-preview
============
### New features:
**The `AadIssuerValidator` class is now public**. See issue for details: [#332](https://github.com/AzureAD/microsoft-identity-web/issues/332).

### Bug fixes:
**Starting in 0.2.1-preview, a `MicrosoftIdentityWebChallengeUserException` was added, but customers might use the `MsalUiRequiredException`, for instance by the Graph SDK**. See issue for details: [#398](https://github.com/AzureAD/microsoft-identity-web/issues/398).

**In a multi-tenant scenario, when calling a downstream API, Microsoft Identity Web was not returning the token for the specific tenant ID**. The correct token based on the tenant, if specified, is returned. See issues for details: [#344](https://github.com/AzureAD/microsoft-identity-web/issues/344) and [MSAL .NET](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/issues/1965).

**When the scopes provided are invalid, an exception will be thrown in addition to recording a response back to the controller**. This ensures the controller does not continue processing as authentication is not possible. See issue for details: [#389](https://github.com/AzureAD/microsoft-identity-web/issues/389).

**When calling a downstream web API, Microsoft Identity Web now checks the token from the HttpContext instead of doing an acquire token silent call.** This will save on cycles as MSAL .NET already does the necessary cache look up. See issue for details: [#381](https://github.com/AzureAD/microsoft-identity-web/issues/381).

**When validating the application roles, only the first role claim was used, which would result in a failure with multiple roles**. Microsoft Identity Web now uses all the roles and throws an exception if the roles are invalid. See issue for details: [#374](https://github.com/AzureAD/microsoft-identity-web/issues/374).

**A more descriptive exception is thrown when a B2C issuer claim contains `tfp`**. See [wiki](https://github.com/AzureAD/microsoft-identity-web/wiki/Azure-AD-B2C-issuer-claim-support) and issue for details: [#274](https://github.com/AzureAD/microsoft-identity-web/issues/274).

0.2.1-preview
============
### New features:
**Microsoft Identity Web now supports the ComponentsWebAssembly-CSharp project templates from ASP.NET Core**. See issue for details: [#320](https://github.com/AzureAD/microsoft-identity-web/issues/320).

**Microsoft Identity Web now supports the BlazorServerWeb-CSharp project templates from ASP .NET Core**. See issue for details: [#319](https://github.com/AzureAD/microsoft-identity-web/issues/319).

**When using Azure AD B2C, developers can now specify which policy/user flow to use to acquire the token**. Microsoft Identity Web now exposes a user flow parameter, which allows developers to specify the policy/user flow to use with looking for tokens in the cache. See issue for details: [#27](https://github.com/AzureAD/microsoft-identity-web/issues/27).

### Bug fixes:
**Fixes `NullReferenceException` when acquiring a user token because of a null `HttpContext`**. This applies to scenarios like server-side Blazor apps, long-running processes, daemon apps. See issues for details: [#157](https://github.com/AzureAD/microsoft-identity-web/issues/157), [#10](https://github.com/AzureAD/microsoft-identity-web/issues/10), [#38](https://github.com/AzureAD/microsoft-identity-web/issues/38).

**When encountering a challenge from a Blazor page, Microsoft Identity Web could not handle the challenge in the same way it does for an MVC or Razor page**. The challenge from a Blazor page is now handled corrected. See issue for details: [#360](https://github.com/AzureAD/microsoft-identity-web/issues/360).

**When acquiring a token for a user in a server side Blazor app, a null reference exception was encountered because the `CurrentHttpContext` was null**. Microsoft Identity Web now uses a Blazor specific class `AuthenticationStateProvider` to determine the current user. See issue for details: [#157](https://github.com/AzureAD/microsoft-identity-web/issues/157).

**In the templates, `CallWebApi` is an async method and now named accordingly, `CallWebApiAsync`**. See issue for details: [#357](https://github.com/AzureAD/microsoft-identity-web/issues/357).

**Microsoft Identity Web now creates a `HttpRequestMessage` to append the authorization header with the bearer token**. See issue for details: [350](https://github.com/AzureAD/microsoft-identity-web/issues/350).

**In the case of no authentication, the templates no longer support the usage of `--call-graph` and `--call-webapi-url`**. See issue for details: [337](https://github.com/AzureAD/microsoft-identity-web/issues/337).

**Now that Microsoft Identity Web can specify the AAD B2C tokens by user flow, the correct method, `GetAccountAsync()` can be called for confidential clients**. See issue for details: [#295](https://github.com/AzureAD/microsoft-identity-web/issues/295).

### Fundamentals:
**Microsoft Identity Web has error and log messages as constants**. See issue for details: [#261](https://github.com/AzureAD/microsoft-identity-web/issues/261).

0.2.0-preview
============
### API breaking changes:
Before | After
-- | --
services.AddSignIn() | services.AddMicrosoftWebAppAuthentication()
services.AddSignIn() | services.AddAuthentication().AddMicrosoftWebApp()
services.AddProtectedWebApi() | services.AddMicrosoftWebApiAuthentication()
services.AddProtectedWebApi() | services.AddAuthentication().AddMicrosoftWebApi()
.AddWebAppCallsProtectedWebApi() | .AddMicrosoftWebAppCallsWebApi()
.AddProtectedWebApiCallsWebApi() | .AddMicrosoftWebApiCallsWebApi()

- See the [wiki](https://aka.ms/ms-id-web/net5) for migration assistance and more information on the new API.
- Rename `MsalMemoryTokenCacheOptions.SlidingExpiration` to align with ASP.NET Core and use `AbsoluteExpirationRelativeToNow`. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/250).
- Removed the `ForceHttpsRedirectUris`, `RedirectUri`, and `PostLogoutRedirectUri` options from `MicrosoftIdentityOptions`. ASP.NET Core recommends the [following guidance](https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/proxy-load-balancer?view=aspnetcore-3.1) on working with proxies. See [issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/223).
- Removed the `SingletonTokenAcquisition` property from `MicrosoftIdentityOptions`. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/249).
- Microsoft Identity Web now has an `MsalDistributedTokenCacheAdapterOptions` class inheriting from `DistributedCacheEntryOptions` so the token cache serialization can expose their own options. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/251).

### New Features:
**Microsoft Identity Web implements the C# 8.0 nullable standard**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/15).

**Microsoft Identity Web now validates the app roles for a web API, for example a web API called by a daemon application**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/131).

**Microsoft Identity Web now supports .NET 5.0**, in addition to .NET Core 3.1. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/194).

**The project templates now have an option to generate the call to a downstream web API, or a call to Microsoft Graph**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/196).

**Microsoft Identity Web now has the ability to specify custom cookie options in the `AddMicrosoftWebApp` methods**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/237).

### Bug Fixes:
**When accessing KeyVault, storage flags need to be used, as there is no user profile**. The correct storage flags are now used. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/219).

**Uses the recommended workaround for the clients incompatible with the `SameSite=None` cookie attribute**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/238).

**Fixed a dependency injection anti-pattern when resolving `ITokenAcquisition`**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/240).

**The `TokenValidationParameters` are now cloned before using**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/241).

**Microsoft Identity Web now throws a `SecurityTokenValidationException`**, when there is an invalid audience. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/242).

**Microsoft Identity Web no longer throws an exception if the user sets the custom audiences**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/243).

**Removed multiple calls to `HandleCodeRedemption` in `TokenAcquisition`**. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/246).

**Fixes to the `MsalSessionTokenCacheProvider`**, such as removing the static lock object and removing the session commit. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/252).

**In the `AccountController`, Microsoft Identity Web now uses `IOptions` instead of `IOptionsMonitor`**, for consistency. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/232).

**Microsoft Identity Web no longer calls the `BuildServiceProvider` in the configuration methods** and uses a more appropriate `Configure` overload that provides the required `IServiceProvider` instance. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/234).

**Microsoft Identity Web now uses the `SuggestedCacheKey`** returned in the `TokenCacheNotificationArgs` from MSAL to determine the correct cache key. This enables the removal of several lines of code and the use of the `HttpContext.User`. See issue [235](https://github.com/AzureAD/microsoft-identity-web/issues/235), [248](https://github.com/AzureAD/microsoft-identity-web/issues/248), [273](https://github.com/AzureAD/microsoft-identity-web/issues/273), and [222](https://github.com/AzureAD/microsoft-identity-web/issues/222) for details.

**Microsoft Identity Web now retrieves the `client_info` data directly from the protocol message**. See [issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/245).

0.1.5-preview
============
### New Features:
**Microsoft Identity Web supports certificates.** The developer can now use client and token decryption certificates, which can be retrieved from a variety of sources, like Azure Key Vault, certificate store, a Base54 encoded string, and more. The location of the certificate can be specified in a configuration file or programmatically. See [issue](https://github.com/AzureAD/microsoft-identity-web/issues/165) and [wiki](https://github.com/AzureAD/microsoft-identity-web/wiki/Using-certificates) for more details.

**Microsoft Identity Web now allows specifying if the x5c claim (the public key of the certificate) should be sent to the STS.** Sending the x5c enables easy certificate rollover. To enable this behavior set the `SendX5C` property in the configuration file. See [issue](https://github.com/AzureAD/microsoft-identity-web/issues/197) for more details.

**Microsoft Identity Web provides an option to force redirect URIs to use the HTTPS scheme,** which can be useful in certain scenarios, like app deployment in a container. To enable this behavior set `ForceHttpsRedirectUris` property in the configuration file. See [issue](https://github.com/AzureAD/microsoft-identity-web/issues/175) for more details.

### Bug Fixes:
**Microsoft Identity Web uses `System.Text.Json` namespace instead of `Newtonsoft.Json` for working with JSON.** See [issue](https://github.com/AzureAD/microsoft-identity-web/issues/182) for more details.

**The documentation now correctly specifies that `ClaimsPrincipalExtensions.GetNameIdentifierId` returns a `uid` claim value.** See [issue](https://github.com/AzureAD/microsoft-identity-web/issues/171) for more details.

0.1.4-preview
============
New Features:
**Microsoft Identity Web provides an option to specify if the token acquisition service should be a singleton**. See [issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/1).

Bug Fixes:
**When logging in with an unauthorized account, the user was redirected to `/Account/AccessDenied` which did not exist**. Microsoft Identity Web UI now properly sets the path on the scheme with the same name. See [issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/117).

**In the context of a guest account, Microsoft Identity Web used the `loginHint` to determine the guest account for accessing the MSAL .NET cache**. Now, Microsoft Identity Web retrieves `user_info` from the authorization server and is able to determine the unique object identifier for guest accounts. See [issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/18).

0.1.3-preview
============
New Features:
**Microsoft Identity Web now allows developers to not pass any scope value in `AddWebAppCallsProtectedWebApi`**. See [issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/14).

**When working with containers or reverse proxies, being able to specify the redirectUri and postLogoutRedirectUri is important.** Microsoft Identity Web now allows the setting of the RedirectUri and PostLogoutRedirectUri as part of the `MicrosoftIdentityOptions`. See [Issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/115).

Bug Fixes:
**The AddProtectedWebApiCallsProtectedWebApi method registers an event handler for OnTokenValidated without preserving any existing registered event handlers.** Now events are chained correctly. See [issue for details](https://github.com/AzureAD/microsoft-identity-web/issues/154).

**Depending on the endpoint, v1.0 or v2.0, and if the application is B2C or not, the default format of the `aud` value in the token will be different.** Microsoft Identity Web now looks at these parameters to validate the audience.

0.1.2-preview
============
New Features:
**Microsoft Identity Web now uses an IHttpClientFactory to implement resilient HTTP requests**. The ASP.NET Core IHttpClientFactory manages the pooling and lifetime of the underlying HttpClientMessageHandler instances, which avoids port exhaustion and common DNS problems that occur when manually managing HttpClient lifetimes. More details on this feature [here](https://github.com/AzureAD/microsoft-identity-web/issues/6).

Bug Fixes:
Performance improvement: **AadIssuerValidator class now caches the authority aliases under the correct cache key**. See [issue](https://github.com/AzureAD/microsoft-identity-web/issues/51) for more details.

**When not including the ClientSecret in appsettings.json, a null reference exception was thrown when acquiring the authorization code with MSAL.NET**. Microsoft Identity Web now checks all the required options and responds with actionable error messages if any are missing. See [issue](https://github.com/AzureAD/microsoft-identity-web/issues/66) for more details.

0.1.1-preview
============
New Features:
**Microsoft Identity Web now surfaces the ClaimConstants class**. This allows developers to build a unique ClaimsPrincipal. [See issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/100)

Bug Fixes:
**`AddSignIn()` now provides a more robust processing of authorities accepting them to end in `/` or not**. [See issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/19)

**Setting the `ValidAudiences` in `AddProtectedWebApi()` now accepts any custom audience (any string)**. [See issue for more details](https://github.com/AzureAD/microsoft-identity-web/issues/52)

0.1.0-preview
============
This is the first preview NuGet package for [Microsoft Identity Web](https://github.com/AzureAD/microsoft-identity-web/wiki).
