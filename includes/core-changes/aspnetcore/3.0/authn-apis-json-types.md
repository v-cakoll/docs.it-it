---
ms.openlocfilehash: 494e792d63a611cdaedf3e40aa607cfbb0420ae4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901858"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a>Autenticazione: tipi Newtonsoft. JSON sostituiti

In ASP.NET Core 3,0 i tipi di `Newtonsoft.Json` usati nelle API di autenticazione sono stati sostituiti con tipi di `System.Text.Json`. Eccetto nei casi seguenti, l'utilizzo di base dei pacchetti di autenticazione rimane inalterato:

* Classi derivate dai provider OAuth, ad esempio quelle di [ASPNET-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).
* Implementazioni avanzate di manipolazione delle attestazioni.

Per ulteriori informazioni, vedere [DotNet/aspnetcore # 7105](https://github.com/dotnet/aspnetcore/pull/7105). Per informazioni, vedere [DotNet/aspnetcore # 7289](https://github.com/dotnet/aspnetcore/issues/7289).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Per le implementazioni OAuth derivate, la modifica più comune consiste nel sostituire `JObject.Parse` con `JsonDocument.Parse` nell'override `CreateTicketAsync` come illustrato di [seguito](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40). `JsonDocument` implementa `IDisposable`.

Nell'elenco seguente vengono descritte le modifiche note:

- <xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> viene `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`. Tutte le implementazioni derivate di `ClaimAction` sono interessate in modo analogo.
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> ha rimosso un costruttore precedente e l'altro ha sostituito `JObject` con `JsonElement`. La proprietà `User` e il metodo `RunClaimActions` sono stati aggiornati in modo che corrispondano.
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> ora accetta un parametro di tipo `JsonDocument` invece di `JObject`. La proprietà `Response` è stata aggiornata in modo da corrispondere. `OAuthTokenResponse` è ora monouso e verrà eliminato da `OAuthHandler`. Le implementazioni OAuth derivate che eseguono l'override di `ExchangeCodeAsync` non devono eliminare l'`JsonDocument` o `OAuthTokenResponse`.
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> è stato modificato da `JObject` a `JsonDocument`.
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> è stato modificato da `JObject` a `JsonElement`.
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> stato modificato dall'accettazione `JObject` `JsonElement`.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

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
