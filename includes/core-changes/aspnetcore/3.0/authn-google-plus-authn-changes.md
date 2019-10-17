---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393995"
---
### <a name="authentication-google-deprecated-and-replaced"></a>Autenticazione: Google + deprecato e sostituito

Google sta iniziando ad [arrestare](https://developers.google.com/+/api-shutdown) l'accesso a Google + per le app con un anticipo del 28 gennaio 2019.

#### <a name="change-description"></a>Descrizione della modifica

ASP.NET 4. x e ASP.NET Core usano le API di accesso di Google + per autenticare gli utenti dell'account Google nelle app Web. I pacchetti NuGet interessati sono [Microsoft. AspNetCore. Authentication. Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) per ASP.NET Core e [Microsoft. Owin. Security. Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) per `Microsoft.Owin` con ASP.NET Web Form e MVC.

Le API di sostituzione di Google usano un'origine dati e un formato diversi. Le soluzioni e le mitigazioni fornite di seguito rappresentano le modifiche strutturali. Le app devono verificare che i dati stessi soddisfino ancora i requisiti. Ad esempio, i nomi, gli indirizzi di posta elettronica, i collegamenti del profilo e le foto del profilo possono fornire valori leggermente diversi rispetto a prima.

#### <a name="version-introduced"></a>Versione introdotta

Tutte le versioni. Questa modifica è esterna a ASP.NET Core.

#### <a name="recommended-action"></a>Azione consigliata

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a>Owin con ASP.NET Web Form e MVC

Per `Microsoft.Owin` 3.1.0 e versioni successive, viene descritta una mitigazione [temporanea.](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635) Le app devono completare il test con la mitigazione per verificare la presenza di modifiche nel formato dati. Ci sono piani per rilasciare `Microsoft.Owin` 4.0.1 con una correzione. Le app che usano qualsiasi versione precedente devono eseguire l'aggiornamento alla versione 4.0.1.

##### <a name="aspnet-core-1x"></a>ASP.NET Core 1. x

La mitigazione in [Owin con ASP.NET Web Form e MVC](#owin-with-aspnet-web-forms-and-mvc) può essere adattata a ASP.NET Core 1. x. Le patch del pacchetto NuGet non sono pianificate perché 1. x ha raggiunto lo stato [di fine vita](https://dotnet.microsoft.com/platform/support-policy) .

##### <a name="aspnet-core-2x"></a>ASP.NET Core 2. x

Per `Microsoft.AspNetCore.Authentication.Google` versione 2. x, sostituire la chiamata esistente con `AddGoogle` in `Startup.ConfigureServices` con il codice seguente:

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

Le patch di febbraio 2,1 e 2,2 hanno incorporato la riconfigurazione precedente come nuovo valore predefinito. Non è prevista alcuna patch per ASP.NET Core 2,0 perché ha raggiunto il [termine della vita](https://dotnet.microsoft.com/platform/support-policy).

##### <a name="aspnet-core-30"></a>ASP.NET Core 3,0

La mitigazione fornita per ASP.NET Core 2. x può essere usata anche per ASP.NET Core 3,0. Nelle anteprime future 3,0 è possibile rimuovere il pacchetto `Microsoft.AspNetCore.Authentication.Google`. Gli utenti verrebbero invece indirizzati a `Microsoft.AspNetCore.Authentication.OpenIdConnect`. Nel codice seguente viene illustrato come sostituire `AddGoogle` con `AddOpenIdConnect` in `Startup.ConfigureServices`. Questa sostituzione può essere usata con ASP.NET Core 2,0 e versioni successive e può essere adattata per ASP.NET Core 1. x in base alle esigenze.

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/sigin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
