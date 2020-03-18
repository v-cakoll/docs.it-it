---
ms.openlocfilehash: 3cc07eef109b9096bc5a5fbcd1ea098a23b2155f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968141"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a>HTTP: Le modifiche del browser SameSite influiscono sull'autenticazione

Alcuni browser, come Chrome e Firefox, hanno apportato `SameSite` modifiche di rilievo alle loro implementazioni di per i cookie. Le modifiche influiscono sugli scenari di autenticazione remota, ad esempio `SameSite=None`OpenID Connect e WS-Federation, che devono rifiutare esplicitamente l'invio di . Tuttavia, `SameSite=None` si rompe su iOS 12 e alcune versioni precedenti di altri browser. L'app deve annusare queste `SameSite`versioni e omettere .

Per una discussione su questo problema, vedere [dotnet/aspnetcore-14996](https://github.com/dotnet/aspnetcore/issues/14996).

#### <a name="version-introduced"></a>Versione introdotta

3.1 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

`SameSite`è una bozza di estensione standard 2016 per i cookie HTTP. Ha lo scopo di mitigare Cross-Site Request Forgery (CSRF). Questo è stato originariamente progettato come una caratteristica che i server avrebbero optare per con l'aggiunta di nuovi parametri. ASP.NET Core 2.0 ha `SameSite`aggiunto il supporto iniziale per .

#### <a name="new-behavior"></a>Nuovo comportamento

Google ha proposto una nuova bozza di standard non compatibile con le versioni precedenti. Lo standard cambia la `Lax` modalità predefinita `None` in e aggiunge una nuova voce per rifiutare esplicitamente. `Lax` è sufficiente per la maggior parte dei cookie dell'app; tuttavia, interrompe gli scenari tra siti come OpenID Connect e l'accesso WS-Federation. La maggior parte degli account di accesso OAuth non sono interessati a causa delle differenze nel modo in cui la richiesta scorre. Il `None` nuovo parametro causa problemi di compatibilità con i client che hanno implementato lo standard di bozza precedente (ad esempio, iOS 12). Chrome 80 includerà le modifiche. Vedi [Aggiornamenti SameSite](https://www.chromium.org/updates/same-site) per la cronologia di avvio del prodotto Chrome.

ASP.NET Core 3.1 è stato `SameSite` aggiornato per implementare il nuovo comportamento. L'aggiornamento ridefinisce `SameSiteMode.None` il `SameSite=None` comportamento di generare e aggiunge un nuovo valore `SameSiteMode.Unspecified` per omettere l'attributo. `SameSite` Tutte le API dei `Unspecified`cookie ora utilizzano , anche se alcuni componenti che utilizzano i cookie impostano valori più specifici per i loro scenari, ad esempio la correlazione OpenID Connect e i cookie nonce.

Per altre modifiche recenti in quest'area, vedere HTTP: Alcune impostazioni [predefinite di SameSite dei cookie sono state modificate](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none)in Nessuno . In ASP.NET Core 3.0, la <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> maggior <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> parte dei valori predefiniti è stata modificata da a (ma che utilizza ancora lo standard precedente).

#### <a name="reason-for-change"></a>Motivo della modifica

Modifiche del browser e delle specifiche come descritto nel testo precedente.

#### <a name="recommended-action"></a>Azione consigliata

Le app che interagiscono con siti remoti, ad esempio tramite l'accesso di terze parti, devono:Apps that interact with remote sites, such as through third-party login, need to:

* Testare tali scenari in più browser.
* Applicare il browser dei criteri di cookie attenuando attenuazione discusso in [Supportare i browser meno recenti](#support-older-browsers).

Per il test e le istruzioni di sniffing del browser, vedere la sezione seguente.

##### <a name="determine-if-youre-affected"></a>Determinare se si è interessati

Testare l'app Web usando una versione client che può attivare il nuovo comportamento. Chrome, Firefox e Microsoft Edge Chromium hanno tutti nuovi flag di funzionalità opt-in che possono essere utilizzati per il test. Verifica che la tua app sia compatibile con le versioni client meno recenti dopo aver applicato le patch, in particolare Safari. Per ulteriori informazioni, consultate [Supportare i browser meno recenti.](#support-older-browsers)

##### <a name="chrome"></a>Chrome

Chrome 78 e versioni successive producono risultati fuorvianti dei test. Tali versioni hanno una mitigazione temporanea in atto e consentono i cookie di meno di due minuti. Con i flag di test appropriati abilitati, Chrome 76 e 77 producono risultati più accurati. Per testare il `chrome://flags/#same-site-by-default-cookies` nuovo comportamento, attivare o disattivare l'opzione.To test the new behavior, toggle to enabled. Chrome 75 e versioni precedenti sono `None` segnalati per non riuscire con la nuova impostazione. Per ulteriori informazioni, consultate [Supportare i browser meno recenti.](#support-older-browsers)

Google non rende disponibili le versioni precedenti di Chrome. È possibile, tuttavia, scaricare le versioni precedenti di Chromium, che sarà sufficiente per il test. Seguire le istruzioni riportate in [Download Chromium](https://www.chromium.org/getting-involved/download-chromium).

* [Cromo 76 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [Cromo 74 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a>Safari

Safari 12 ha implementato rigorosamente la bozza precedente `None` e non riesce se vede il nuovo valore nei cookie. Questo deve essere evitato tramite il codice sniffing del browser mostrato in [Supporta i browser più vecchi](#support-older-browsers). Assicurati di testare Safari 12 e 13, nonché gli accessi basati su WebKit in stile sistema operativo utilizzando Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL) o qualsiasi libreria in uso. Il problema dipende dalla versione del sistema operativo sottostante. OSX Mojave 10.14 e iOS 12 sono noti per avere problemi di compatibilità con il nuovo comportamento. L'aggiornamento a OSX Catalina 10.15 o iOS 13 risolve il problema. Safari non dispone attualmente di un flag di consenso esplicito per testare il nuovo comportamento delle specifiche.

##### <a name="firefox"></a>Firefox

Il supporto Firefox per il nuovo standard può essere testato sulla `about:config` versione 68 `network.cookie.sameSite.laxByDefault`e successive, attivando la pagina con il flag di funzionalità . Non sono stati segnalati problemi di compatibilità sulle versioni precedenti di Firefox.

##### <a name="microsoft-edge"></a>Microsoft Edge

Mentre Microsoft Edge supporta `SameSite` il vecchio standard, a partire dalla versione 44 non ha avuto problemi di compatibilità con il nuovo standard.

##### <a name="microsoft-edge-chromium"></a>Cromo Microsoft Edge

Il flag `edge://flags/#same-site-by-default-cookies`di funzionalità è . Nessun problema di compatibilità sono stati osservati durante il test con Microsoft Edge Chromium 78.

##### <a name="electron"></a>Elettrone

Le versioni di Electron includono versioni precedenti di Chromium. Ad esempio, la versione di Electron utilizzata da Microsoft Teams è Chromium 66, che presenta il comportamento precedente. Eseguire il proprio test di compatibilità con la versione di Electron utilizzata dal prodotto. Per ulteriori informazioni, consultate [Supportare i browser meno recenti.](#support-older-browsers)

##### <a name="support-older-browsers"></a>Supporta browser meno recenti

Lo standard 2016 `SameSite` ha imposto che `SameSite=Strict` i valori sconosciuti siano trattati come valori. Di conseguenza, tutti i browser meno recenti che `SameSite` supportano lo `None`standard originale potrebbero interrompersi quando vedono una proprietà con un valore di . Le app Web devono implementare lo sniffing del browser se intendono supportare questi vecchi browser. ASP.NET Core non implementa lo sniffing `User-Agent` del browser perché i valori dell'intestazione della richiesta sono altamente instabili e cambiano su base settimanale. Al contrario, un punto di estensione `User-Agent`nei criteri dei cookie consente di aggiungere una logica specifica.

In *Startup.cs*aggiungere il codice seguente:

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

##### <a name="opt-out-switches"></a>Interruttori di opt-out

L'opzione `Microsoft.AspNetCore.SuppressSameSiteNone` di compatibilità consente di rifiutare temporaneamente l'esclusione dal nuovo ASP.NET comportamento dei cookie Core. Aggiungere il codice JSON seguente a un file runtimeconfig.template.json nel progetto:Add the following JSON to a *runtimeconfig.template.json* file in your project:

```json
{
  "configProperties": {
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true"
  }
}
```

##### <a name="other-versions"></a>Altre versioni

Patch `SameSite` correlate sono in arrivo per:

* ASP.NET Core 2.1, 2.2 e 3.0
* `Microsoft.Owin`4.1
* `System.Web`(per .NET Framework 4.7.2 e versioni successive)

#### <a name="category"></a>Category

ASP.NET

#### <a name="affected-apis"></a>API interessate

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
