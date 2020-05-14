---
ms.openlocfilehash: 52b9caf2d5b3d44c0c6349501dafc371541fdd70
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396341"
---
### <a name="pubternal-apis-removed"></a>API "Pubternal" rimosse

Per gestire meglio la superficie dell'API pubblica di ASP.NET Core, la maggior parte dei tipi negli `*.Internal` spazi dei nomi (detti :::no-loc text="\"pubternal\""::: API) è diventata effettivamente interna. I membri di questi spazi dei nomi non venivano mai progettati per essere supportati come API pubbliche. Le API possono interrompere le versioni secondarie e spesso. Il codice che dipende da queste API si interrompe quando si esegue l'aggiornamento a ASP.NET Core 3,0.

Per altre informazioni, vedere [DotNet/aspnetcore # 4932](https://github.com/dotnet/aspnetcore/issues/4932) e [DotNet/aspnetcore # 11312](https://github.com/dotnet/aspnetcore/issues/11312).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le API interessate sono contrassegnate con il `public` modificatore di accesso e sono presenti negli `*.Internal` spazi dei nomi.

#### <a name="new-behavior"></a>Nuovo comportamento

Le API interessate sono contrassegnate con il modificatore di accesso [interno (~/docs/CSharp/Language-Reference/Keywords/Internal.MD) e non possono più essere utilizzate dal codice esterno a tale assembly.

#### <a name="reason-for-change"></a>Motivo della modifica

Le linee guida per queste :::no-loc text="\"pubternal\""::: API sono:

* Potrebbe cambiare senza preavviso.
* Non sono soggette ai criteri .NET per evitare modifiche di rilievo.

Lasciare le API `public` (anche negli `*.Internal` spazi dei nomi) è stato confuso per i clienti.

#### <a name="recommended-action"></a>Azione consigliata

Interrompere l'uso di queste :::no-loc text="\"pubternal\""::: API. In caso di domande sulle API alternative, aprire un problema nel repository [DotNet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) .

Si consideri, ad esempio, il codice di buffer delle richieste HTTP seguente in un progetto ASP.NET Core 2,2. Il `EnableRewind` metodo di estensione esiste nello `Microsoft.AspNetCore.Http.Internal` spazio dei nomi.

```csharp
HttpContext.Request.EnableRewind();
```

In un progetto ASP.NET Core 3,0, sostituire la `EnableRewind` chiamata con una chiamata al `EnableBuffering` metodo di estensione. La funzionalità di memorizzazione nel buffer delle richieste funziona come in passato. `EnableBuffering`chiama l' `internal` API Now.

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Tutte le API negli `Microsoft.AspNetCore.*` `Microsoft.Extensions.*` spazi dei nomi e che presentano un `Internal` segmento nel nome dello spazio dei nomi. Ad esempio:

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
