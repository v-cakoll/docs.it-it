---
ms.openlocfilehash: 09fd95ba5f3aee59f2abdfbb4e64eb6202e2b873
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394426"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a><span data-ttu-id="a5353-101">MVC: i tipi "Pubternal" sono stati modificati in Internal</span><span class="sxs-lookup"><span data-stu-id="a5353-101">MVC: "Pubternal" types changed to internal</span></span>

<span data-ttu-id="a5353-102">In ASP.NET Core 3,0 tutti i tipi "pubternal" in MVC sono stati aggiornati per essere `public` in uno spazio dei nomi supportato o `internal`, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a5353-102">In ASP.NET Core 3.0, all "pubternal" types in MVC were updated to either be `public` in a supported namespace or `internal` as appropriate.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a5353-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="a5353-103">Change description</span></span>

<span data-ttu-id="a5353-104">In ASP.NET Core i tipi "pubternal" sono dichiarati come `public`, ma risiedono in uno spazio dei nomi con suffisso @no__t 1.</span><span class="sxs-lookup"><span data-stu-id="a5353-104">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a `.Internal`-suffixed namespace.</span></span> <span data-ttu-id="a5353-105">Anche se questi tipi sono `public`, non hanno criteri di supporto e sono soggetti a modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="a5353-105">While these types are `public`, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="a5353-106">Sfortunatamente, l'uso accidentale di questi tipi è stato comune, con conseguente riduzione delle modifiche apportate a questi progetti e della possibilità di mantenere il Framework.</span><span class="sxs-lookup"><span data-stu-id="a5353-106">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a5353-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a5353-107">Version introduced</span></span>

<span data-ttu-id="a5353-108">3.0</span><span class="sxs-lookup"><span data-stu-id="a5353-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a5353-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="a5353-109">Old behavior</span></span>

<span data-ttu-id="a5353-110">Alcuni tipi in MVC sono `public`, ma in uno spazio dei nomi `.Internal`.</span><span class="sxs-lookup"><span data-stu-id="a5353-110">Some types in MVC were `public` but in a `.Internal` namespace.</span></span> <span data-ttu-id="a5353-111">Questi tipi non hanno criteri di supporto e sono soggetti a modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="a5353-111">These types had no support policy and were subject to breaking changes.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a5353-112">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="a5353-112">New behavior</span></span>

<span data-ttu-id="a5353-113">Tutti questi tipi vengono aggiornati per essere `public` in uno spazio dei nomi supportato o contrassegnati come `internal`.</span><span class="sxs-lookup"><span data-stu-id="a5353-113">All such types are updated either to be `public` in a supported namespace or marked as `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a5353-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="a5353-114">Reason for change</span></span>

<span data-ttu-id="a5353-115">L'uso accidentale dei tipi "pubternal" è stato comune, con conseguente riduzione delle modifiche apportate a questi progetti e della possibilità di mantenere il Framework.</span><span class="sxs-lookup"><span data-stu-id="a5353-115">Accidental use of the "pubternal" types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a5353-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a5353-116">Recommended action</span></span>

<span data-ttu-id="a5353-117">Se si usano i tipi che sono diventati realmente `public` e sono stati spostati in un nuovo spazio dei nomi supportato, aggiornare i riferimenti in modo che corrispondano ai nuovi spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a5353-117">If you're using types that have become truly `public` and have been moved into a new, supported namespace, update your references to match the new namespaces.</span></span>

<span data-ttu-id="a5353-118">Se si usano i tipi che sono stati contrassegnati come `internal`, sarà necessario trovare un'alternativa.</span><span class="sxs-lookup"><span data-stu-id="a5353-118">If you're using types that have become marked as `internal`, you'll need to find an alternative.</span></span> <span data-ttu-id="a5353-119">I tipi "pubternal" precedenti non erano mai supportati per l'uso pubblico.</span><span class="sxs-lookup"><span data-stu-id="a5353-119">The previously "pubternal" types were never supported for public use.</span></span> <span data-ttu-id="a5353-120">Se in questi spazi dei nomi sono presenti tipi specifici che sono fondamentali per le app, archiviare un problema in [ASPNET/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span><span class="sxs-lookup"><span data-stu-id="a5353-120">If there are specific types in these namespaces that are critical to your apps, file an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span> <span data-ttu-id="a5353-121">È possibile che vengano apportate alcune considerazioni per rendere i tipi richiesti `public`.</span><span class="sxs-lookup"><span data-stu-id="a5353-121">Considerations may be made for making the requested types `public`.</span></span>

#### <a name="category"></a><span data-ttu-id="a5353-122">Category</span><span class="sxs-lookup"><span data-stu-id="a5353-122">Category</span></span>

<span data-ttu-id="a5353-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a5353-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a5353-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="a5353-124">Affected APIs</span></span>

<span data-ttu-id="a5353-125">Questa modifica include i tipi negli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5353-125">This change includes types in the following namespaces:</span></span>

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
