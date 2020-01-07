---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344296"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="02c3a-101">Razor: la compilazione di runtime è stata spostata in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="02c3a-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="02c3a-102">Il supporto per la compilazione in fase di esecuzione delle visualizzazioni Razor e Razor Pages è stato spostato in un pacchetto separato.</span><span class="sxs-lookup"><span data-stu-id="02c3a-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="02c3a-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="02c3a-103">Version introduced</span></span>

<span data-ttu-id="02c3a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="02c3a-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="02c3a-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="02c3a-105">Old behavior</span></span>

<span data-ttu-id="02c3a-106">La compilazione del runtime è disponibile senza che siano necessari pacchetti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="02c3a-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="02c3a-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="02c3a-107">New behavior</span></span>

<span data-ttu-id="02c3a-108">La funzionalità è stata spostata nel pacchetto [Microsoft. AspNetCore. Mvc. Razor. RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) .</span><span class="sxs-lookup"><span data-stu-id="02c3a-108">The functionality has been moved to the [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) package.</span></span>

<span data-ttu-id="02c3a-109">Le API seguenti erano in precedenza disponibili in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` per supportare la compilazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="02c3a-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="02c3a-110">Le API sono ora disponibili tramite `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span><span class="sxs-lookup"><span data-stu-id="02c3a-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- <span data-ttu-id="02c3a-111">`RazorViewEngineOptions.FileProviders` è ora `MvcRazorRuntimeCompilationOptions.FileProviders`</span><span class="sxs-lookup"><span data-stu-id="02c3a-111">`RazorViewEngineOptions.FileProviders` is now `MvcRazorRuntimeCompilationOptions.FileProviders`</span></span>
- <span data-ttu-id="02c3a-112">`RazorViewEngineOptions.AdditionalCompilationReferences` è ora `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span><span class="sxs-lookup"><span data-stu-id="02c3a-112">`RazorViewEngineOptions.AdditionalCompilationReferences` is now `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span></span>

<span data-ttu-id="02c3a-113">Inoltre, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="02c3a-113">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="02c3a-114">Per impostazione predefinita, la ricompilazione delle modifiche ai file è abilitata facendo riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="02c3a-114">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="02c3a-115">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="02c3a-115">Reason for change</span></span>

<span data-ttu-id="02c3a-116">Questa modifica era necessaria per rimuovere la dipendenza del Framework condiviso ASP.NET Core su Roslyn.</span><span class="sxs-lookup"><span data-stu-id="02c3a-116">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="02c3a-117">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="02c3a-117">Recommended action</span></span>

<span data-ttu-id="02c3a-118">Per le app che richiedono la compilazione o la ricompilazione di runtime dei file Razor, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="02c3a-118">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="02c3a-119">Aggiungere un riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="02c3a-119">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="02c3a-120">Aggiornare il metodo `Startup.ConfigureServices` del progetto in modo da includere una chiamata a `AddRazorRuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="02c3a-120">Update the project's `Startup.ConfigureServices` method to include a call to `AddRazorRuntimeCompilation`.</span></span> <span data-ttu-id="02c3a-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="02c3a-121">For example:</span></span>

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="02c3a-122">Categoria</span><span class="sxs-lookup"><span data-stu-id="02c3a-122">Category</span></span>

<span data-ttu-id="02c3a-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02c3a-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="02c3a-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="02c3a-124">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
