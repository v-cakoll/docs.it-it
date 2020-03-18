---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344296"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="29bf9-101">Razor: la compilazione di runtime spostata in un pacchettoRazor: Runtime compilation moved to a package</span><span class="sxs-lookup"><span data-stu-id="29bf9-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="29bf9-102">Il supporto per la compilazione in fase di esecuzione delle visualizzazioni Razor e delle pagine Razor è stato spostato in un pacchetto separato.</span><span class="sxs-lookup"><span data-stu-id="29bf9-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="29bf9-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="29bf9-103">Version introduced</span></span>

<span data-ttu-id="29bf9-104">3.0</span><span class="sxs-lookup"><span data-stu-id="29bf9-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="29bf9-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="29bf9-105">Old behavior</span></span>

<span data-ttu-id="29bf9-106">La compilazione di runtime è disponibile senza la necessità di pacchetti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="29bf9-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="29bf9-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="29bf9-107">New behavior</span></span>

<span data-ttu-id="29bf9-108">La funzionalità è stata spostata nel pacchetto [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/)</span><span class="sxs-lookup"><span data-stu-id="29bf9-108">The functionality has been moved to the [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) package.</span></span>

<span data-ttu-id="29bf9-109">Le API seguenti erano precedentemente disponibili per `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` supportare la compilazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="29bf9-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="29bf9-110">Le API sono ora `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`disponibili tramite .</span><span class="sxs-lookup"><span data-stu-id="29bf9-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- <span data-ttu-id="29bf9-111">`RazorViewEngineOptions.FileProviders` è ora `MvcRazorRuntimeCompilationOptions.FileProviders`</span><span class="sxs-lookup"><span data-stu-id="29bf9-111">`RazorViewEngineOptions.FileProviders` is now `MvcRazorRuntimeCompilationOptions.FileProviders`</span></span>
- <span data-ttu-id="29bf9-112">`RazorViewEngineOptions.AdditionalCompilationReferences` è ora `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span><span class="sxs-lookup"><span data-stu-id="29bf9-112">`RazorViewEngineOptions.AdditionalCompilationReferences` is now `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span></span>

<span data-ttu-id="29bf9-113">Inoltre, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="29bf9-113">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="29bf9-114">La ricompilazione delle modifiche ai file `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` è abilitata per impostazione predefinita facendo riferimento al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="29bf9-114">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="29bf9-115">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="29bf9-115">Reason for change</span></span>

<span data-ttu-id="29bf9-116">Questa modifica era necessaria per rimuovere la dipendenza del framework condiviso ASP.NET Core su Roslyn.This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span><span class="sxs-lookup"><span data-stu-id="29bf9-116">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="29bf9-117">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="29bf9-117">Recommended action</span></span>

<span data-ttu-id="29bf9-118">Le app che richiedono la compilazione o la ricompilazione di runtime dei file Razor devono eseguire le operazioni seguenti:Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span><span class="sxs-lookup"><span data-stu-id="29bf9-118">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="29bf9-119">Aggiungere un riferimento `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="29bf9-119">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="29bf9-120">Aggiornare il `Startup.ConfigureServices` metodo del progetto `AddRazorRuntimeCompilation`per includere una chiamata a .</span><span class="sxs-lookup"><span data-stu-id="29bf9-120">Update the project's `Startup.ConfigureServices` method to include a call to `AddRazorRuntimeCompilation`.</span></span> <span data-ttu-id="29bf9-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="29bf9-121">For example:</span></span>

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="29bf9-122">Category</span><span class="sxs-lookup"><span data-stu-id="29bf9-122">Category</span></span>

<span data-ttu-id="29bf9-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="29bf9-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="29bf9-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="29bf9-124">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
