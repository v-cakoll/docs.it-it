---
ms.openlocfilehash: 02602c70689a6d2729e03d3d7230cda5ae7a4994
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901953"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a>HTTP: browser navigava sullostesso sito modifiche che influiscano sull'autenticazione

Alcuni browser, ad esempio Chrome e Firefox, hanno apportato modifiche di rilievo alle implementazioni di `SameSite` per i cookie. Le modifiche influiscano sugli scenari di autenticazione remota, ad esempio OpenID Connect e WS-Federation, che devono rifiutare esplicitamente inviando `SameSite=None`. Tuttavia, `SameSite=None` si interrompe in iOS 12 e in alcune versioni precedenti di altri browser. L'app deve annusare queste versioni e omettere `SameSite`.

Per informazioni su questo problema, vedere [DotNet/aspnetcore # 14996](https://github.com/dotnet/aspnetcore/issues/14996).

#### <a name="version-introduced"></a>Versione introdotta

3,1 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

`SameSite` è un'estensione standard bozza 2016 ai cookie HTTP. È progettato per attenuare la richiesta tra siti falsa (CSRF). Questa operazione è stata originariamente progettata come funzionalità che i server avrebbero acconsentito aggiungendo i nuovi parametri. ASP.NET Core 2,0 è stato aggiunto il supporto iniziale per `SameSite`.

#### <a name="new-behavior"></a>Nuovo comportamento

Google ha proposto un nuovo standard Draft che non è compatibile con le versioni precedenti. Lo standard modifica la modalità predefinita per `Lax` e aggiunge una nuova voce `None` per rifiutare esplicitamente. `Lax` è sufficiente per la maggior parte dei cookie dell'app; Tuttavia, vengono interrotti scenari tra siti come OpenID Connect e l'account di accesso WS-Federation. La maggior parte degli accessi OAuth non è interessata a causa di differenze nel modo in cui la richiesta fluisce. Il nuovo parametro `None` causa problemi di compatibilità con i client che hanno implementato lo standard Draft precedente (ad esempio, iOS 12). Chrome 80 includerà le modifiche. Vedere [aggiornamenti di navigava sullostesso sito](https://www.chromium.org/updates/same-site) per la sequenza temporale di avvio del prodotto Chrome.

ASP.NET Core 3,1 è stato aggiornato per implementare il nuovo comportamento del `SameSite`. L'aggiornamento ridefinisce il comportamento di `SameSiteMode.None` per emettere `SameSite=None` e aggiunge un nuovo valore `SameSiteMode.Unspecified` per omettere l'attributo `SameSite`. Per impostazione predefinita, tutte le API cookie vengono `Unspecified`, anche se alcuni componenti che usano cookie impostano valori più specifici per i relativi scenari, ad esempio i cookie di correlazione e nonce di OpenID Connect.

Per altre modifiche recenti in quest'area, vedere [http: alcuni cookie navigava sullostesso sito predefiniti sono stati modificati in nessuno](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none). In ASP.NET Core 3,0, la maggior parte delle impostazioni predefinite è stata modificata da <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> a <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType>, ma è ancora in uso lo standard precedente.

#### <a name="reason-for-change"></a>Motivo della modifica

Modifiche del browser e delle specifiche come indicato nel testo precedente.

#### <a name="recommended-action"></a>Azione consigliata

Le app che interagiscono con i siti remoti, ad esempio tramite account di accesso di terze parti, devono:

* Testare questi scenari in più browser.
* Applicare la mitigazione dello sniffing del browser criteri cookie descritta in [supportare i browser meno recenti](#support-older-browsers).

Per istruzioni su test e analisi del browser, vedere la sezione seguente.

##### <a name="determine-if-youre-affected"></a>Determinare se si è interessati

Testare l'app Web usando una versione client che può acconsentire esplicitamente al nuovo comportamento. Chrome, Firefox e Microsoft Edge Chromium hanno tutti nuovi flag di funzionalità di consenso esplicito che possono essere usati per i test. Verificare che l'app sia compatibile con le versioni precedenti del client dopo aver applicato le patch, in particolare Safari. Per ulteriori informazioni, vedere [supportare browser meno recenti](#support-older-browsers).

##### <a name="chrome"></a>Chrome

Chrome 78 e versioni successive producono risultati dei test fuorvianti. Queste versioni presentano una mitigazione temporanea e consentono ai cookie meno di due minuti. Con i flag di test appropriati abilitati, Chrome 76 e 77 producono risultati più accurati. Per testare il nuovo comportamento, impostare `chrome://flags/#same-site-by-default-cookies` su abilitato. Chrome 75 e versioni precedenti vengono segnalati per avere esito negativo con la nuova impostazione `None`. Per ulteriori informazioni, vedere [supportare browser meno recenti](#support-older-browsers).

Google non rende disponibili versioni precedenti di Chrome. È possibile, tuttavia, scaricare le versioni precedenti di Chromium, che sarà sufficiente per il test. Seguire le istruzioni riportate in [scaricare Chromium](https://www.chromium.org/getting-involved/download-chromium).

* [Cromo 76 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [Cromo 74 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a>Safari

Safari 12 ha implementato rigorosamente la bozza precedente e ha esito negativo se rileva il nuovo valore `None` nei cookie. Questa operazione deve essere evitata tramite il codice di sniffing del browser illustrato in [supportare i browser meno recenti](#support-older-browsers). Assicurarsi di testare Safari 12 e 13, nonché gli account di accesso basati su WebKit, in stile sistema operativo tramite Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL) o qualsiasi libreria in uso. Il problema dipende dalla versione del sistema operativo sottostante. I problemi di compatibilità con il nuovo comportamento sono noti per OSX Mojave 10,14 e iOS 12. L'aggiornamento a OSX Catalina 10,15 o iOS 13 corregge il problema. Safari non dispone attualmente di un flag di consenso esplicito per il test del nuovo comportamento della specifica.

##### <a name="firefox"></a>Firefox

Il supporto di Firefox per il nuovo standard può essere testato nella versione 68 e successive scegliendo nella pagina `about:config` con il flag funzionalità `network.cookie.sameSite.laxByDefault`. Nessun problema di compatibilità è stato segnalato nelle versioni precedenti di Firefox.

##### <a name="microsoft-edge"></a>Microsoft Edge

Sebbene Microsoft Edge supporti il vecchio `SameSite` standard, a partire dalla versione 44, non ha avuto problemi di compatibilità con il nuovo standard.

##### <a name="microsoft-edge-chromium"></a>Cromo Microsoft Edge

Il flag della funzionalità è `edge://flags/#same-site-by-default-cookies`. Nessun problema di compatibilità rilevato durante il test con Microsoft Edge Chromium 78.

##### <a name="electron"></a>Electron

Le versioni di Electron includono versioni precedenti di cromo. Ad esempio, la versione di Electron usata da Microsoft teams è Chromium 66, che presenta il comportamento precedente. Eseguire test di compatibilità personalizzati con la versione di Electron utilizzata dal prodotto. Per ulteriori informazioni, vedere [supportare browser meno recenti](#support-older-browsers).

##### <a name="support-older-browsers"></a>Supportare i browser meno recenti

2016 `SameSite` standard imposto che i valori sconosciuti vengano considerati come `SameSite=Strict` valori. Di conseguenza, tutti i browser meno recenti che supportano lo standard originale potrebbero interrompersi quando viene visualizzato un `SameSite` proprietà con un valore di `None`. Le app Web devono implementare lo sniffing del browser se intendono supportare questi browser obsoleti. ASP.NET Core non implementa lo sniffing del browser perché `User-Agent` i valori dell'intestazione della richiesta sono altamente instabili e cambiano su base settimanale. Un punto di estensione nel criterio dei cookie consente invece di aggiungere la logica specifica del `User-Agent`.

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

##### <a name="opt-out-switches"></a>Opzioni di rifiuto esplicito

Il `Microsoft.AspNetCore.SuppressSameSiteNone` opzione di compatibilità consente di rifiutare temporaneamente il nuovo comportamento di ASP.NET Core cookie. Aggiungere il codice JSON seguente a un file *runtimeconfig. template. JSON* nel progetto:

```json
{ 
  "configProperties": { 
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true" 
  } 
}
```

##### <a name="other-versions"></a>Altre versioni

Le patch `SameSite` correlate sono imminenti per:

* ASP.NET Core 2,1, 2,2 e 3,0
* `Microsoft.Owin` 4,1
* `System.Web` (per .NET Framework 4.7.2 e versioni successive)

#### <a name="category"></a>Categoria

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
