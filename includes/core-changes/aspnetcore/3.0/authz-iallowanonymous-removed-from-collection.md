---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901610"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a><span data-ttu-id="49cb2-101">Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext.Filters</span><span class="sxs-lookup"><span data-stu-id="49cb2-101">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>

<span data-ttu-id="49cb2-102">A partire da ASP.NET Core 3.0, MVC non aggiunge [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) per [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributi individuati nei controller e metodi di azione.</span><span class="sxs-lookup"><span data-stu-id="49cb2-102">As of ASP.NET Core 3.0, MVC doesn't add [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) for [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributes that were discovered on controllers and action methods.</span></span> <span data-ttu-id="49cb2-103">Questa modifica viene affrontata localmente per i derivati di <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, ma si tratta di una modifica sostanziale per <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> e <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementazioni.</span><span class="sxs-lookup"><span data-stu-id="49cb2-103">This change is addressed locally for derivatives of <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, but it's a breaking change for <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> and <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementations.</span></span> <span data-ttu-id="49cb2-104">Tali implementazioni di cui è stato eseguito il wrapping in un attributo [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) sono un modo [comune](https://stackoverflow.com/a/41348219/608220) e supportato per ottenere un'autorizzazione fortemente tipizzata basata su attributi quando sono necessarie sia la configurazione che l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="49cb2-104">Such implementations wrapped in a [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) attribute are a [popular](https://stackoverflow.com/a/41348219/608220) and supported way to achieve strongly-typed, attribute-based authorization when both configuration and dependency injection are required.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="49cb2-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49cb2-105">Version introduced</span></span>

<span data-ttu-id="49cb2-106">3.0</span><span class="sxs-lookup"><span data-stu-id="49cb2-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="49cb2-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="49cb2-107">Old behavior</span></span>

<span data-ttu-id="49cb2-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous>nell'insieme [AuthorizationFilterContext.Filters.](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A)</span><span class="sxs-lookup"><span data-stu-id="49cb2-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> appeared in the [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) collection.</span></span> <span data-ttu-id="49cb2-109">Il test della presenza dell'interfaccia era un approccio valido per eseguire l'override o disabilitare il filtro nei singoli metodi del controller.</span><span class="sxs-lookup"><span data-stu-id="49cb2-109">Testing for the interface's presence was a valid approach to override or disable the filter on individual controller methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="49cb2-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="49cb2-110">New behavior</span></span>

<span data-ttu-id="49cb2-111">`IAllowAnonymous`non viene più `AuthorizationFilterContext.Filters` visualizzato nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="49cb2-111">`IAllowAnonymous` no longer appears in the `AuthorizationFilterContext.Filters` collection.</span></span> <span data-ttu-id="49cb2-112">`IAsyncAuthorizationFilter`le implementazioni che dipendono dal comportamento precedente causano in genere risposte HTTP 401 non autorizzate o HTTP 403 non consentite intermittenti.</span><span class="sxs-lookup"><span data-stu-id="49cb2-112">`IAsyncAuthorizationFilter` implementations that are dependent on the old behavior typically cause intermittent HTTP 401 Unauthorized or HTTP 403 Forbidden responses.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="49cb2-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="49cb2-113">Reason for change</span></span>

<span data-ttu-id="49cb2-114">È stata introdotta una nuova strategia di routing degli endpoint in ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="49cb2-114">A new endpoint routing strategy was introduced in ASP.NET Core 3.0.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="49cb2-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="49cb2-115">Recommended action</span></span>

<span data-ttu-id="49cb2-116">Cercare i metadati dell'endpoint per `IAllowAnonymous`.</span><span class="sxs-lookup"><span data-stu-id="49cb2-116">Search the endpoint metadata for `IAllowAnonymous`.</span></span> <span data-ttu-id="49cb2-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="49cb2-117">For example:</span></span>

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

<span data-ttu-id="49cb2-118">Un esempio di questa tecnica è visto in [questo metodo HasAllowAnonymous](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span><span class="sxs-lookup"><span data-stu-id="49cb2-118">An example of this technique is seen in [this HasAllowAnonymous method](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span></span>

#### <a name="category"></a><span data-ttu-id="49cb2-119">Category</span><span class="sxs-lookup"><span data-stu-id="49cb2-119">Category</span></span>

<span data-ttu-id="49cb2-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="49cb2-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="49cb2-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="49cb2-121">Affected APIs</span></span>

<span data-ttu-id="49cb2-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="49cb2-122">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
