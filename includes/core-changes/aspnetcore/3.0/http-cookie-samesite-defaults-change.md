---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74282512"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a>HTTP: alcuni cookie navigava sullostesso sito predefiniti sono stati modificati in None

`SameSite` è un'opzione per i cookie che consentono di attenuare alcuni attacchi di richiesta intersito falsa (CSRF). Quando questa opzione è stata introdotta inizialmente, sono state usate impostazioni predefinite incoerenti tra varie API ASP.NET Core. L'incoerenza ha determinato risultati confusi. A partire da ASP.NET Core 3,0, queste impostazioni predefinite sono allineate meglio. È necessario acconsentire esplicitamente a questa funzionalità in base ai singoli componenti.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

API ASP.NET Core simili utilizzano valori <xref:Microsoft.AspNetCore.Http.SameSiteMode> predefiniti diversi. Un esempio di incoerenza è indicato in `HttpResponse.Cookies.Append(String, String)` e `HttpResponse.Cookies.Append(String, String, CookieOptions)`, che per impostazione predefinita sono rispettivamente `SameSiteMode.None` e `SameSiteMode.Lax`.

#### <a name="new-behavior"></a>Nuovo comportamento

Per impostazione predefinita, tutte le API interessate `SameSiteMode.None`.

#### <a name="reason-for-change"></a>Motivo della modifica

Il valore predefinito è stato modificato in modo da rendere `SameSite` una funzionalità di consenso esplicito.

#### <a name="recommended-action"></a>Azione consigliata

Ogni componente che emette cookie deve decidere se `SameSite` è appropriato per gli scenari. Esaminare l'utilizzo delle API interessate e riconfigurare `SameSite` in base alle esigenze.

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
