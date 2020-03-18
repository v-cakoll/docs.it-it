---
ms.openlocfilehash: 5741e8cdd51e00d5459c4c1032a56682429aab17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901834"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a>MVC: i tipi "Pubternal" sono cambiati in interni

In ASP.NET Core 3.0, tutti i tipi "pubternal" in MVC sono stati aggiornati in modo che siano `public` in uno spazio dei nomi supportato o `internal` in base alle esigenze.

#### <a name="change-description"></a>Descrizione modifica:

In ASP.NET Core, i tipi "pubternal" vengono dichiarati come `public` ma risiedono in uno `.Internal`spazio dei nomi con suffisso .suffix. Sebbene questi `public`tipi siano , non hanno criteri di supporto e sono soggetti a modifiche di rilievo. Sfortunatamente, l'uso accidentale di questi tipi è stato comune, con conseguente interruzione delle modifiche a questi progetti e limitando la capacità di mantenere il framework.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Alcuni tipi in `public` MVC `.Internal` erano ma in uno spazio dei nomi. Questi tipi non avevano una politica di supporto e sono stati soggetti a modifiche di rilievo.

#### <a name="new-behavior"></a>Nuovo comportamento

Tutti questi tipi vengono `public` aggiornati per essere `internal`in uno spazio dei nomi supportato o contrassegnati come .

#### <a name="reason-for-change"></a>Motivo della modifica

L'uso accidentale dei tipi "pubternal" è stato comune, con conseguente modifiche di rilievo a questi progetti e limitando la capacità di mantenere il framework.

#### <a name="recommended-action"></a>Azione consigliata

Se si utilizzano tipi che `public` sono diventati veramente e sono stati spostati in un nuovo spazio dei nomi supportato, aggiornare i riferimenti in modo che corrispondano ai nuovi spazi dei nomi.

Se si utilizzano tipi che `internal`sono stati contrassegnati come , è necessario trovare un'alternativa. I tipi "pubternal" in precedenza non erano mai supportati per l'uso pubblico. Se in questi spazi dei nomi sono presenti tipi specifici critici per le app, presentare un problema in [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues). È possibile tenere conto `public`della creazione dei tipi richiesti.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Questa modifica include i tipi negli spazi dei nomi seguenti:This change includes types in the following namespaces:

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

<!--

#### Affected APIs

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

-->
