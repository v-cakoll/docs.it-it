---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901827"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a><span data-ttu-id="73690-101">MVC: suffisso asincrono rimosso dai nomi delle azioni del controller</span><span class="sxs-lookup"><span data-stu-id="73690-101">MVC: Async suffix trimmed from controller action names</span></span>

<span data-ttu-id="73690-102">Come parte dell'indirizzamento di [DotNet/aspnetcore # 4849](https://github.com/dotnet/aspnetcore/issues/4849), ASP.NET Core MVC taglia il suffisso `Async` dai nomi delle azioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="73690-102">As part of addressing [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849), ASP.NET Core MVC trims the suffix `Async` from action names by default.</span></span> <span data-ttu-id="73690-103">A partire da ASP.NET Core 3,0, questa modifica interessa sia il routing che la generazione del collegamento.</span><span class="sxs-lookup"><span data-stu-id="73690-103">Starting with ASP.NET Core 3.0, this change affects both routing and link generation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="73690-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="73690-104">Version introduced</span></span>

<span data-ttu-id="73690-105">3.0</span><span class="sxs-lookup"><span data-stu-id="73690-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="73690-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="73690-106">Old behavior</span></span>

<span data-ttu-id="73690-107">Si consideri il seguente ASP.NET Core controller MVC:</span><span class="sxs-lookup"><span data-stu-id="73690-107">Consider the following ASP.NET Core MVC controller:</span></span>

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

<span data-ttu-id="73690-108">L'azione è instradabile tramite `Product/ListAsync`.</span><span class="sxs-lookup"><span data-stu-id="73690-108">The action is routable via `Product/ListAsync`.</span></span> <span data-ttu-id="73690-109">Per la generazione di collegamenti è necessario specificare il suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="73690-109">Link generation requires specifying the `Async` suffix.</span></span> <span data-ttu-id="73690-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="73690-110">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a><span data-ttu-id="73690-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="73690-111">New behavior</span></span>

<span data-ttu-id="73690-112">In ASP.NET Core 3,0, l'azione è instradabile tramite `Product/List`.</span><span class="sxs-lookup"><span data-stu-id="73690-112">In ASP.NET Core 3.0, the action is routable via `Product/List`.</span></span> <span data-ttu-id="73690-113">Il codice di generazione del collegamento deve omettere il suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="73690-113">Link generation code should omit the `Async` suffix.</span></span> <span data-ttu-id="73690-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="73690-114">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

<span data-ttu-id="73690-115">Questa modifica non influisce sui nomi specificati utilizzando l'attributo `[ActionName]`.</span><span class="sxs-lookup"><span data-stu-id="73690-115">This change doesn't affect names specified using the `[ActionName]` attribute.</span></span> <span data-ttu-id="73690-116">Il nuovo comportamento può essere disabilitato impostando `MvcOptions.SuppressAsyncSuffixInActionNames` su `false` in `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="73690-116">The new behavior can be disabled by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a><span data-ttu-id="73690-117">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="73690-117">Reason for change</span></span>

<span data-ttu-id="73690-118">Per convenzione, i metodi .NET asincroni hanno come suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="73690-118">By convention, asynchronous .NET methods are suffixed with `Async`.</span></span> <span data-ttu-id="73690-119">Tuttavia, quando un metodo definisce un'azione MVC, è indesiderabile usare il suffisso `Async`.</span><span class="sxs-lookup"><span data-stu-id="73690-119">However, when a method defines an MVC action, it's undesirable to use the `Async` suffix.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="73690-120">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="73690-120">Recommended action</span></span>

<span data-ttu-id="73690-121">Se l'app dipende da azioni MVC che conservano il suffisso `Async` del nome, scegliere una delle seguenti attenuazioni:</span><span class="sxs-lookup"><span data-stu-id="73690-121">If your app depends on MVC actions preserving the name's `Async` suffix, choose one of the following mitigations:</span></span>

- <span data-ttu-id="73690-122">Utilizzare l'attributo `[ActionName]` per mantenere il nome originale.</span><span class="sxs-lookup"><span data-stu-id="73690-122">Use the `[ActionName]` attribute to preserve the original name.</span></span>
- <span data-ttu-id="73690-123">Disabilitare la ridenominazione completamente impostando `MvcOptions.SuppressAsyncSuffixInActionNames` su `false` in `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="73690-123">Disable the renaming entirely by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a><span data-ttu-id="73690-124">Categoria</span><span class="sxs-lookup"><span data-stu-id="73690-124">Category</span></span>

<span data-ttu-id="73690-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="73690-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="73690-126">API interessate</span><span class="sxs-lookup"><span data-stu-id="73690-126">Affected APIs</span></span>

<span data-ttu-id="73690-127">nessuna</span><span class="sxs-lookup"><span data-stu-id="73690-127">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
