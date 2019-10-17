---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393995"
---
### <a name="authentication-google-deprecated-and-replaced"></a><span data-ttu-id="45e7a-101">Autenticazione: Google + deprecato e sostituito</span><span class="sxs-lookup"><span data-stu-id="45e7a-101">Authentication: Google+ deprecated and replaced</span></span>

<span data-ttu-id="45e7a-102">Google sta iniziando ad [arrestare](https://developers.google.com/+/api-shutdown) l'accesso a Google + per le app con un anticipo del 28 gennaio 2019.</span><span class="sxs-lookup"><span data-stu-id="45e7a-102">Google is starting to [shut down](https://developers.google.com/+/api-shutdown) Google+ Sign-in for apps as early as January 28, 2019.</span></span>

#### <a name="change-description"></a><span data-ttu-id="45e7a-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="45e7a-103">Change description</span></span>

<span data-ttu-id="45e7a-104">ASP.NET 4. x e ASP.NET Core usano le API di accesso di Google + per autenticare gli utenti dell'account Google nelle app Web.</span><span class="sxs-lookup"><span data-stu-id="45e7a-104">ASP.NET 4.x and ASP.NET Core have been using the Google+ Sign-in APIs to authenticate Google account users in web apps.</span></span> <span data-ttu-id="45e7a-105">I pacchetti NuGet interessati sono [Microsoft. AspNetCore. Authentication. Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) per ASP.NET Core e [Microsoft. Owin. Security. Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) per `Microsoft.Owin` con ASP.NET Web Form e MVC.</span><span class="sxs-lookup"><span data-stu-id="45e7a-105">The affected NuGet packages are [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) for ASP.NET Core and [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) for `Microsoft.Owin` with ASP.NET Web Forms and MVC.</span></span>

<span data-ttu-id="45e7a-106">Le API di sostituzione di Google usano un'origine dati e un formato diversi.</span><span class="sxs-lookup"><span data-stu-id="45e7a-106">Google's replacement APIs use a different data source and format.</span></span> <span data-ttu-id="45e7a-107">Le soluzioni e le mitigazioni fornite di seguito rappresentano le modifiche strutturali.</span><span class="sxs-lookup"><span data-stu-id="45e7a-107">The mitigations and solutions provided below account for the structural changes.</span></span> <span data-ttu-id="45e7a-108">Le app devono verificare che i dati stessi soddisfino ancora i requisiti.</span><span class="sxs-lookup"><span data-stu-id="45e7a-108">Apps should verify the data itself still satisfies their requirements.</span></span> <span data-ttu-id="45e7a-109">Ad esempio, i nomi, gli indirizzi di posta elettronica, i collegamenti del profilo e le foto del profilo possono fornire valori leggermente diversi rispetto a prima.</span><span class="sxs-lookup"><span data-stu-id="45e7a-109">For example, names, email addresses, profile links, and profile photos may provide subtly different values than before.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="45e7a-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="45e7a-110">Version introduced</span></span>

<span data-ttu-id="45e7a-111">Tutte le versioni.</span><span class="sxs-lookup"><span data-stu-id="45e7a-111">All versions.</span></span> <span data-ttu-id="45e7a-112">Questa modifica è esterna a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="45e7a-112">This change is external to ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="45e7a-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="45e7a-113">Recommended action</span></span>

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a><span data-ttu-id="45e7a-114">Owin con ASP.NET Web Form e MVC</span><span class="sxs-lookup"><span data-stu-id="45e7a-114">Owin with ASP.NET Web Forms and MVC</span></span>

<span data-ttu-id="45e7a-115">Per `Microsoft.Owin` 3.1.0 e versioni successive, viene descritta una mitigazione [temporanea.](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635)</span><span class="sxs-lookup"><span data-stu-id="45e7a-115">For `Microsoft.Owin` 3.1.0 and later, a temporary mitigation is outlined [here](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span></span> <span data-ttu-id="45e7a-116">Le app devono completare il test con la mitigazione per verificare la presenza di modifiche nel formato dati.</span><span class="sxs-lookup"><span data-stu-id="45e7a-116">Apps should complete testing with the mitigation to check for changes in the data format.</span></span> <span data-ttu-id="45e7a-117">Ci sono piani per rilasciare `Microsoft.Owin` 4.0.1 con una correzione.</span><span class="sxs-lookup"><span data-stu-id="45e7a-117">There are plans to release `Microsoft.Owin` 4.0.1 with a fix.</span></span> <span data-ttu-id="45e7a-118">Le app che usano qualsiasi versione precedente devono eseguire l'aggiornamento alla versione 4.0.1.</span><span class="sxs-lookup"><span data-stu-id="45e7a-118">Apps using any prior version should update to version 4.0.1.</span></span>

##### <a name="aspnet-core-1x"></a><span data-ttu-id="45e7a-119">ASP.NET Core 1. x</span><span class="sxs-lookup"><span data-stu-id="45e7a-119">ASP.NET Core 1.x</span></span>

<span data-ttu-id="45e7a-120">La mitigazione in [Owin con ASP.NET Web Form e MVC](#owin-with-aspnet-web-forms-and-mvc) può essere adattata a ASP.NET Core 1. x.</span><span class="sxs-lookup"><span data-stu-id="45e7a-120">The mitigation in [Owin with ASP.NET Web Forms and MVC](#owin-with-aspnet-web-forms-and-mvc) can be adapted to ASP.NET Core 1.x.</span></span> <span data-ttu-id="45e7a-121">Le patch del pacchetto NuGet non sono pianificate perché 1. x ha raggiunto lo stato [di fine vita](https://dotnet.microsoft.com/platform/support-policy) .</span><span class="sxs-lookup"><span data-stu-id="45e7a-121">NuGet package patches aren't planned because 1.x has reached [end of life](https://dotnet.microsoft.com/platform/support-policy) status.</span></span>

##### <a name="aspnet-core-2x"></a><span data-ttu-id="45e7a-122">ASP.NET Core 2. x</span><span class="sxs-lookup"><span data-stu-id="45e7a-122">ASP.NET Core 2.x</span></span>

<span data-ttu-id="45e7a-123">Per `Microsoft.AspNetCore.Authentication.Google` versione 2. x, sostituire la chiamata esistente con `AddGoogle` in `Startup.ConfigureServices` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="45e7a-123">For `Microsoft.AspNetCore.Authentication.Google` version 2.x, replace your existing call to `AddGoogle` in `Startup.ConfigureServices` with the following code:</span></span>

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

<span data-ttu-id="45e7a-124">Le patch di febbraio 2,1 e 2,2 hanno incorporato la riconfigurazione precedente come nuovo valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="45e7a-124">The February 2.1 and 2.2 patches incorporated the preceding reconfiguration as the new default.</span></span> <span data-ttu-id="45e7a-125">Non è prevista alcuna patch per ASP.NET Core 2,0 perché ha raggiunto il [termine della vita](https://dotnet.microsoft.com/platform/support-policy).</span><span class="sxs-lookup"><span data-stu-id="45e7a-125">No patch is planned for ASP.NET Core 2.0 since it has reached [end of life](https://dotnet.microsoft.com/platform/support-policy).</span></span>

##### <a name="aspnet-core-30"></a><span data-ttu-id="45e7a-126">ASP.NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="45e7a-126">ASP.NET Core 3.0</span></span>

<span data-ttu-id="45e7a-127">La mitigazione fornita per ASP.NET Core 2. x può essere usata anche per ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="45e7a-127">The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0.</span></span> <span data-ttu-id="45e7a-128">Nelle anteprime future 3,0 è possibile rimuovere il pacchetto `Microsoft.AspNetCore.Authentication.Google`.</span><span class="sxs-lookup"><span data-stu-id="45e7a-128">In future 3.0 previews, the `Microsoft.AspNetCore.Authentication.Google` package may be removed.</span></span> <span data-ttu-id="45e7a-129">Gli utenti verrebbero invece indirizzati a `Microsoft.AspNetCore.Authentication.OpenIdConnect`.</span><span class="sxs-lookup"><span data-stu-id="45e7a-129">Users would be directed to `Microsoft.AspNetCore.Authentication.OpenIdConnect` instead.</span></span> <span data-ttu-id="45e7a-130">Nel codice seguente viene illustrato come sostituire `AddGoogle` con `AddOpenIdConnect` in `Startup.ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="45e7a-130">The following code shows how to replace `AddGoogle` with `AddOpenIdConnect` in `Startup.ConfigureServices`.</span></span> <span data-ttu-id="45e7a-131">Questa sostituzione può essere usata con ASP.NET Core 2,0 e versioni successive e può essere adattata per ASP.NET Core 1. x in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="45e7a-131">This replacement can be used with ASP.NET Core 2.0 and later and can be adapted for ASP.NET Core 1.x as needed.</span></span>

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

#### <a name="category"></a><span data-ttu-id="45e7a-132">Category</span><span class="sxs-lookup"><span data-stu-id="45e7a-132">Category</span></span>

<span data-ttu-id="45e7a-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="45e7a-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="45e7a-134">API interessate</span><span class="sxs-lookup"><span data-stu-id="45e7a-134">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
