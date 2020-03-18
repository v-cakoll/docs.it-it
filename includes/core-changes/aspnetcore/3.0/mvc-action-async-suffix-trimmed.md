---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901827"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a><span data-ttu-id="d9023-101">MVC: suffisso asincrono tagliato dai nomi delle azioni del controller</span><span class="sxs-lookup"><span data-stu-id="d9023-101">MVC: Async suffix trimmed from controller action names</span></span>

<span data-ttu-id="d9023-102">Come parte dell'indirizzamento di [dotnet/aspnetcore-4849](https://github.com/dotnet/aspnetcore/issues/4849) `Async` , ASP.NET Core MVC taglia il suffisso dai nomi delle azioni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9023-102">As part of addressing [dotnet/aspnetcore#4849](https://github.com/dotnet/aspnetcore/issues/4849), ASP.NET Core MVC trims the suffix `Async` from action names by default.</span></span> <span data-ttu-id="d9023-103">A partire da ASP.NET Core 3.0, questa modifica influisce sia sul routing che sulla generazione dei collegamenti.</span><span class="sxs-lookup"><span data-stu-id="d9023-103">Starting with ASP.NET Core 3.0, this change affects both routing and link generation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9023-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d9023-104">Version introduced</span></span>

<span data-ttu-id="d9023-105">3.0</span><span class="sxs-lookup"><span data-stu-id="d9023-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d9023-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="d9023-106">Old behavior</span></span>

<span data-ttu-id="d9023-107">Si consideri il seguente controller DI MVC ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="d9023-107">Consider the following ASP.NET Core MVC controller:</span></span>

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

<span data-ttu-id="d9023-108">L'azione è `Product/ListAsync`instradabile tramite .</span><span class="sxs-lookup"><span data-stu-id="d9023-108">The action is routable via `Product/ListAsync`.</span></span> <span data-ttu-id="d9023-109">La generazione dei `Async` collegamenti richiede la specifica del suffisso.</span><span class="sxs-lookup"><span data-stu-id="d9023-109">Link generation requires specifying the `Async` suffix.</span></span> <span data-ttu-id="d9023-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d9023-110">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a><span data-ttu-id="d9023-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="d9023-111">New behavior</span></span>

<span data-ttu-id="d9023-112">In ASP.NET Core 3.0, l'azione è instradabile tramite `Product/List`.</span><span class="sxs-lookup"><span data-stu-id="d9023-112">In ASP.NET Core 3.0, the action is routable via `Product/List`.</span></span> <span data-ttu-id="d9023-113">Il codice di generazione `Async` del collegamento deve omettere il suffisso.</span><span class="sxs-lookup"><span data-stu-id="d9023-113">Link generation code should omit the `Async` suffix.</span></span> <span data-ttu-id="d9023-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d9023-114">For example:</span></span>

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

<span data-ttu-id="d9023-115">Questa modifica non influisce sui `[ActionName]` nomi specificati utilizzando l'attributo .</span><span class="sxs-lookup"><span data-stu-id="d9023-115">This change doesn't affect names specified using the `[ActionName]` attribute.</span></span> <span data-ttu-id="d9023-116">Il nuovo comportamento può `MvcOptions.SuppressAsyncSuffixInActionNames` essere `false` `Startup.ConfigureServices`disabilitato impostando su in :</span><span class="sxs-lookup"><span data-stu-id="d9023-116">The new behavior can be disabled by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a><span data-ttu-id="d9023-117">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d9023-117">Reason for change</span></span>

<span data-ttu-id="d9023-118">Per convenzione, i metodi .NET asincroni sono suffissi con `Async`.</span><span class="sxs-lookup"><span data-stu-id="d9023-118">By convention, asynchronous .NET methods are suffixed with `Async`.</span></span> <span data-ttu-id="d9023-119">Tuttavia, quando un metodo definisce un'azione MVC, `Async` è indesiderabile utilizzare il suffisso.</span><span class="sxs-lookup"><span data-stu-id="d9023-119">However, when a method defines an MVC action, it's undesirable to use the `Async` suffix.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9023-120">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d9023-120">Recommended action</span></span>

<span data-ttu-id="d9023-121">Se l'app dipende da azioni MVC `Async` che conservano il suffisso del nome, scegli una delle seguenti attenuazioni:</span><span class="sxs-lookup"><span data-stu-id="d9023-121">If your app depends on MVC actions preserving the name's `Async` suffix, choose one of the following mitigations:</span></span>

- <span data-ttu-id="d9023-122">Utilizzare `[ActionName]` l'attributo per mantenere il nome originale.</span><span class="sxs-lookup"><span data-stu-id="d9023-122">Use the `[ActionName]` attribute to preserve the original name.</span></span>
- <span data-ttu-id="d9023-123">Disattivare completamente la `MvcOptions.SuppressAsyncSuffixInActionNames` ridenominazione impostando su `false` in `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="d9023-123">Disable the renaming entirely by setting `MvcOptions.SuppressAsyncSuffixInActionNames` to `false` in `Startup.ConfigureServices`:</span></span>

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a><span data-ttu-id="d9023-124">Category</span><span class="sxs-lookup"><span data-stu-id="d9023-124">Category</span></span>

<span data-ttu-id="d9023-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d9023-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9023-126">API interessate</span><span class="sxs-lookup"><span data-stu-id="d9023-126">Affected APIs</span></span>

<span data-ttu-id="d9023-127">nessuno</span><span class="sxs-lookup"><span data-stu-id="d9023-127">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
