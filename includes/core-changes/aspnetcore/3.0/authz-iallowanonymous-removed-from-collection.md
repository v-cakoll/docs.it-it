---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901610"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a>Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext. filters

A partire da ASP.NET Core 3,0, MVC non aggiunge [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) per gli attributi [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) individuati nei controller e nei metodi di azione. Questa modifica viene risolta localmente per i derivati di <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, ma si tratta di una modifica sostanziale per le implementazioni di <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> e <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter>. Queste implementazioni incapsulate in un attributo [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) sono un modo [comune](https://stackoverflow.com/a/41348219/608220) e supportato per ottenere l'autorizzazione basata su attributi fortemente tipizzata quando sono necessarie sia la configurazione che l'inserimento delle dipendenze.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

<xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> visualizzato nella raccolta [AuthorizationFilterContext. filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) . Il test della presenza dell'interfaccia era un approccio valido per eseguire l'override o disabilitare il filtro nei singoli metodi del controller.

#### <a name="new-behavior"></a>Nuovo comportamento

`IAllowAnonymous` non viene più visualizzato nella raccolta di `AuthorizationFilterContext.Filters`. `IAsyncAuthorizationFilter` implementazioni che dipendono dal comportamento precedente in genere provocano risposte intermittenti HTTP 401 non autorizzate o HTTP 403.

#### <a name="reason-for-change"></a>Motivo della modifica

Una nuova strategia di routing degli endpoint è stata introdotta in ASP.NET Core 3,0.

#### <a name="recommended-action"></a>Azione consigliata

Cercare `IAllowAnonymous`nei metadati dell'endpoint. Ad esempio:

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

Un esempio di questa tecnica è illustrato in [questo metodo HasAllowAnonymous](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuna

<!--

#### Affected APIs

Not detectable via API analysis

-->
