---
ms.openlocfilehash: b4499637cd5fff015335e0cdb3c6cf1c3ea6cff0
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637184"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a>Autenticazione: tipi Newtonsoft.Json sostituiti

In ASP.NET Core 3.0, `Newtonsoft.Json` i tipi utilizzati `System.Text.Json` nelle API di autenticazione sono stati sostituiti con i tipi. Ad eccezione dei seguenti casi, l'utilizzo di base dei pacchetti di autenticazione rimane inalterato:

* Classi derivate dai provider OAuth, ad esempio quelle di [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).
* Implementazioni avanzate di manipolazione delle attestazioni.

Per ulteriori informazioni, vedere [dotnet/aspnetcore-7105](https://github.com/dotnet/aspnetcore/pull/7105). Per una discussione, vedere [dotnet/aspnetcore-7289](https://github.com/dotnet/aspnetcore/issues/7289).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Per le implementazioni OAuth derivate, `JObject.Parse` la `JsonDocument.Parse` modifica `CreateTicketAsync` più comune consiste nel sostituire con nell'override come illustrato [di seguito.](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40) `JsonDocument` implementa `IDisposable`.

Nell'elenco seguente vengono descritte le modifiche note:

- <xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType>diventa `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`. Tutte le implementazioni derivate di `ClaimAction` sono interessate in modo analogo.
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> diventa `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext>è stato rimosso un vecchio `JObject` costruttore e l'altro sostituito con `JsonElement`. La `User` proprietà `RunClaimActions` e il metodo sono stati aggiornati in modo che corrispondano.
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)>ora accetta un parametro di tipo `JsonDocument` anziché `JObject`. La `Response` proprietà è stata aggiornata in modo che corrisponda. `OAuthTokenResponse`è ora usa e getta `OAuthHandler`e sarà smaltito da . Le implementazioni OAuth `ExchangeCodeAsync` derivate che esegue `JsonDocument` `OAuthTokenResponse`l'override non è necessario eliminare l'oggetto o .
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType>modificato `JObject` da `JsonDocument`a .
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType>modificato `JObject` da `JsonElement`a .
- L'ultimo parametro di [TwitterHandler.CreateTicketAsync(ClaimsIdentity,AuthenticationProperties,AccessToken,JObject)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.authentication.twitter.twitterhandler.createticketasync?view=aspnetcore-2.2#Microsoft_AspNetCore_Authentication_Twitter_TwitterHandler_CreateTicketAsync_System_Security_Claims_ClaimsIdentity_Microsoft_AspNetCore_Authentication_AuthenticationProperties_Microsoft_AspNetCore_Authentication_Twitter_AccessToken_Newtonsoft_Json_Linq_JObject_) è stato modificato da `JObject` in . `JsonElement` Il metodo <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,System.Text.Json.JsonElement)?displayProperty=nameWithType>di sostituzione è .

#### <a name="category"></a>Category

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
