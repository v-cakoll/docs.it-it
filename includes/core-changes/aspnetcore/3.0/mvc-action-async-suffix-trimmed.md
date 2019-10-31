---
ms.openlocfilehash: 503d61cb86c83e2f32ad40c60a127ae255ef71b0
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198466"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a><span data-ttu-id="b683c-101">MVC: suffisso asincrono rimosso dai nomi delle azioni del controller</span><span class="sxs-lookup"><span data-stu-id="b683c-101">MVC: Async suffix trimmed from controller action names</span></span>

<span data-ttu-id="b683c-102">Nell'ambito dell'indirizzamento di [ASPNET/AspNetCore # 4849](https://github.com/aspnet/AspNetCore/issues/4849), ASP.NET Core MVC taglia il suffisso `Async` dai nomi delle azioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b683c-102">As part of addressing [aspnet/AspNetCore#4849](https://github.com/aspnet/AspNetCore/issues/4849), ASP.NET Core MVC trims the suffix `Async` from action names by default.</span></span> <span data-ttu-id="b683c-103">A partire da ASP.NET Core 3,0, questa modifica interessa sia il routing che la generazione del collegamento.</span><span class="sxs-lookup"><span data-stu-id="b683c-103">Starting with ASP.NET Core 3.0, this change affects both routing and link generation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b683c-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b683c-104">Version introduced</span></span>

<span data-ttu-id="b683c-105">3.0</span><span class="sxs-lookup"><span data-stu-id="b683c-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b683c-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="b683c-106">Old behavior</span></span>

<span data-ttu-id="b683c-107">Si consideri il seguente ASP.NET Core controller MVC:</span><span class="sxs-lookup"><span data-stu-id="b683c-107">Consider the following ASP.NET Core MVC controller:</span></span>

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

<span data-ttu-id="b683c-108">L'azione è instradabile tramite `Product/ListAsync`.</span><span class="sxs-lookup"><span data-stu-id="b683c-108">The action is routable via `Product/ListAsync`.</span></span> <span data-ttu-id="b683c-109">Per la generazione di collegamenti è necessario specificare il suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="b683c-109">Link generation requires specifying the `Async` suffix.</span></span> <span data-ttu-id="b683c-110">Esempio:</span><span class="sxs-lookup"><span data-stu-id="b683c-110">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a><span data-ttu-id="b683c-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="b683c-111">New behavior</span></span>

<span data-ttu-id="b683c-112">In ASP.NET Core 3,0, l'azione è instradabile tramite `Product/List`.</span><span class="sxs-lookup"><span data-stu-id="b683c-112">In ASP.NET Core 3.0, the action is routable via `Product/List`.</span></span> <span data-ttu-id="b683c-113">Il codice di generazione del collegamento deve omettere il suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="b683c-113">Link generation code should omit the `Async` suffix.</span></span> <span data-ttu-id="b683c-114">Esempio:</span><span class="sxs-lookup"><span data-stu-id="b683c-114">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

<span data-ttu-id="b683c-115">Questa modifica non influisce sui nomi specificati utilizzando l'attributo `[ActionName]`.</span><span class="sxs-lookup"><span data-stu-id="b683c-115">This change doesn't affect names specified using the `[ActionName]` attribute.</span></span> <span data-ttu-id="b683c-116">Il nuovo comportamento può essere disabilitato impostando `MvcOptions.SuppressAsyncSuffixInActionNames` su `false` in `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="b683c-116">The new behavior can be disabled by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a><span data-ttu-id="b683c-117">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="b683c-117">Reason for change</span></span>

<span data-ttu-id="b683c-118">Per convenzione, i metodi .NET asincroni sono con suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="b683c-118">By convention, asynchronous .NET methods are suffixed with `Async`.</span></span> <span data-ttu-id="b683c-119">Tuttavia, quando un metodo definisce un'azione MVC, è indesiderabile usare il suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="b683c-119">However, when a method defines an MVC action, it's undesirable to use the `Async` suffix.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b683c-120">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b683c-120">Recommended action</span></span>

<span data-ttu-id="b683c-121">Se l'app dipende da azioni MVC che conservano il suffisso `Async` del nome, scegliere una delle seguenti attenuazioni:</span><span class="sxs-lookup"><span data-stu-id="b683c-121">If your app depends on MVC actions preserving the name's `Async` suffix, choose one of the following mitigations:</span></span>

- <span data-ttu-id="b683c-122">Utilizzare l'attributo `[ActionName]` per mantenere il nome originale.</span><span class="sxs-lookup"><span data-stu-id="b683c-122">Use the `[ActionName]` attribute to preserve the original name.</span></span>
- <span data-ttu-id="b683c-123">Disabilitare la ridenominazione completamente impostando `MvcOptions.SuppressAsyncSuffixInActionNames` su `false` in `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="b683c-123">Disable the renaming entirely by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a><span data-ttu-id="b683c-124">Category</span><span class="sxs-lookup"><span data-stu-id="b683c-124">Category</span></span>

<span data-ttu-id="b683c-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b683c-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b683c-126">API interessate</span><span class="sxs-lookup"><span data-stu-id="b683c-126">Affected APIs</span></span>

<span data-ttu-id="b683c-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b683c-127">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
