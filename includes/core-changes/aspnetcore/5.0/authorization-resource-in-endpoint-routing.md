---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441550"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a>Autorizzazione: la risorsa nel routing dell'endpoint è HttpContext

Quando si usa il routing degli endpoint in ASP.NET Core 3,1, la risorsa usata per l'autorizzazione è l'endpoint. Questo approccio non è sufficiente per ottenere l'accesso ai dati della route ( <xref:Microsoft.AspNetCore.Routing.RouteData> ). In precedenza in MVC <xref:Microsoft.AspNetCore.Http.HttpContext> è stata passata una risorsa, che consente l'accesso sia all'endpoint ( <xref:Microsoft.AspNetCore.Http.Endpoint> ) che ai dati della route. Questa modifica garantisce che la risorsa passata all'autorizzazione sia sempre `HttpContext` .

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 7

#### <a name="old-behavior"></a>Comportamento precedente

Quando si usa il routing degli endpoint e gli attributi del middleware di autorizzazione ( <xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware> ) o [[autorizza]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) , la risorsa passata all'autorizzazione è l'endpoint corrispondente.

#### <a name="new-behavior"></a>Nuovo comportamento

Il routing dell'endpoint passa l'oggetto `HttpContext` all'autorizzazione.

#### <a name="reason-for-change"></a>Motivo della modifica

È possibile ottenere l'endpoint dalla `HttpContext` . Tuttavia, non è stato possibile ottenere dall'endpoint elementi come i dati della route. Si è verificata una perdita di funzionalità dal routing non endpoint.

#### <a name="recommended-action"></a>Azione consigliata

Se l'app usa la risorsa endpoint, chiamare <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> su `HttpContext` per continuare ad accedere all'endpoint.

In ASP.NET Core 5,0 Preview 8 e versioni successive è possibile ripristinare il comportamento precedente con <xref:System.AppContext.SetSwitch%2A> . Ad esempio:

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!--

#### Affected APIs

Not detectable via API analysis

-->
