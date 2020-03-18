---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393995"
---
### <a name="authentication-google-deprecated-and-replaced"></a><span data-ttu-id="2fadb-101">Autenticazione: Google è deprecato e sostituito</span><span class="sxs-lookup"><span data-stu-id="2fadb-101">Authentication: Google+ deprecated and replaced</span></span>

<span data-ttu-id="2fadb-102">Google sta iniziando a [chiudere](https://developers.google.com/+/api-shutdown) Google Sign-in per le app già dal 28 gennaio 2019.</span><span class="sxs-lookup"><span data-stu-id="2fadb-102">Google is starting to [shut down](https://developers.google.com/+/api-shutdown) Google+ Sign-in for apps as early as January 28, 2019.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2fadb-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="2fadb-103">Change description</span></span>

<span data-ttu-id="2fadb-104">ASP.NET 4.x e ASP.NET Core hanno utilizzato le API di accesso di Google per autenticare gli utenti dell'account Google nelle app Web.</span><span class="sxs-lookup"><span data-stu-id="2fadb-104">ASP.NET 4.x and ASP.NET Core have been using the Google+ Sign-in APIs to authenticate Google account users in web apps.</span></span> <span data-ttu-id="2fadb-105">I pacchetti NuGet interessati sono [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) per ASP.NET Core `Microsoft.Owin` e [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) per con ASP.NET Web Form e MVC.</span><span class="sxs-lookup"><span data-stu-id="2fadb-105">The affected NuGet packages are [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) for ASP.NET Core and [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) for `Microsoft.Owin` with ASP.NET Web Forms and MVC.</span></span>

<span data-ttu-id="2fadb-106">Le API sostitutive di Google utilizzano un formato e un'origine dati diversi.</span><span class="sxs-lookup"><span data-stu-id="2fadb-106">Google's replacement APIs use a different data source and format.</span></span> <span data-ttu-id="2fadb-107">Le attenuazioni e le soluzioni fornite di seguito tengono conto dei cambiamenti strutturali.</span><span class="sxs-lookup"><span data-stu-id="2fadb-107">The mitigations and solutions provided below account for the structural changes.</span></span> <span data-ttu-id="2fadb-108">Le app devono verificare che i dati stessi soddisfino ancora i requisiti.</span><span class="sxs-lookup"><span data-stu-id="2fadb-108">Apps should verify the data itself still satisfies their requirements.</span></span> <span data-ttu-id="2fadb-109">Ad esempio, nomi, indirizzi e-mail, link al profilo e foto del profilo possono fornire valori leggermente diversi rispetto a prima.</span><span class="sxs-lookup"><span data-stu-id="2fadb-109">For example, names, email addresses, profile links, and profile photos may provide subtly different values than before.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2fadb-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2fadb-110">Version introduced</span></span>

<span data-ttu-id="2fadb-111">tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="2fadb-111">All versions.</span></span> <span data-ttu-id="2fadb-112">Questa modifica è esterna a ASP.NET Core.This change is external to ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fadb-112">This change is external to ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2fadb-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2fadb-113">Recommended action</span></span>

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a><span data-ttu-id="2fadb-114">Owin con ASP.NET web form e MVC</span><span class="sxs-lookup"><span data-stu-id="2fadb-114">Owin with ASP.NET Web Forms and MVC</span></span>

<span data-ttu-id="2fadb-115">Per `Microsoft.Owin` 3.1.0 e versioni successive, una mitigazione temporanea è descritta [qui](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span><span class="sxs-lookup"><span data-stu-id="2fadb-115">For `Microsoft.Owin` 3.1.0 and later, a temporary mitigation is outlined [here](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span></span> <span data-ttu-id="2fadb-116">Le app devono completare i test con l'attenuazione per verificare la presenza di modifiche nel formato dei dati.</span><span class="sxs-lookup"><span data-stu-id="2fadb-116">Apps should complete testing with the mitigation to check for changes in the data format.</span></span> <span data-ttu-id="2fadb-117">Ci sono piani `Microsoft.Owin` per rilasciare 4.0.1 con una correzione.</span><span class="sxs-lookup"><span data-stu-id="2fadb-117">There are plans to release `Microsoft.Owin` 4.0.1 with a fix.</span></span> <span data-ttu-id="2fadb-118">Le app che usano qualsiasi versione precedente devono essere aggiornate alla versione 4.0.1.Apps using any prior version should update to version 4.0.1.</span><span class="sxs-lookup"><span data-stu-id="2fadb-118">Apps using any prior version should update to version 4.0.1.</span></span>

##### <a name="aspnet-core-1x"></a><span data-ttu-id="2fadb-119">ASP.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2fadb-119">ASP.NET Core 1.x</span></span>

<span data-ttu-id="2fadb-120">L'attenuazione in [Owin con ASP.NET Web Form e MVC](#owin-with-aspnet-web-forms-and-mvc) può essere adattata a ASP.NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="2fadb-120">The mitigation in [Owin with ASP.NET Web Forms and MVC](#owin-with-aspnet-web-forms-and-mvc) can be adapted to ASP.NET Core 1.x.</span></span> <span data-ttu-id="2fadb-121">Le patch del pacchetto NuGet non sono pianificate perché 1.x ha raggiunto lo stato [di fine ciclo vita.](https://dotnet.microsoft.com/platform/support-policy)</span><span class="sxs-lookup"><span data-stu-id="2fadb-121">NuGet package patches aren't planned because 1.x has reached [end of life](https://dotnet.microsoft.com/platform/support-policy) status.</span></span>

##### <a name="aspnet-core-2x"></a><span data-ttu-id="2fadb-122">ASP.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2fadb-122">ASP.NET Core 2.x</span></span>

<span data-ttu-id="2fadb-123">Per `Microsoft.AspNetCore.Authentication.Google` la versione 2.x, `AddGoogle` sostituire `Startup.ConfigureServices` la chiamata esistente a in con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2fadb-123">For `Microsoft.AspNetCore.Authentication.Google` version 2.x, replace your existing call to `AddGoogle` in `Startup.ConfigureServices` with the following code:</span></span>

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

<span data-ttu-id="2fadb-124">Le patch del 2.1 e 2.2 febbraio hanno incorporato la riconfigurazione precedente come nuova impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2fadb-124">The February 2.1 and 2.2 patches incorporated the preceding reconfiguration as the new default.</span></span> <span data-ttu-id="2fadb-125">Nessuna patch è prevista per ASP.NET Core 2.0 da quando ha raggiunto [la fine del ciclo di vita](https://dotnet.microsoft.com/platform/support-policy).</span><span class="sxs-lookup"><span data-stu-id="2fadb-125">No patch is planned for ASP.NET Core 2.0 since it has reached [end of life](https://dotnet.microsoft.com/platform/support-policy).</span></span>

##### <a name="aspnet-core-30"></a><span data-ttu-id="2fadb-126">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2fadb-126">ASP.NET Core 3.0</span></span>

<span data-ttu-id="2fadb-127">L'attenuazione fornita per ASP.NET Core 2.x può essere usata anche per ASP.NET Core 3.0.The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2fadb-127">The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0.</span></span> <span data-ttu-id="2fadb-128">In futuro 3.0 anteprime, il `Microsoft.AspNetCore.Authentication.Google` pacchetto potrebbe essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="2fadb-128">In future 3.0 previews, the `Microsoft.AspNetCore.Authentication.Google` package may be removed.</span></span> <span data-ttu-id="2fadb-129">Gli utenti verrebbero indirizzati a `Microsoft.AspNetCore.Authentication.OpenIdConnect` invece.</span><span class="sxs-lookup"><span data-stu-id="2fadb-129">Users would be directed to `Microsoft.AspNetCore.Authentication.OpenIdConnect` instead.</span></span> <span data-ttu-id="2fadb-130">Nel codice riportato `AddGoogle` di `AddOpenIdConnect` `Startup.ConfigureServices`seguito viene illustrato come sostituire con in .</span><span class="sxs-lookup"><span data-stu-id="2fadb-130">The following code shows how to replace `AddGoogle` with `AddOpenIdConnect` in `Startup.ConfigureServices`.</span></span> <span data-ttu-id="2fadb-131">Questa sostituzione può essere utilizzata con ASP.NET Core 2.0 e versioni successive e può essere adattata per ASP.NET Core 1.x in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2fadb-131">This replacement can be used with ASP.NET Core 2.0 and later and can be adapted for ASP.NET Core 1.x as needed.</span></span>

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

#### <a name="category"></a><span data-ttu-id="2fadb-132">Category</span><span class="sxs-lookup"><span data-stu-id="2fadb-132">Category</span></span>

<span data-ttu-id="2fadb-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2fadb-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2fadb-134">API interessate</span><span class="sxs-lookup"><span data-stu-id="2fadb-134">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
