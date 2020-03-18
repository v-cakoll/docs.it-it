---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74282512"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a>HTTP: alcune impostazioni predefinite di SameSite dei cookie sono state modificate in Nessuno

`SameSite`è un'opzione per i cookie che può aiutare a mitigare alcuni attacchi CSRF (Cross-Site Request Forgery). Quando questa opzione è stata inizialmente introdotta, i valori predefiniti incoerenti sono stati usati in varie API di ASP.NET Core.When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs. L'incoerenza ha portato a risultati confusi. A partire da ASP.NET Core 3.0, queste impostazioni predefinite sono meglio allineate. È necessario acconsentire esplicitamente a questa funzionalità in base al componente.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Simile ASP.NET API core usavano valori predefiniti <xref:Microsoft.AspNetCore.Http.SameSiteMode> diversi. Un esempio di incoerenza `HttpResponse.Cookies.Append(String, String)` è `HttpResponse.Cookies.Append(String, String, CookieOptions)`visto in `SameSiteMode.None` e `SameSiteMode.Lax`, che per impostazione predefinita è e , rispettivamente.

#### <a name="new-behavior"></a>Nuovo comportamento

Per impostazione predefinita, `SameSiteMode.None`tutte le API interessate vengono .

#### <a name="reason-for-change"></a>Motivo della modifica

Il valore predefinito è `SameSite` stato modificato per creare una funzionalità di consenso esplicito.

#### <a name="recommended-action"></a>Azione consigliata

Ogni componente che emette cookie `SameSite` deve decidere se è appropriato per i propri scenari. Esaminare l'utilizzo delle API interessate e riconfigurare `SameSite` in base alle esigenze.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
