---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441550"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="b8028-101">Autorizzazione: la risorsa nel routing dell'endpoint è HttpContext</span><span class="sxs-lookup"><span data-stu-id="b8028-101">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="b8028-102">Quando si usa il routing degli endpoint in ASP.NET Core 3,1, la risorsa usata per l'autorizzazione è l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b8028-102">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="b8028-103">Questo approccio non è sufficiente per ottenere l'accesso ai dati della route ( <xref:Microsoft.AspNetCore.Routing.RouteData> ).</span><span class="sxs-lookup"><span data-stu-id="b8028-103">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="b8028-104">In precedenza in MVC <xref:Microsoft.AspNetCore.Http.HttpContext> è stata passata una risorsa, che consente l'accesso sia all'endpoint ( <xref:Microsoft.AspNetCore.Http.Endpoint> ) che ai dati della route.</span><span class="sxs-lookup"><span data-stu-id="b8028-104">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="b8028-105">Questa modifica garantisce che la risorsa passata all'autorizzazione sia sempre `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="b8028-105">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b8028-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b8028-106">Version introduced</span></span>

<span data-ttu-id="b8028-107">5,0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="b8028-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b8028-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="b8028-108">Old behavior</span></span>

<span data-ttu-id="b8028-109">Quando si usa il routing degli endpoint e gli attributi del middleware di autorizzazione ( <xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware> ) o [[autorizza]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) , la risorsa passata all'autorizzazione è l'endpoint corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b8028-109">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b8028-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="b8028-110">New behavior</span></span>

<span data-ttu-id="b8028-111">Il routing dell'endpoint passa l'oggetto `HttpContext` all'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8028-111">Endpoint routing passes the `HttpContext` to authorization.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b8028-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="b8028-112">Reason for change</span></span>

<span data-ttu-id="b8028-113">È possibile ottenere l'endpoint dalla `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="b8028-113">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="b8028-114">Tuttavia, non è stato possibile ottenere dall'endpoint elementi come i dati della route.</span><span class="sxs-lookup"><span data-stu-id="b8028-114">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="b8028-115">Si è verificata una perdita di funzionalità dal routing non endpoint.</span><span class="sxs-lookup"><span data-stu-id="b8028-115">There was a loss in functionality from non-endpoint routing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b8028-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b8028-116">Recommended action</span></span>

<span data-ttu-id="b8028-117">Se l'app usa la risorsa endpoint, chiamare <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> su `HttpContext` per continuare ad accedere all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b8028-117">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="b8028-118">In ASP.NET Core 5,0 Preview 8 e versioni successive è possibile ripristinare il comportamento precedente con <xref:System.AppContext.SetSwitch%2A> .</span><span class="sxs-lookup"><span data-stu-id="b8028-118">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="b8028-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b8028-119">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a><span data-ttu-id="b8028-120">Categoria</span><span class="sxs-lookup"><span data-stu-id="b8028-120">Category</span></span>

<span data-ttu-id="b8028-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b8028-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b8028-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="b8028-122">Affected APIs</span></span>

<span data-ttu-id="b8028-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b8028-123">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
