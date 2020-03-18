---
ms.openlocfilehash: 3cc07eef109b9096bc5a5fbcd1ea098a23b2155f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968141"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a><span data-ttu-id="280b3-101">HTTP: Le modifiche del browser SameSite influiscono sull'autenticazione</span><span class="sxs-lookup"><span data-stu-id="280b3-101">HTTP: Browser SameSite changes impact authentication</span></span>

<span data-ttu-id="280b3-102">Alcuni browser, come Chrome e Firefox, hanno apportato `SameSite` modifiche di rilievo alle loro implementazioni di per i cookie.</span><span class="sxs-lookup"><span data-stu-id="280b3-102">Some browsers, such as Chrome and Firefox, made breaking changes to their implementations of `SameSite` for cookies.</span></span> <span data-ttu-id="280b3-103">Le modifiche influiscono sugli scenari di autenticazione remota, ad esempio `SameSite=None`OpenID Connect e WS-Federation, che devono rifiutare esplicitamente l'invio di .</span><span class="sxs-lookup"><span data-stu-id="280b3-103">The changes impact remote authentication scenarios, such as OpenID Connect and WS-Federation, which must opt out by sending `SameSite=None`.</span></span> <span data-ttu-id="280b3-104">Tuttavia, `SameSite=None` si rompe su iOS 12 e alcune versioni precedenti di altri browser.</span><span class="sxs-lookup"><span data-stu-id="280b3-104">However, `SameSite=None` breaks on iOS 12 and some older versions of other browsers.</span></span> <span data-ttu-id="280b3-105">L'app deve annusare queste `SameSite`versioni e omettere .</span><span class="sxs-lookup"><span data-stu-id="280b3-105">The app needs to sniff these versions and omit `SameSite`.</span></span>

<span data-ttu-id="280b3-106">Per una discussione su questo problema, vedere [dotnet/aspnetcore-14996](https://github.com/dotnet/aspnetcore/issues/14996).</span><span class="sxs-lookup"><span data-stu-id="280b3-106">For discussion on this issue, see [dotnet/aspnetcore#14996](https://github.com/dotnet/aspnetcore/issues/14996).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="280b3-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="280b3-107">Version introduced</span></span>

<span data-ttu-id="280b3-108">3.1 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="280b3-108">3.1 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="280b3-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="280b3-109">Old behavior</span></span>

<span data-ttu-id="280b3-110">`SameSite`è una bozza di estensione standard 2016 per i cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="280b3-110">`SameSite` is a 2016 draft standard extension to HTTP cookies.</span></span> <span data-ttu-id="280b3-111">Ha lo scopo di mitigare Cross-Site Request Forgery (CSRF).</span><span class="sxs-lookup"><span data-stu-id="280b3-111">It's intended to mitigate Cross-Site Request Forgery (CSRF).</span></span> <span data-ttu-id="280b3-112">Questo è stato originariamente progettato come una caratteristica che i server avrebbero optare per con l'aggiunta di nuovi parametri.</span><span class="sxs-lookup"><span data-stu-id="280b3-112">This was originally designed as a feature the servers would opt into by adding the new parameters.</span></span> <span data-ttu-id="280b3-113">ASP.NET Core 2.0 ha `SameSite`aggiunto il supporto iniziale per .</span><span class="sxs-lookup"><span data-stu-id="280b3-113">ASP.NET Core 2.0 added initial support for `SameSite`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="280b3-114">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="280b3-114">New behavior</span></span>

<span data-ttu-id="280b3-115">Google ha proposto una nuova bozza di standard non compatibile con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="280b3-115">Google proposed a new draft standard that isn't backwards compatible.</span></span> <span data-ttu-id="280b3-116">Lo standard cambia la `Lax` modalità predefinita `None` in e aggiunge una nuova voce per rifiutare esplicitamente. `Lax` è sufficiente per la maggior parte dei cookie dell'app; tuttavia, interrompe gli scenari tra siti come OpenID Connect e l'accesso WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="280b3-116">The standard changes the default mode to `Lax` and adds a new entry `None` to opt out. `Lax` suffices for most app cookies; however, it breaks cross-site scenarios like OpenID Connect and WS-Federation login.</span></span> <span data-ttu-id="280b3-117">La maggior parte degli account di accesso OAuth non sono interessati a causa delle differenze nel modo in cui la richiesta scorre.</span><span class="sxs-lookup"><span data-stu-id="280b3-117">Most OAuth logins aren't affected because of differences in how the request flows.</span></span> <span data-ttu-id="280b3-118">Il `None` nuovo parametro causa problemi di compatibilità con i client che hanno implementato lo standard di bozza precedente (ad esempio, iOS 12).</span><span class="sxs-lookup"><span data-stu-id="280b3-118">The new `None` parameter causes compatibility problems with clients that implemented the prior draft standard (for example, iOS 12).</span></span> <span data-ttu-id="280b3-119">Chrome 80 includerà le modifiche.</span><span class="sxs-lookup"><span data-stu-id="280b3-119">Chrome 80 will include the changes.</span></span> <span data-ttu-id="280b3-120">Vedi [Aggiornamenti SameSite](https://www.chromium.org/updates/same-site) per la cronologia di avvio del prodotto Chrome.</span><span class="sxs-lookup"><span data-stu-id="280b3-120">See [SameSite Updates](https://www.chromium.org/updates/same-site) for the Chrome product launch timeline.</span></span>

<span data-ttu-id="280b3-121">ASP.NET Core 3.1 è stato `SameSite` aggiornato per implementare il nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="280b3-121">ASP.NET Core 3.1 has been updated to implement the new `SameSite` behavior.</span></span> <span data-ttu-id="280b3-122">L'aggiornamento ridefinisce `SameSiteMode.None` il `SameSite=None` comportamento di generare e aggiunge un nuovo valore `SameSiteMode.Unspecified` per omettere l'attributo. `SameSite`</span><span class="sxs-lookup"><span data-stu-id="280b3-122">The update redefines the behavior of `SameSiteMode.None` to emit `SameSite=None` and adds a new value `SameSiteMode.Unspecified` to omit the `SameSite` attribute.</span></span> <span data-ttu-id="280b3-123">Tutte le API dei `Unspecified`cookie ora utilizzano , anche se alcuni componenti che utilizzano i cookie impostano valori più specifici per i loro scenari, ad esempio la correlazione OpenID Connect e i cookie nonce.</span><span class="sxs-lookup"><span data-stu-id="280b3-123">All cookie APIs now default to `Unspecified`, though some components that use cookies set values more specific to their scenarios such as the OpenID Connect correlation and nonce cookies.</span></span>

<span data-ttu-id="280b3-124">Per altre modifiche recenti in quest'area, vedere HTTP: Alcune impostazioni [predefinite di SameSite dei cookie sono state modificate](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none)in Nessuno .</span><span class="sxs-lookup"><span data-stu-id="280b3-124">For other recent changes in this area, see [HTTP: Some cookie SameSite defaults changed to None](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none).</span></span> <span data-ttu-id="280b3-125">In ASP.NET Core 3.0, la <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> maggior <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> parte dei valori predefiniti è stata modificata da a (ma che utilizza ancora lo standard precedente).</span><span class="sxs-lookup"><span data-stu-id="280b3-125">In ASP.NET Core 3.0, most defaults were changed from <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> to <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> (but still using the prior standard).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="280b3-126">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="280b3-126">Reason for change</span></span>

<span data-ttu-id="280b3-127">Modifiche del browser e delle specifiche come descritto nel testo precedente.</span><span class="sxs-lookup"><span data-stu-id="280b3-127">Browser and specification changes as outlined in the preceding text.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="280b3-128">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="280b3-128">Recommended action</span></span>

<span data-ttu-id="280b3-129">Le app che interagiscono con siti remoti, ad esempio tramite l'accesso di terze parti, devono:Apps that interact with remote sites, such as through third-party login, need to:</span><span class="sxs-lookup"><span data-stu-id="280b3-129">Apps that interact with remote sites, such as through third-party login, need to:</span></span>

* <span data-ttu-id="280b3-130">Testare tali scenari in più browser.</span><span class="sxs-lookup"><span data-stu-id="280b3-130">Test those scenarios on multiple browsers.</span></span>
* <span data-ttu-id="280b3-131">Applicare il browser dei criteri di cookie attenuando attenuazione discusso in [Supportare i browser meno recenti](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="280b3-131">Apply the cookie policy browser sniffing mitigation discussed in [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="280b3-132">Per il test e le istruzioni di sniffing del browser, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="280b3-132">For testing and browser sniffing instructions, see the following section.</span></span>

##### <a name="determine-if-youre-affected"></a><span data-ttu-id="280b3-133">Determinare se si è interessati</span><span class="sxs-lookup"><span data-stu-id="280b3-133">Determine if you're affected</span></span>

<span data-ttu-id="280b3-134">Testare l'app Web usando una versione client che può attivare il nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="280b3-134">Test your web app using a client version that can opt into the new behavior.</span></span> <span data-ttu-id="280b3-135">Chrome, Firefox e Microsoft Edge Chromium hanno tutti nuovi flag di funzionalità opt-in che possono essere utilizzati per il test.</span><span class="sxs-lookup"><span data-stu-id="280b3-135">Chrome, Firefox, and Microsoft Edge Chromium all have new opt-in feature flags that can be used for testing.</span></span> <span data-ttu-id="280b3-136">Verifica che la tua app sia compatibile con le versioni client meno recenti dopo aver applicato le patch, in particolare Safari.</span><span class="sxs-lookup"><span data-stu-id="280b3-136">Verify that your app is compatible with older client versions after you've applied the patches, especially Safari.</span></span> <span data-ttu-id="280b3-137">Per ulteriori informazioni, consultate [Supportare i browser meno recenti.](#support-older-browsers)</span><span class="sxs-lookup"><span data-stu-id="280b3-137">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="chrome"></a><span data-ttu-id="280b3-138">Chrome</span><span class="sxs-lookup"><span data-stu-id="280b3-138">Chrome</span></span>

<span data-ttu-id="280b3-139">Chrome 78 e versioni successive producono risultati fuorvianti dei test.</span><span class="sxs-lookup"><span data-stu-id="280b3-139">Chrome 78 and later yield misleading test results.</span></span> <span data-ttu-id="280b3-140">Tali versioni hanno una mitigazione temporanea in atto e consentono i cookie di meno di due minuti.</span><span class="sxs-lookup"><span data-stu-id="280b3-140">Those versions have a temporary mitigation in place and allow cookies less than two minutes old.</span></span> <span data-ttu-id="280b3-141">Con i flag di test appropriati abilitati, Chrome 76 e 77 producono risultati più accurati.</span><span class="sxs-lookup"><span data-stu-id="280b3-141">With the appropriate test flags enabled, Chrome 76 and 77 yield more accurate results.</span></span> <span data-ttu-id="280b3-142">Per testare il `chrome://flags/#same-site-by-default-cookies` nuovo comportamento, attivare o disattivare l'opzione.To test the new behavior, toggle to enabled.</span><span class="sxs-lookup"><span data-stu-id="280b3-142">To test the new behavior, toggle `chrome://flags/#same-site-by-default-cookies` to enabled.</span></span> <span data-ttu-id="280b3-143">Chrome 75 e versioni precedenti sono `None` segnalati per non riuscire con la nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="280b3-143">Chrome 75 and earlier are reported to fail with the new `None` setting.</span></span> <span data-ttu-id="280b3-144">Per ulteriori informazioni, consultate [Supportare i browser meno recenti.](#support-older-browsers)</span><span class="sxs-lookup"><span data-stu-id="280b3-144">For more information, see [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="280b3-145">Google non rende disponibili le versioni precedenti di Chrome.</span><span class="sxs-lookup"><span data-stu-id="280b3-145">Google doesn't make older Chrome versions available.</span></span> <span data-ttu-id="280b3-146">È possibile, tuttavia, scaricare le versioni precedenti di Chromium, che sarà sufficiente per il test.</span><span class="sxs-lookup"><span data-stu-id="280b3-146">You can, however, download older versions of Chromium, which will suffice for testing.</span></span> <span data-ttu-id="280b3-147">Seguire le istruzioni riportate in [Download Chromium](https://www.chromium.org/getting-involved/download-chromium).</span><span class="sxs-lookup"><span data-stu-id="280b3-147">Follow the instructions at [Download Chromium](https://www.chromium.org/getting-involved/download-chromium).</span></span>

* [<span data-ttu-id="280b3-148">Cromo 76 Win64</span><span class="sxs-lookup"><span data-stu-id="280b3-148">Chromium 76 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [<span data-ttu-id="280b3-149">Cromo 74 Win64</span><span class="sxs-lookup"><span data-stu-id="280b3-149">Chromium 74 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a><span data-ttu-id="280b3-150">Safari</span><span class="sxs-lookup"><span data-stu-id="280b3-150">Safari</span></span>

<span data-ttu-id="280b3-151">Safari 12 ha implementato rigorosamente la bozza precedente `None` e non riesce se vede il nuovo valore nei cookie.</span><span class="sxs-lookup"><span data-stu-id="280b3-151">Safari 12 strictly implemented the prior draft and fails if it sees the new `None` value in cookies.</span></span> <span data-ttu-id="280b3-152">Questo deve essere evitato tramite il codice sniffing del browser mostrato in [Supporta i browser più vecchi](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="280b3-152">This must be avoided via the browser sniffing code shown in [Support older browsers](#support-older-browsers).</span></span> <span data-ttu-id="280b3-153">Assicurati di testare Safari 12 e 13, nonché gli accessi basati su WebKit in stile sistema operativo utilizzando Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL) o qualsiasi libreria in uso.</span><span class="sxs-lookup"><span data-stu-id="280b3-153">Ensure you test Safari 12 and 13 as well as WebKit-based, OS-style logins using Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL), or whichever library you're using.</span></span> <span data-ttu-id="280b3-154">Il problema dipende dalla versione del sistema operativo sottostante.</span><span class="sxs-lookup"><span data-stu-id="280b3-154">The problem is dependent on the underlying OS version.</span></span> <span data-ttu-id="280b3-155">OSX Mojave 10.14 e iOS 12 sono noti per avere problemi di compatibilità con il nuovo comportamento.</span><span class="sxs-lookup"><span data-stu-id="280b3-155">OSX Mojave 10.14 and iOS 12 are known to have compatibility problems with the new behavior.</span></span> <span data-ttu-id="280b3-156">L'aggiornamento a OSX Catalina 10.15 o iOS 13 risolve il problema.</span><span class="sxs-lookup"><span data-stu-id="280b3-156">Upgrading to OSX Catalina 10.15 or iOS 13 fixes the problem.</span></span> <span data-ttu-id="280b3-157">Safari non dispone attualmente di un flag di consenso esplicito per testare il nuovo comportamento delle specifiche.</span><span class="sxs-lookup"><span data-stu-id="280b3-157">Safari doesn't currently have an opt-in flag for testing the new specification behavior.</span></span>

##### <a name="firefox"></a><span data-ttu-id="280b3-158">Firefox</span><span class="sxs-lookup"><span data-stu-id="280b3-158">Firefox</span></span>

<span data-ttu-id="280b3-159">Il supporto Firefox per il nuovo standard può essere testato sulla `about:config` versione 68 `network.cookie.sameSite.laxByDefault`e successive, attivando la pagina con il flag di funzionalità .</span><span class="sxs-lookup"><span data-stu-id="280b3-159">Firefox support for the new standard can be tested on version 68 and later by opting in on the `about:config` page with the feature flag `network.cookie.sameSite.laxByDefault`.</span></span> <span data-ttu-id="280b3-160">Non sono stati segnalati problemi di compatibilità sulle versioni precedenti di Firefox.</span><span class="sxs-lookup"><span data-stu-id="280b3-160">No compatibility issues have been reported on older versions of Firefox.</span></span>

##### <a name="microsoft-edge"></a><span data-ttu-id="280b3-161">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="280b3-161">Microsoft Edge</span></span>

<span data-ttu-id="280b3-162">Mentre Microsoft Edge supporta `SameSite` il vecchio standard, a partire dalla versione 44 non ha avuto problemi di compatibilità con il nuovo standard.</span><span class="sxs-lookup"><span data-stu-id="280b3-162">While Microsoft Edge supports the old `SameSite` standard, as of version 44 it didn't have any compatibility problems with the new standard.</span></span>

##### <a name="microsoft-edge-chromium"></a><span data-ttu-id="280b3-163">Cromo Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="280b3-163">Microsoft Edge Chromium</span></span>

<span data-ttu-id="280b3-164">Il flag `edge://flags/#same-site-by-default-cookies`di funzionalità è .</span><span class="sxs-lookup"><span data-stu-id="280b3-164">The feature flag is `edge://flags/#same-site-by-default-cookies`.</span></span> <span data-ttu-id="280b3-165">Nessun problema di compatibilità sono stati osservati durante il test con Microsoft Edge Chromium 78.</span><span class="sxs-lookup"><span data-stu-id="280b3-165">No compatibility issues were observed when testing with Microsoft Edge Chromium 78.</span></span>

##### <a name="electron"></a><span data-ttu-id="280b3-166">Elettrone</span><span class="sxs-lookup"><span data-stu-id="280b3-166">Electron</span></span>

<span data-ttu-id="280b3-167">Le versioni di Electron includono versioni precedenti di Chromium.</span><span class="sxs-lookup"><span data-stu-id="280b3-167">Versions of Electron include older versions of Chromium.</span></span> <span data-ttu-id="280b3-168">Ad esempio, la versione di Electron utilizzata da Microsoft Teams è Chromium 66, che presenta il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="280b3-168">For example, the version of Electron used by Microsoft Teams is Chromium 66, which exhibits the older behavior.</span></span> <span data-ttu-id="280b3-169">Eseguire il proprio test di compatibilità con la versione di Electron utilizzata dal prodotto.</span><span class="sxs-lookup"><span data-stu-id="280b3-169">Perform your own compatibility testing with the version of Electron your product uses.</span></span> <span data-ttu-id="280b3-170">Per ulteriori informazioni, consultate [Supportare i browser meno recenti.](#support-older-browsers)</span><span class="sxs-lookup"><span data-stu-id="280b3-170">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="support-older-browsers"></a><span data-ttu-id="280b3-171">Supporta browser meno recenti</span><span class="sxs-lookup"><span data-stu-id="280b3-171">Support older browsers</span></span>

<span data-ttu-id="280b3-172">Lo standard 2016 `SameSite` ha imposto che `SameSite=Strict` i valori sconosciuti siano trattati come valori.</span><span class="sxs-lookup"><span data-stu-id="280b3-172">The 2016 `SameSite` standard mandated that unknown values be treated as `SameSite=Strict` values.</span></span> <span data-ttu-id="280b3-173">Di conseguenza, tutti i browser meno recenti che `SameSite` supportano lo `None`standard originale potrebbero interrompersi quando vedono una proprietà con un valore di .</span><span class="sxs-lookup"><span data-stu-id="280b3-173">Consequently, any older browsers that support the original standard may break when they see a `SameSite` property with a value of `None`.</span></span> <span data-ttu-id="280b3-174">Le app Web devono implementare lo sniffing del browser se intendono supportare questi vecchi browser.</span><span class="sxs-lookup"><span data-stu-id="280b3-174">Web apps must implement browser sniffing if they intend to support these old browsers.</span></span> <span data-ttu-id="280b3-175">ASP.NET Core non implementa lo sniffing `User-Agent` del browser perché i valori dell'intestazione della richiesta sono altamente instabili e cambiano su base settimanale.</span><span class="sxs-lookup"><span data-stu-id="280b3-175">ASP.NET Core doesn't implement browser sniffing for you because `User-Agent` request header values are highly unstable and change on a weekly basis.</span></span> <span data-ttu-id="280b3-176">Al contrario, un punto di estensione `User-Agent`nei criteri dei cookie consente di aggiungere una logica specifica.</span><span class="sxs-lookup"><span data-stu-id="280b3-176">Instead, an extension point in the cookie policy allows you to add `User-Agent`-specific logic.</span></span>

<span data-ttu-id="280b3-177">In *Startup.cs*aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="280b3-177">In *Startup.cs*, add the following code:</span></span>

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

##### <a name="opt-out-switches"></a><span data-ttu-id="280b3-178">Interruttori di opt-out</span><span class="sxs-lookup"><span data-stu-id="280b3-178">Opt-out switches</span></span>

<span data-ttu-id="280b3-179">L'opzione `Microsoft.AspNetCore.SuppressSameSiteNone` di compatibilità consente di rifiutare temporaneamente l'esclusione dal nuovo ASP.NET comportamento dei cookie Core.</span><span class="sxs-lookup"><span data-stu-id="280b3-179">The `Microsoft.AspNetCore.SuppressSameSiteNone` compatibility switch enables you to temporarily opt out of the new ASP.NET Core cookie behavior.</span></span> <span data-ttu-id="280b3-180">Aggiungere il codice JSON seguente a un file runtimeconfig.template.json nel progetto:Add the following JSON to a *runtimeconfig.template.json* file in your project:</span><span class="sxs-lookup"><span data-stu-id="280b3-180">Add the following JSON to a *runtimeconfig.template.json* file in your project:</span></span>

```json
{
  "configProperties": {
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true"
  }
}
```

##### <a name="other-versions"></a><span data-ttu-id="280b3-181">Altre versioni</span><span class="sxs-lookup"><span data-stu-id="280b3-181">Other Versions</span></span>

<span data-ttu-id="280b3-182">Patch `SameSite` correlate sono in arrivo per:</span><span class="sxs-lookup"><span data-stu-id="280b3-182">Related `SameSite` patches are forthcoming for:</span></span>

* <span data-ttu-id="280b3-183">ASP.NET Core 2.1, 2.2 e 3.0</span><span class="sxs-lookup"><span data-stu-id="280b3-183">ASP.NET Core 2.1, 2.2, and 3.0</span></span>
* <span data-ttu-id="280b3-184">`Microsoft.Owin`4.1</span><span class="sxs-lookup"><span data-stu-id="280b3-184">`Microsoft.Owin` 4.1</span></span>
* <span data-ttu-id="280b3-185">`System.Web`(per .NET Framework 4.7.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="280b3-185">`System.Web` (for .NET Framework 4.7.2 and later)</span></span>

#### <a name="category"></a><span data-ttu-id="280b3-186">Category</span><span class="sxs-lookup"><span data-stu-id="280b3-186">Category</span></span>

<span data-ttu-id="280b3-187">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="280b3-187">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="280b3-188">API interessate</span><span class="sxs-lookup"><span data-stu-id="280b3-188">Affected APIs</span></span>

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
