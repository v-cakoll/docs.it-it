---
ms.openlocfilehash: 89af89d3580fd1396335a0cd8964b46c13d7637e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344314"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a><span data-ttu-id="5e645-101">Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext. filters</span><span class="sxs-lookup"><span data-stu-id="5e645-101">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>

<span data-ttu-id="5e645-102">A partire da ASP.NET Core 3,0, MVC non aggiunge [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) per gli attributi [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) individuati nei controller e nei metodi di azione.</span><span class="sxs-lookup"><span data-stu-id="5e645-102">As of ASP.NET Core 3.0, MVC doesn't add [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) for [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributes that were discovered on controllers and action methods.</span></span> <span data-ttu-id="5e645-103">Questa modifica viene risolta localmente per i derivati di <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, ma si tratta di una modifica sostanziale per le implementazioni di <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> e <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter>.</span><span class="sxs-lookup"><span data-stu-id="5e645-103">This change is addressed locally for derivatives of <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, but it's a breaking change for <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> and <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementations.</span></span> <span data-ttu-id="5e645-104">Queste implementazioni incapsulate in un attributo [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) sono un modo [comune](https://stackoverflow.com/a/41348219/608220) e supportato per ottenere l'autorizzazione basata su attributi fortemente tipizzata quando sono necessarie sia la configurazione che l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="5e645-104">Such implementations wrapped in a [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) attribute are a [popular](https://stackoverflow.com/a/41348219/608220) and supported way to achieve strongly-typed, attribute-based authorization when both configuration and dependency injection are required.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5e645-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="5e645-105">Version introduced</span></span>

<span data-ttu-id="5e645-106">3.0</span><span class="sxs-lookup"><span data-stu-id="5e645-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5e645-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="5e645-107">Old behavior</span></span>

<span data-ttu-id="5e645-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> visualizzato nella raccolta [AuthorizationFilterContext. filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) .</span><span class="sxs-lookup"><span data-stu-id="5e645-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> appeared in the [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) collection.</span></span> <span data-ttu-id="5e645-109">Il test della presenza dell'interfaccia era un approccio valido per eseguire l'override o disabilitare il filtro nei singoli metodi del controller.</span><span class="sxs-lookup"><span data-stu-id="5e645-109">Testing for the interface's presence was a valid approach to override or disable the filter on individual controller methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5e645-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="5e645-110">New behavior</span></span>

<span data-ttu-id="5e645-111">`IAllowAnonymous` non viene più visualizzato nella raccolta di `AuthorizationFilterContext.Filters`.</span><span class="sxs-lookup"><span data-stu-id="5e645-111">`IAllowAnonymous` no longer appears in the `AuthorizationFilterContext.Filters` collection.</span></span> <span data-ttu-id="5e645-112">`IAsyncAuthorizationFilter` implementazioni che dipendono dal comportamento precedente in genere provocano risposte intermittenti HTTP 401 non autorizzate o HTTP 403.</span><span class="sxs-lookup"><span data-stu-id="5e645-112">`IAsyncAuthorizationFilter` implementations that are dependent on the old behavior typically cause intermittent HTTP 401 Unauthorized or HTTP 403 Forbidden responses.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5e645-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="5e645-113">Reason for change</span></span>

<span data-ttu-id="5e645-114">Una nuova strategia di routing degli endpoint è stata introdotta in ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="5e645-114">A new endpoint routing strategy was introduced in ASP.NET Core 3.0.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5e645-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="5e645-115">Recommended action</span></span>

<span data-ttu-id="5e645-116">Cercare `IAllowAnonymous`nei metadati dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5e645-116">Search the endpoint metadata for `IAllowAnonymous`.</span></span> <span data-ttu-id="5e645-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e645-117">For example:</span></span>

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

<span data-ttu-id="5e645-118">Un esempio di questa tecnica è illustrato in [questo metodo HasAllowAnonymous](https://github.com/aspnet/AspNetCore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span><span class="sxs-lookup"><span data-stu-id="5e645-118">An example of this technique is seen in [this HasAllowAnonymous method](https://github.com/aspnet/AspNetCore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span></span>

#### <a name="category"></a><span data-ttu-id="5e645-119">Categoria</span><span class="sxs-lookup"><span data-stu-id="5e645-119">Category</span></span>

<span data-ttu-id="5e645-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5e645-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5e645-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="5e645-121">Affected APIs</span></span>

<span data-ttu-id="5e645-122">nessuna</span><span class="sxs-lookup"><span data-stu-id="5e645-122">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
