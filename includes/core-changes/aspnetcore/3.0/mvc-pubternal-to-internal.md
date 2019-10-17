---
ms.openlocfilehash: 09fd95ba5f3aee59f2abdfbb4e64eb6202e2b873
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394426"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a>MVC: i tipi "Pubternal" sono stati modificati in Internal

In ASP.NET Core 3,0 tutti i tipi "pubternal" in MVC sono stati aggiornati per essere `public` in uno spazio dei nomi supportato o `internal`, a seconda delle esigenze.

#### <a name="change-description"></a>Descrizione della modifica

In ASP.NET Core i tipi "pubternal" sono dichiarati come `public`, ma risiedono in uno spazio dei nomi con suffisso @no__t 1. Anche se questi tipi sono `public`, non hanno criteri di supporto e sono soggetti a modifiche di rilievo. Sfortunatamente, l'uso accidentale di questi tipi è stato comune, con conseguente riduzione delle modifiche apportate a questi progetti e della possibilità di mantenere il Framework.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Alcuni tipi in MVC sono `public`, ma in uno spazio dei nomi `.Internal`. Questi tipi non hanno criteri di supporto e sono soggetti a modifiche di rilievo.

#### <a name="new-behavior"></a>Nuovo comportamento

Tutti questi tipi vengono aggiornati per essere `public` in uno spazio dei nomi supportato o contrassegnati come `internal`.

#### <a name="reason-for-change"></a>Motivo della modifica

L'uso accidentale dei tipi "pubternal" è stato comune, con conseguente riduzione delle modifiche apportate a questi progetti e della possibilità di mantenere il Framework.

#### <a name="recommended-action"></a>Azione consigliata

Se si usano i tipi che sono diventati realmente `public` e sono stati spostati in un nuovo spazio dei nomi supportato, aggiornare i riferimenti in modo che corrispondano ai nuovi spazi dei nomi.

Se si usano i tipi che sono stati contrassegnati come `internal`, sarà necessario trovare un'alternativa. I tipi "pubternal" precedenti non erano mai supportati per l'uso pubblico. Se in questi spazi dei nomi sono presenti tipi specifici che sono fondamentali per le app, archiviare un problema in [ASPNET/AspNetCore](https://github.com/aspnet/AspNetCore/issues). È possibile che vengano apportate alcune considerazioni per rendere i tipi richiesti `public`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Questa modifica include i tipi negli spazi dei nomi seguenti:

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
