---
ms.openlocfilehash: bbf8a02096a4a654a041cfe17c760939fc17f2f5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393927"
---
### <a name="session-state-obsolete-apis-removed"></a>Stato sessione: API obsolete rimosse 

Sono state rimosse le API obsolete per la configurazione dei cookie di sessione. Per altre informazioni, vedere [ASPNET/annunciations # 257](https://github.com/aspnet/Announcements/issues/257).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica impone la coerenza tra le API per la configurazione delle funzionalità che usano i cookie.

#### <a name="recommended-action"></a>Azione consigliata

Migrare l'utilizzo delle API rimosse alle sostituzioni più recenti. Si consideri l'esempio seguente in `Startup.ConfigureServices`:

```csharp
public void ConfigureServices(ServiceCollection services)
{
    services.AddSession(options =>
    {
        // Removed obsolete APIs
        options.CookieName = "SessionCookie";
        options.CookieDomain = "contoso.com";
        options.CookiePath = "/";
        options.CookieHttpOnly = true;
        options.CookieSecure = CookieSecurePolicy.Always;

        // new API
        options.Cookie.Name = "SessionCookie";
        options.Cookie.Domain = "contoso.com";
        options.Cookie.Path = "/";
        options.Cookie.HttpOnly = true;
        options.Cookie.SecurePolicy = CookieSecurePolicy.Always;
    });
}
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieName?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure?displayProperty=fullName>

<!-- 

#### Affected APIs

- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieName`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure`

-->
