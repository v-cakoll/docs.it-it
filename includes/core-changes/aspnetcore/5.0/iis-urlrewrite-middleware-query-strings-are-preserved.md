---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325217"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a>IIS: vengono mantenute le stringhe di query del middleware UrlRewrite

Un difetto del middleware UrlRewrite IIS ha impedito la conservazione della stringa di query nelle regole di riscrittura. Questo difetto è stato corretto per garantire la coerenza con il comportamento del modulo UrlRewrite di IIS.

Per informazioni, vedere Issue [DotNet/aspnetcore # 22972](https://github.com/dotnet/aspnetcore/issues/22972).

#### <a name="version-introduced"></a>Versione introdotta

ASP.NET Core 5,0 Preview 7

#### <a name="old-behavior"></a>Comportamento precedente

Si consideri la regola di riscrittura seguente:

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

La regola precedente non aggiunge la stringa di query. URI come `/about?id=1` reindirizza a `/contact` anziché `/contact?id=1` . `appendQueryString`Per impostazione predefinita, viene impostato anche l'attributo `true` .

#### <a name="new-behavior"></a>Nuovo comportamento

La stringa di query viene mantenuta. L'URI dell'esempio in un [comportamento precedente](#old-behavior) è `/contact?id=1` .

#### <a name="reason-for-change"></a>Motivo della modifica

Il comportamento precedente non corrisponde al comportamento del modulo UrlRewrite di IIS. Per supportare il porting tra il middleware e il modulo, l'obiettivo è mantenere comportamenti coerenti.

#### <a name="recommended-action"></a>Azione consigliata

Se è preferibile il comportamento della rimozione della stringa di query, impostare l' `action` elemento su `appendQueryString="false"` .

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
