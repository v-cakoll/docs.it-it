---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393995"
---
### <a name="authentication-google-deprecated-and-replaced"></a>Autenticazione: Google è deprecato e sostituito

Google sta iniziando a [chiudere](https://developers.google.com/+/api-shutdown) Google Sign-in per le app già dal 28 gennaio 2019.

#### <a name="change-description"></a>Descrizione modifica:

ASP.NET 4.x e ASP.NET Core hanno utilizzato le API di accesso di Google per autenticare gli utenti dell'account Google nelle app Web. I pacchetti NuGet interessati sono [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) per ASP.NET Core `Microsoft.Owin` e [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) per con ASP.NET Web Form e MVC.

Le API sostitutive di Google utilizzano un formato e un'origine dati diversi. Le attenuazioni e le soluzioni fornite di seguito tengono conto dei cambiamenti strutturali. Le app devono verificare che i dati stessi soddisfino ancora i requisiti. Ad esempio, nomi, indirizzi e-mail, link al profilo e foto del profilo possono fornire valori leggermente diversi rispetto a prima.

#### <a name="version-introduced"></a>Versione introdotta

tutte le versioni. Questa modifica è esterna a ASP.NET Core.This change is external to ASP.NET Core.

#### <a name="recommended-action"></a>Azione consigliata

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a>Owin con ASP.NET web form e MVC

Per `Microsoft.Owin` 3.1.0 e versioni successive, una mitigazione temporanea è descritta [qui](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635). Le app devono completare i test con l'attenuazione per verificare la presenza di modifiche nel formato dei dati. Ci sono piani `Microsoft.Owin` per rilasciare 4.0.1 con una correzione. Le app che usano qualsiasi versione precedente devono essere aggiornate alla versione 4.0.1.Apps using any prior version should update to version 4.0.1.

##### <a name="aspnet-core-1x"></a>ASP.NET Core 1.x

L'attenuazione in [Owin con ASP.NET Web Form e MVC](#owin-with-aspnet-web-forms-and-mvc) può essere adattata a ASP.NET Core 1.x. Le patch del pacchetto NuGet non sono pianificate perché 1.x ha raggiunto lo stato [di fine ciclo vita.](https://dotnet.microsoft.com/platform/support-policy)

##### <a name="aspnet-core-2x"></a>ASP.NET Core 2.x

Per `Microsoft.AspNetCore.Authentication.Google` la versione 2.x, `AddGoogle` sostituire `Startup.ConfigureServices` la chiamata esistente a in con il codice seguente:

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

Le patch del 2.1 e 2.2 febbraio hanno incorporato la riconfigurazione precedente come nuova impostazione predefinita. Nessuna patch è prevista per ASP.NET Core 2.0 da quando ha raggiunto [la fine del ciclo di vita](https://dotnet.microsoft.com/platform/support-policy).

##### <a name="aspnet-core-30"></a>ASP.NET Core 3.0

L'attenuazione fornita per ASP.NET Core 2.x può essere usata anche per ASP.NET Core 3.0.The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0. In futuro 3.0 anteprime, il `Microsoft.AspNetCore.Authentication.Google` pacchetto potrebbe essere rimosso. Gli utenti verrebbero indirizzati a `Microsoft.AspNetCore.Authentication.OpenIdConnect` invece. Nel codice riportato `AddGoogle` di `AddOpenIdConnect` `Startup.ConfigureServices`seguito viene illustrato come sostituire con in . Questa sostituzione può essere utilizzata con ASP.NET Core 2.0 e versioni successive e può essere adattata per ASP.NET Core 1.x in base alle esigenze.

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
