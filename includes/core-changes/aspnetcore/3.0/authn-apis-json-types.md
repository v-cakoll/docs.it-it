---
ms.openlocfilehash: ad451329d7b9ec15bc8b3c49159346d79944d692
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394257"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="bf3bf-101">Autenticazione: tipi Newtonsoft. JSON sostituiti</span><span class="sxs-lookup"><span data-stu-id="bf3bf-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="bf3bf-102">In ASP.NET Core 3,0 i tipi `Newtonsoft.Json` usati nelle API di autenticazione sono stati sostituiti con i tipi `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="bf3bf-103">Eccetto nei casi seguenti, l'utilizzo di base dei pacchetti di autenticazione rimane inalterato:</span><span class="sxs-lookup"><span data-stu-id="bf3bf-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="bf3bf-104">Classi derivate dai provider OAuth, ad esempio quelle di [ASPNET-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span><span class="sxs-lookup"><span data-stu-id="bf3bf-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="bf3bf-105">Implementazioni avanzate di manipolazione delle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="bf3bf-106">Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 7105](https://github.com/aspnet/AspNetCore/pull/7105).</span><span class="sxs-lookup"><span data-stu-id="bf3bf-106">For more information, see [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105).</span></span> <span data-ttu-id="bf3bf-107">Per informazioni, vedere [ASPNET/AspNetCore # 7289](https://github.com/aspnet/AspNetCore/issues/7289).</span><span class="sxs-lookup"><span data-stu-id="bf3bf-107">For discussion, see [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bf3bf-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bf3bf-108">Version introduced</span></span>

<span data-ttu-id="bf3bf-109">3.0</span><span class="sxs-lookup"><span data-stu-id="bf3bf-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bf3bf-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bf3bf-110">Recommended action</span></span>

<span data-ttu-id="bf3bf-111">Per le implementazioni OAuth derivate, la modifica più comune consiste nel sostituire `JObject.Parse` con `JsonDocument.Parse` nell'override `CreateTicketAsync`, come illustrato di [seguito](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span><span class="sxs-lookup"><span data-stu-id="bf3bf-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="bf3bf-112">`JsonDocument` implementa `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="bf3bf-113">Nell'elenco seguente vengono descritte le modifiche note:</span><span class="sxs-lookup"><span data-stu-id="bf3bf-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="bf3bf-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> diventa `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="bf3bf-115">Tutte le implementazioni derivate di `ClaimAction` sono interessate in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="bf3bf-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="bf3bf-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="bf3bf-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="bf3bf-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="bf3bf-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> ha rimosso un costruttore precedente e l'altro ha sostituito `JObject` con `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="bf3bf-119">La proprietà `User` e il metodo `RunClaimActions` sono stati aggiornati in modo che corrispondano.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="bf3bf-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> ora accetta un parametro di tipo `JsonDocument` invece di `JObject`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="bf3bf-121">La proprietà `Response` è stata aggiornata in modo da corrispondere.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="bf3bf-122">`OAuthTokenResponse` è ora monouso e verrà eliminato da `OAuthHandler`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="bf3bf-123">Le implementazioni OAuth derivate che eseguono l'override di `ExchangeCodeAsync` non devono eliminare il `JsonDocument` o `OAuthTokenResponse`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="bf3bf-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> è stato modificato da `JObject` a `JsonDocument`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="bf3bf-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> è stato modificato da `JObject` a `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="bf3bf-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> è stato modificato dall'accettazione `JObject` al `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> changed from accepting `JObject` to `JsonElement`.</span></span>

#### <a name="category"></a><span data-ttu-id="bf3bf-127">Category</span><span class="sxs-lookup"><span data-stu-id="bf3bf-127">Category</span></span>

<span data-ttu-id="bf3bf-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bf3bf-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bf3bf-129">API interessate</span><span class="sxs-lookup"><span data-stu-id="bf3bf-129">Affected APIs</span></span>

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
