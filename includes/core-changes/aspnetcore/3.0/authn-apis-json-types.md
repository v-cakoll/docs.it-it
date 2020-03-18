---
ms.openlocfilehash: 494e792d63a611cdaedf3e40aa607cfbb0420ae4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901858"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="8342e-101">Autenticazione: tipi Newtonsoft.Json sostituiti</span><span class="sxs-lookup"><span data-stu-id="8342e-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="8342e-102">In ASP.NET Core 3.0, `Newtonsoft.Json` i tipi utilizzati `System.Text.Json` nelle API di autenticazione sono stati sostituiti con i tipi.</span><span class="sxs-lookup"><span data-stu-id="8342e-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="8342e-103">Ad eccezione dei seguenti casi, l'utilizzo di base dei pacchetti di autenticazione rimane inalterato:</span><span class="sxs-lookup"><span data-stu-id="8342e-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="8342e-104">Classi derivate dai provider OAuth, ad esempio quelle di [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span><span class="sxs-lookup"><span data-stu-id="8342e-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="8342e-105">Implementazioni avanzate di manipolazione delle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="8342e-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="8342e-106">Per ulteriori informazioni, vedere [dotnet/aspnetcore-7105](https://github.com/dotnet/aspnetcore/pull/7105).</span><span class="sxs-lookup"><span data-stu-id="8342e-106">For more information, see [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105).</span></span> <span data-ttu-id="8342e-107">Per una discussione, vedere [dotnet/aspnetcore-7289](https://github.com/dotnet/aspnetcore/issues/7289).</span><span class="sxs-lookup"><span data-stu-id="8342e-107">For discussion, see [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8342e-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="8342e-108">Version introduced</span></span>

<span data-ttu-id="8342e-109">3.0</span><span class="sxs-lookup"><span data-stu-id="8342e-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8342e-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="8342e-110">Recommended action</span></span>

<span data-ttu-id="8342e-111">Per le implementazioni OAuth derivate, `JObject.Parse` la `JsonDocument.Parse` modifica `CreateTicketAsync` più comune consiste nel sostituire con nell'override come illustrato [di seguito.](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40)</span><span class="sxs-lookup"><span data-stu-id="8342e-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="8342e-112">`JsonDocument` implementa `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="8342e-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="8342e-113">Nell'elenco seguente vengono descritte le modifiche note:</span><span class="sxs-lookup"><span data-stu-id="8342e-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="8342e-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType>diventa `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span><span class="sxs-lookup"><span data-stu-id="8342e-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="8342e-115">Tutte le implementazioni derivate di `ClaimAction` sono interessate in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="8342e-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="8342e-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="8342e-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="8342e-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="8342e-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="8342e-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext>è stato rimosso un vecchio `JObject` costruttore e l'altro sostituito con `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="8342e-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="8342e-119">La `User` proprietà `RunClaimActions` e il metodo sono stati aggiornati in modo che corrispondano.</span><span class="sxs-lookup"><span data-stu-id="8342e-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="8342e-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)>ora accetta un parametro di tipo `JsonDocument` anziché `JObject`.</span><span class="sxs-lookup"><span data-stu-id="8342e-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="8342e-121">La `Response` proprietà è stata aggiornata in modo che corrisponda.</span><span class="sxs-lookup"><span data-stu-id="8342e-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="8342e-122">`OAuthTokenResponse`è ora usa e getta `OAuthHandler`e sarà smaltito da .</span><span class="sxs-lookup"><span data-stu-id="8342e-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="8342e-123">Le implementazioni OAuth `ExchangeCodeAsync` derivate che esegue `JsonDocument` `OAuthTokenResponse`l'override non è necessario eliminare l'oggetto o .</span><span class="sxs-lookup"><span data-stu-id="8342e-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="8342e-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType>modificato `JObject` da `JsonDocument`a .</span><span class="sxs-lookup"><span data-stu-id="8342e-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="8342e-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType>modificato `JObject` da `JsonElement`a .</span><span class="sxs-lookup"><span data-stu-id="8342e-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="8342e-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType>cambiato da `JObject` `JsonElement`accettare a .</span><span class="sxs-lookup"><span data-stu-id="8342e-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> changed from accepting `JObject` to `JsonElement`.</span></span>

#### <a name="category"></a><span data-ttu-id="8342e-127">Category</span><span class="sxs-lookup"><span data-stu-id="8342e-127">Category</span></span>

<span data-ttu-id="8342e-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8342e-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8342e-129">API interessate</span><span class="sxs-lookup"><span data-stu-id="8342e-129">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
