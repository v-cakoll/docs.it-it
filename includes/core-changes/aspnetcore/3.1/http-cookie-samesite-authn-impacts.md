---
ms.openlocfilehash: 02602c70689a6d2729e03d3d7230cda5ae7a4994
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901953"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a><span data-ttu-id="0bf70-101">HTTP: browser navigava sullostesso sito modifiche che influiscano sull'autenticazione</span><span class="sxs-lookup"><span data-stu-id="0bf70-101">HTTP: Browser SameSite changes impact authentication</span></span>

<span data-ttu-id="0bf70-102">Alcuni browser, ad esempio Chrome e Firefox, hanno apportato modifiche di rilievo alle implementazioni di `SameSite` per i cookie.</span><span class="sxs-lookup"><span data-stu-id="0bf70-102">Some browsers, such as Chrome and Firefox, made breaking changes to their implementations of `SameSite` for cookies.</span></span> <span data-ttu-id="0bf70-103">Le modifiche influiscano sugli scenari di autenticazione remota, ad esempio OpenID Connect e WS-Federation, che devono rifiutare esplicitamente inviando `SameSite=None`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-103">The changes impact remote authentication scenarios, such as OpenID Connect and WS-Federation, which must opt out by sending `SameSite=None`.</span></span> <span data-ttu-id="0bf70-104">Tuttavia, `SameSite=None` si interrompe in iOS 12 e in alcune versioni precedenti di altri browser.</span><span class="sxs-lookup"><span data-stu-id="0bf70-104">However, `SameSite=None` breaks on iOS 12 and some older versions of other browsers.</span></span> <span data-ttu-id="0bf70-105">L'app deve annusare queste versioni e omettere `SameSite`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-105">The app needs to sniff these versions and omit `SameSite`.</span></span>

<span data-ttu-id="0bf70-106">Per informazioni su questo problema, vedere [DotNet/aspnetcore # 14996](https://github.com/dotnet/aspnetcore/issues/14996).</span><span class="sxs-lookup"><span data-stu-id="0bf70-106">For discussion on this issue, see [dotnet/aspnetcore#14996](https://github.com/dotnet/aspnetcore/issues/14996).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0bf70-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="0bf70-107">Version introduced</span></span>

<span data-ttu-id="0bf70-108">3,1 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="0bf70-108">3.1 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0bf70-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="0bf70-109">Old behavior</span></span>

<span data-ttu-id="0bf70-110">`SameSite` è un'estensione standard bozza 2016 ai cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="0bf70-110">`SameSite` is a 2016 draft standard extension to HTTP cookies.</span></span> <span data-ttu-id="0bf70-111">È progettato per attenuare la richiesta tra siti falsa (CSRF).</span><span class="sxs-lookup"><span data-stu-id="0bf70-111">It's intended to mitigate Cross-Site Request Forgery (CSRF).</span></span> <span data-ttu-id="0bf70-112">Questa operazione è stata originariamente progettata come funzionalità che i server avrebbero acconsentito aggiungendo i nuovi parametri.</span><span class="sxs-lookup"><span data-stu-id="0bf70-112">This was originally designed as a feature the servers would opt into by adding the new parameters.</span></span> <span data-ttu-id="0bf70-113">ASP.NET Core 2,0 è stato aggiunto il supporto iniziale per `SameSite`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-113">ASP.NET Core 2.0 added initial support for `SameSite`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0bf70-114">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="0bf70-114">New behavior</span></span>

<span data-ttu-id="0bf70-115">Google ha proposto un nuovo standard Draft che non è compatibile con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0bf70-115">Google proposed a new draft standard that isn't backwards compatible.</span></span> <span data-ttu-id="0bf70-116">Lo standard modifica la modalità predefinita per `Lax` e aggiunge una nuova voce `None` per rifiutare esplicitamente. `Lax` è sufficiente per la maggior parte dei cookie dell'app; Tuttavia, vengono interrotti scenari tra siti come OpenID Connect e l'account di accesso WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="0bf70-116">The standard changes the default mode to `Lax` and adds a new entry `None` to opt out. `Lax` suffices for most app cookies; however, it breaks cross-site scenarios like OpenID Connect and WS-Federation login.</span></span> <span data-ttu-id="0bf70-117">La maggior parte degli accessi OAuth non è interessata a causa di differenze nel modo in cui la richiesta fluisce.</span><span class="sxs-lookup"><span data-stu-id="0bf70-117">Most OAuth logins aren't affected because of differences in how the request flows.</span></span> <span data-ttu-id="0bf70-118">Il nuovo parametro `None` causa problemi di compatibilità con i client che hanno implementato lo standard Draft precedente (ad esempio, iOS 12).</span><span class="sxs-lookup"><span data-stu-id="0bf70-118">The new `None` parameter causes compatibility problems with clients that implemented the prior draft standard (for example, iOS 12).</span></span> <span data-ttu-id="0bf70-119">Chrome 80 includerà le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0bf70-119">Chrome 80 will include the changes.</span></span> <span data-ttu-id="0bf70-120">Vedere [aggiornamenti di navigava sullostesso sito](https://www.chromium.org/updates/same-site) per la sequenza temporale di avvio del prodotto Chrome.</span><span class="sxs-lookup"><span data-stu-id="0bf70-120">See [SameSite Updates](https://www.chromium.org/updates/same-site) for the Chrome product launch timeline.</span></span>

<span data-ttu-id="0bf70-121">ASP.NET Core 3,1 è stato aggiornato per implementare il nuovo comportamento del `SameSite`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-121">ASP.NET Core 3.1 has been updated to implement the new `SameSite` behavior.</span></span> <span data-ttu-id="0bf70-122">L'aggiornamento ridefinisce il comportamento di `SameSiteMode.None` per emettere `SameSite=None` e aggiunge un nuovo valore `SameSiteMode.Unspecified` per omettere l'attributo `SameSite`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-122">The update redefines the behavior of `SameSiteMode.None` to emit `SameSite=None` and adds a new value `SameSiteMode.Unspecified` to omit the `SameSite` attribute.</span></span> <span data-ttu-id="0bf70-123">Per impostazione predefinita, tutte le API cookie vengono `Unspecified`, anche se alcuni componenti che usano cookie impostano valori più specifici per i relativi scenari, ad esempio i cookie di correlazione e nonce di OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="0bf70-123">All cookie APIs now default to `Unspecified`, though some components that use cookies set values more specific to their scenarios such as the OpenID Connect correlation and nonce cookies.</span></span>

<span data-ttu-id="0bf70-124">Per altre modifiche recenti in quest'area, vedere [http: alcuni cookie navigava sullostesso sito predefiniti sono stati modificati in nessuno](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none).</span><span class="sxs-lookup"><span data-stu-id="0bf70-124">For other recent changes in this area, see [HTTP: Some cookie SameSite defaults changed to None](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none).</span></span> <span data-ttu-id="0bf70-125">In ASP.NET Core 3,0, la maggior parte delle impostazioni predefinite è stata modificata da <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> a <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType>, ma è ancora in uso lo standard precedente.</span><span class="sxs-lookup"><span data-stu-id="0bf70-125">In ASP.NET Core 3.0, most defaults were changed from <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> to <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> (but still using the prior standard).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0bf70-126">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="0bf70-126">Reason for change</span></span>

<span data-ttu-id="0bf70-127">Modifiche del browser e delle specifiche come indicato nel testo precedente.</span><span class="sxs-lookup"><span data-stu-id="0bf70-127">Browser and specification changes as outlined in the preceding text.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0bf70-128">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="0bf70-128">Recommended action</span></span>

<span data-ttu-id="0bf70-129">Le app che interagiscono con i siti remoti, ad esempio tramite account di accesso di terze parti, devono:</span><span class="sxs-lookup"><span data-stu-id="0bf70-129">Apps that interact with remote sites, such as through third-party login, need to:</span></span>

* <span data-ttu-id="0bf70-130">Testare questi scenari in più browser.</span><span class="sxs-lookup"><span data-stu-id="0bf70-130">Test those scenarios on multiple browsers.</span></span>
* <span data-ttu-id="0bf70-131">Applicare la mitigazione dello sniffing del browser criteri cookie descritta in [supportare i browser meno recenti](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="0bf70-131">Apply the cookie policy browser sniffing mitigation discussed in [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="0bf70-132">Per istruzioni su test e analisi del browser, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="0bf70-132">For testing and browser sniffing instructions, see the following section.</span></span>

##### <a name="determine-if-youre-affected"></a><span data-ttu-id="0bf70-133">Determinare se si è interessati</span><span class="sxs-lookup"><span data-stu-id="0bf70-133">Determine if you're affected</span></span>

<span data-ttu-id="0bf70-134">Testare l'app Web usando una versione client che può acconsentire esplicitamente al nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="0bf70-134">Test your web app using a client version that can opt into the new behavior.</span></span> <span data-ttu-id="0bf70-135">Chrome, Firefox e Microsoft Edge Chromium hanno tutti nuovi flag di funzionalità di consenso esplicito che possono essere usati per i test.</span><span class="sxs-lookup"><span data-stu-id="0bf70-135">Chrome, Firefox, and Microsoft Edge Chromium all have new opt-in feature flags that can be used for testing.</span></span> <span data-ttu-id="0bf70-136">Verificare che l'app sia compatibile con le versioni precedenti del client dopo aver applicato le patch, in particolare Safari.</span><span class="sxs-lookup"><span data-stu-id="0bf70-136">Verify that your app is compatible with older client versions after you've applied the patches, especially Safari.</span></span> <span data-ttu-id="0bf70-137">Per ulteriori informazioni, vedere [supportare browser meno recenti](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="0bf70-137">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="chrome"></a><span data-ttu-id="0bf70-138">Chrome</span><span class="sxs-lookup"><span data-stu-id="0bf70-138">Chrome</span></span>

<span data-ttu-id="0bf70-139">Chrome 78 e versioni successive producono risultati dei test fuorvianti.</span><span class="sxs-lookup"><span data-stu-id="0bf70-139">Chrome 78 and later yield misleading test results.</span></span> <span data-ttu-id="0bf70-140">Queste versioni presentano una mitigazione temporanea e consentono ai cookie meno di due minuti.</span><span class="sxs-lookup"><span data-stu-id="0bf70-140">Those versions have a temporary mitigation in place and allow cookies less than two minutes old.</span></span> <span data-ttu-id="0bf70-141">Con i flag di test appropriati abilitati, Chrome 76 e 77 producono risultati più accurati.</span><span class="sxs-lookup"><span data-stu-id="0bf70-141">With the appropriate test flags enabled, Chrome 76 and 77 yield more accurate results.</span></span> <span data-ttu-id="0bf70-142">Per testare il nuovo comportamento, impostare `chrome://flags/#same-site-by-default-cookies` su abilitato.</span><span class="sxs-lookup"><span data-stu-id="0bf70-142">To test the new behavior, toggle `chrome://flags/#same-site-by-default-cookies` to enabled.</span></span> <span data-ttu-id="0bf70-143">Chrome 75 e versioni precedenti vengono segnalati per avere esito negativo con la nuova impostazione `None`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-143">Chrome 75 and earlier are reported to fail with the new `None` setting.</span></span> <span data-ttu-id="0bf70-144">Per ulteriori informazioni, vedere [supportare browser meno recenti](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="0bf70-144">For more information, see [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="0bf70-145">Google non rende disponibili versioni precedenti di Chrome.</span><span class="sxs-lookup"><span data-stu-id="0bf70-145">Google doesn't make older Chrome versions available.</span></span> <span data-ttu-id="0bf70-146">È possibile, tuttavia, scaricare le versioni precedenti di Chromium, che sarà sufficiente per il test.</span><span class="sxs-lookup"><span data-stu-id="0bf70-146">You can, however, download older versions of Chromium, which will suffice for testing.</span></span> <span data-ttu-id="0bf70-147">Seguire le istruzioni riportate in [scaricare Chromium](https://www.chromium.org/getting-involved/download-chromium).</span><span class="sxs-lookup"><span data-stu-id="0bf70-147">Follow the instructions at [Download Chromium](https://www.chromium.org/getting-involved/download-chromium).</span></span>

* [<span data-ttu-id="0bf70-148">Cromo 76 Win64</span><span class="sxs-lookup"><span data-stu-id="0bf70-148">Chromium 76 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [<span data-ttu-id="0bf70-149">Cromo 74 Win64</span><span class="sxs-lookup"><span data-stu-id="0bf70-149">Chromium 74 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a><span data-ttu-id="0bf70-150">Safari</span><span class="sxs-lookup"><span data-stu-id="0bf70-150">Safari</span></span>

<span data-ttu-id="0bf70-151">Safari 12 ha implementato rigorosamente la bozza precedente e ha esito negativo se rileva il nuovo valore `None` nei cookie.</span><span class="sxs-lookup"><span data-stu-id="0bf70-151">Safari 12 strictly implemented the prior draft and fails if it sees the new `None` value in cookies.</span></span> <span data-ttu-id="0bf70-152">Questa operazione deve essere evitata tramite il codice di sniffing del browser illustrato in [supportare i browser meno recenti](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="0bf70-152">This must be avoided via the browser sniffing code shown in [Support older browsers](#support-older-browsers).</span></span> <span data-ttu-id="0bf70-153">Assicurarsi di testare Safari 12 e 13, nonché gli account di accesso basati su WebKit, in stile sistema operativo tramite Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL) o qualsiasi libreria in uso.</span><span class="sxs-lookup"><span data-stu-id="0bf70-153">Ensure you test Safari 12 and 13 as well as WebKit-based, OS-style logins using Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL), or whichever library you're using.</span></span> <span data-ttu-id="0bf70-154">Il problema dipende dalla versione del sistema operativo sottostante.</span><span class="sxs-lookup"><span data-stu-id="0bf70-154">The problem is dependent on the underlying OS version.</span></span> <span data-ttu-id="0bf70-155">I problemi di compatibilità con il nuovo comportamento sono noti per OSX Mojave 10,14 e iOS 12.</span><span class="sxs-lookup"><span data-stu-id="0bf70-155">OSX Mojave 10.14 and iOS 12 are known to have compatibility problems with the new behavior.</span></span> <span data-ttu-id="0bf70-156">L'aggiornamento a OSX Catalina 10,15 o iOS 13 corregge il problema.</span><span class="sxs-lookup"><span data-stu-id="0bf70-156">Upgrading to OSX Catalina 10.15 or iOS 13 fixes the problem.</span></span> <span data-ttu-id="0bf70-157">Safari non dispone attualmente di un flag di consenso esplicito per il test del nuovo comportamento della specifica.</span><span class="sxs-lookup"><span data-stu-id="0bf70-157">Safari doesn't currently have an opt-in flag for testing the new specification behavior.</span></span>

##### <a name="firefox"></a><span data-ttu-id="0bf70-158">Firefox</span><span class="sxs-lookup"><span data-stu-id="0bf70-158">Firefox</span></span>

<span data-ttu-id="0bf70-159">Il supporto di Firefox per il nuovo standard può essere testato nella versione 68 e successive scegliendo nella pagina `about:config` con il flag funzionalità `network.cookie.sameSite.laxByDefault`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-159">Firefox support for the new standard can be tested on version 68 and later by opting in on the `about:config` page with the feature flag `network.cookie.sameSite.laxByDefault`.</span></span> <span data-ttu-id="0bf70-160">Nessun problema di compatibilità è stato segnalato nelle versioni precedenti di Firefox.</span><span class="sxs-lookup"><span data-stu-id="0bf70-160">No compatibility issues have been reported on older versions of Firefox.</span></span>

##### <a name="microsoft-edge"></a><span data-ttu-id="0bf70-161">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0bf70-161">Microsoft Edge</span></span>

<span data-ttu-id="0bf70-162">Sebbene Microsoft Edge supporti il vecchio `SameSite` standard, a partire dalla versione 44, non ha avuto problemi di compatibilità con il nuovo standard.</span><span class="sxs-lookup"><span data-stu-id="0bf70-162">While Microsoft Edge supports the old `SameSite` standard, as of version 44 it didn't have any compatibility problems with the new standard.</span></span>

##### <a name="microsoft-edge-chromium"></a><span data-ttu-id="0bf70-163">Cromo Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0bf70-163">Microsoft Edge Chromium</span></span>

<span data-ttu-id="0bf70-164">Il flag della funzionalità è `edge://flags/#same-site-by-default-cookies`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-164">The feature flag is `edge://flags/#same-site-by-default-cookies`.</span></span> <span data-ttu-id="0bf70-165">Nessun problema di compatibilità rilevato durante il test con Microsoft Edge Chromium 78.</span><span class="sxs-lookup"><span data-stu-id="0bf70-165">No compatibility issues were observed when testing with Microsoft Edge Chromium 78.</span></span>

##### <a name="electron"></a><span data-ttu-id="0bf70-166">Electron</span><span class="sxs-lookup"><span data-stu-id="0bf70-166">Electron</span></span>

<span data-ttu-id="0bf70-167">Le versioni di Electron includono versioni precedenti di cromo.</span><span class="sxs-lookup"><span data-stu-id="0bf70-167">Versions of Electron include older versions of Chromium.</span></span> <span data-ttu-id="0bf70-168">Ad esempio, la versione di Electron usata da Microsoft teams è Chromium 66, che presenta il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="0bf70-168">For example, the version of Electron used by Microsoft Teams is Chromium 66, which exhibits the older behavior.</span></span> <span data-ttu-id="0bf70-169">Eseguire test di compatibilità personalizzati con la versione di Electron utilizzata dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="0bf70-169">Perform your own compatibility testing with the version of Electron your product uses.</span></span> <span data-ttu-id="0bf70-170">Per ulteriori informazioni, vedere [supportare browser meno recenti](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="0bf70-170">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="support-older-browsers"></a><span data-ttu-id="0bf70-171">Supportare i browser meno recenti</span><span class="sxs-lookup"><span data-stu-id="0bf70-171">Support older browsers</span></span>

<span data-ttu-id="0bf70-172">2016 `SameSite` standard imposto che i valori sconosciuti vengano considerati come `SameSite=Strict` valori.</span><span class="sxs-lookup"><span data-stu-id="0bf70-172">The 2016 `SameSite` standard mandated that unknown values be treated as `SameSite=Strict` values.</span></span> <span data-ttu-id="0bf70-173">Di conseguenza, tutti i browser meno recenti che supportano lo standard originale potrebbero interrompersi quando viene visualizzato un `SameSite` proprietà con un valore di `None`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-173">Consequently, any older browsers that support the original standard may break when they see a `SameSite` property with a value of `None`.</span></span> <span data-ttu-id="0bf70-174">Le app Web devono implementare lo sniffing del browser se intendono supportare questi browser obsoleti.</span><span class="sxs-lookup"><span data-stu-id="0bf70-174">Web apps must implement browser sniffing if they intend to support these old browsers.</span></span> <span data-ttu-id="0bf70-175">ASP.NET Core non implementa lo sniffing del browser perché `User-Agent` i valori dell'intestazione della richiesta sono altamente instabili e cambiano su base settimanale.</span><span class="sxs-lookup"><span data-stu-id="0bf70-175">ASP.NET Core doesn't implement browser sniffing for you because `User-Agent` request header values are highly unstable and change on a weekly basis.</span></span> <span data-ttu-id="0bf70-176">Un punto di estensione nel criterio dei cookie consente invece di aggiungere la logica specifica del `User-Agent`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-176">Instead, an extension point in the cookie policy allows you to add `User-Agent`-specific logic.</span></span>

<span data-ttu-id="0bf70-177">In *Startup.cs*aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0bf70-177">In *Startup.cs*, add the following code:</span></span>

```csharp
private void CheckSameSite(HttpContext httpContext, CookieOptions options)
{
    if (options.SameSite == SameSiteMode.None) 
    { 
        var userAgent = httpContext.Request.Headers["User-Agent"].ToString();
        // TODO: Use your User Agent library of choice here. 
        if (/* UserAgent doesn't support new behavior */) 
        { 
            options.SameSite = SameSiteMode.Unspecified;
        }
    }
}

public void ConfigureServices(IServiceCollection services) 
{ 
    services.Configure<CookiePolicyOptions>(options => 
    { 
        options.MinimumSameSitePolicy = SameSiteMode.Unspecified;
        options.OnAppendCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
        options.OnDeleteCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
    }); 
} 

public void Configure(IApplicationBuilder app) 
{ 
    // Before UseAuthentication or anything else that writes cookies.
    app.UseCookiePolicy();

    app.UseAuthentication(); 
    // code omitted for brevity
}
```

##### <a name="opt-out-switches"></a><span data-ttu-id="0bf70-178">Opzioni di rifiuto esplicito</span><span class="sxs-lookup"><span data-stu-id="0bf70-178">Opt-out switches</span></span>

<span data-ttu-id="0bf70-179">Il `Microsoft.AspNetCore.SuppressSameSiteNone` opzione di compatibilità consente di rifiutare temporaneamente il nuovo comportamento di ASP.NET Core cookie.</span><span class="sxs-lookup"><span data-stu-id="0bf70-179">The `Microsoft.AspNetCore.SuppressSameSiteNone` compatibility switch enables you to temporarily opt out of the new ASP.NET Core cookie behavior.</span></span> <span data-ttu-id="0bf70-180">Aggiungere il codice JSON seguente a un file *runtimeconfig. template. JSON* nel progetto:</span><span class="sxs-lookup"><span data-stu-id="0bf70-180">Add the following JSON to a *runtimeconfig.template.json* file in your project:</span></span>

```json
{ 
  "configProperties": { 
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true" 
  } 
}
```

##### <a name="other-versions"></a><span data-ttu-id="0bf70-181">Altre versioni</span><span class="sxs-lookup"><span data-stu-id="0bf70-181">Other Versions</span></span>

<span data-ttu-id="0bf70-182">Le patch `SameSite` correlate sono imminenti per:</span><span class="sxs-lookup"><span data-stu-id="0bf70-182">Related `SameSite` patches are forthcoming for:</span></span>

* <span data-ttu-id="0bf70-183">ASP.NET Core 2,1, 2,2 e 3,0</span><span class="sxs-lookup"><span data-stu-id="0bf70-183">ASP.NET Core 2.1, 2.2, and 3.0</span></span>
* <span data-ttu-id="0bf70-184">`Microsoft.Owin` 4,1</span><span class="sxs-lookup"><span data-stu-id="0bf70-184">`Microsoft.Owin` 4.1</span></span>
* <span data-ttu-id="0bf70-185">`System.Web` (per .NET Framework 4.7.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="0bf70-185">`System.Web` (for .NET Framework 4.7.2 and later)</span></span>

#### <a name="category"></a><span data-ttu-id="0bf70-186">Categoria</span><span class="sxs-lookup"><span data-stu-id="0bf70-186">Category</span></span>

<span data-ttu-id="0bf70-187">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0bf70-187">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0bf70-188">API interessate</span><span class="sxs-lookup"><span data-stu-id="0bf70-188">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieBuilder.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieOptions.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`
- `Overload:Microsoft.AspNetCore.Http.CookieBuilder.SameSite`
- `Overload:Microsoft.AspNetCore.Http.CookieOptions.SameSite`
- `T:Microsoft.AspNetCore.Http.SameSiteMode`
- `T:Microsoft.Net.Http.Headers.SameSiteMode`
- `Overload:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite`

-->
