---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393897"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="135ae-101">Razor: la compilazione di runtime è stata spostata in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="135ae-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="135ae-102">Il supporto per la compilazione in fase di esecuzione delle visualizzazioni Razor e Razor Pages è stato spostato in un pacchetto separato.</span><span class="sxs-lookup"><span data-stu-id="135ae-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="135ae-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="135ae-103">Version introduced</span></span>

<span data-ttu-id="135ae-104">3.0</span><span class="sxs-lookup"><span data-stu-id="135ae-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="135ae-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="135ae-105">Old behavior</span></span>

<span data-ttu-id="135ae-106">La compilazione del runtime è disponibile senza che siano necessari pacchetti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="135ae-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="135ae-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="135ae-107">New behavior</span></span>

<span data-ttu-id="135ae-108">La funzionalità è stata spostata nel pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="135ae-108">The functionality has been moved to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

<span data-ttu-id="135ae-109">Le API seguenti erano in precedenza disponibili in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` per supportare la compilazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="135ae-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="135ae-110">Le API sono ora disponibili tramite `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span><span class="sxs-lookup"><span data-stu-id="135ae-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

<span data-ttu-id="135ae-111">Inoltre, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="135ae-111">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="135ae-112">Per impostazione predefinita, la ricompilazione delle modifiche ai file è abilitata facendo riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="135ae-112">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="135ae-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="135ae-113">Reason for change</span></span>

<span data-ttu-id="135ae-114">Questa modifica era necessaria per rimuovere la dipendenza del Framework condiviso ASP.NET Core su Roslyn.</span><span class="sxs-lookup"><span data-stu-id="135ae-114">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="135ae-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="135ae-115">Recommended action</span></span>

<span data-ttu-id="135ae-116">Per le app che richiedono la compilazione o la ricompilazione di runtime dei file Razor, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="135ae-116">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="135ae-117">Aggiungere un riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="135ae-117">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="135ae-118">Aggiornare il metodo `Startup.ConfigureServices` del progetto in modo da includere una chiamata a `AddMvcRazorRuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="135ae-118">Update the project's `Startup.ConfigureServices` method to include a call to `AddMvcRazorRuntimeCompilation`.</span></span> <span data-ttu-id="135ae-119">Ad esempio, in `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="135ae-119">For example, in `Startup.ConfigureServices`:</span></span>

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="135ae-120">Category</span><span class="sxs-lookup"><span data-stu-id="135ae-120">Category</span></span>

<span data-ttu-id="135ae-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="135ae-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="135ae-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="135ae-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
