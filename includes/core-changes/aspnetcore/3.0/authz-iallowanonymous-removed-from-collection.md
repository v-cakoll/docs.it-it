---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901610"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a>Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext.Filters

A partire da ASP.NET Core 3.0, MVC non aggiunge [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) per [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributi individuati nei controller e metodi di azione. Questa modifica viene affrontata localmente per i derivati di <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, ma si tratta di una modifica sostanziale per <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> e <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementazioni. Tali implementazioni di cui è stato eseguito il wrapping in un attributo [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) sono un modo [comune](https://stackoverflow.com/a/41348219/608220) e supportato per ottenere un'autorizzazione fortemente tipizzata basata su attributi quando sono necessarie sia la configurazione che l'inserimento delle dipendenze.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

<xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous>nell'insieme [AuthorizationFilterContext.Filters.](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) Il test della presenza dell'interfaccia era un approccio valido per eseguire l'override o disabilitare il filtro nei singoli metodi del controller.

#### <a name="new-behavior"></a>Nuovo comportamento

`IAllowAnonymous`non viene più `AuthorizationFilterContext.Filters` visualizzato nella raccolta. `IAsyncAuthorizationFilter`le implementazioni che dipendono dal comportamento precedente causano in genere risposte HTTP 401 non autorizzate o HTTP 403 non consentite intermittenti.

#### <a name="reason-for-change"></a>Motivo della modifica

È stata introdotta una nuova strategia di routing degli endpoint in ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Azione consigliata

Cercare i metadati dell'endpoint per `IAllowAnonymous`. Ad esempio:

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

Un esempio di questa tecnica è visto in [questo metodo HasAllowAnonymous](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!--

#### Affected APIs

Not detectable via API analysis

-->
