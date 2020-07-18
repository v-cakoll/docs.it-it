---
ms.openlocfilehash: 17a167e5245914329195d61ab45ae2d8ecb617d6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416267"
---
### <a name="blazor-target-framework-of-nuget-packages-changed"></a><span data-ttu-id="fc06b-101">Blazer: Framework di destinazione dei pacchetti NuGet modificato</span><span class="sxs-lookup"><span data-stu-id="fc06b-101">Blazor: Target framework of NuGet packages changed</span></span>

<span data-ttu-id="fc06b-102">I progetti webassembly di blazer 3,2 sono stati compilati per la destinazione .NET Standard 2,1 ( `<TargetFramework>netstandard2.1</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="fc06b-102">Blazor 3.2 WebAssembly projects were compiled to target .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span></span> <span data-ttu-id="fc06b-103">In ASP.NET Core 5,0, entrambi i progetti Blazer server e blazer webassembly sono destinati a .NET 5,0 ( `<TargetFramework>net5.0</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="fc06b-103">In ASP.NET Core 5.0, both Blazor Server and Blazor WebAssembly projects target .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span></span> <span data-ttu-id="fc06b-104">Per una migliore allineamento con la modifica del Framework di destinazione, i pacchetti di Blazer seguenti non sono più destinati .NET Standard 2,1:</span><span class="sxs-lookup"><span data-stu-id="fc06b-104">To better align with the target framework change, the following Blazor packages no longer target .NET Standard 2.1:</span></span>

* [<span data-ttu-id="fc06b-105">Microsoft. AspNetCore. Components</span><span class="sxs-lookup"><span data-stu-id="fc06b-105">Microsoft.AspNetCore.Components</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [<span data-ttu-id="fc06b-106">Microsoft. AspNetCore. Components. Authorization</span><span class="sxs-lookup"><span data-stu-id="fc06b-106">Microsoft.AspNetCore.Components.Authorization</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [<span data-ttu-id="fc06b-107">Microsoft. AspNetCore. Components. Forms</span><span class="sxs-lookup"><span data-stu-id="fc06b-107">Microsoft.AspNetCore.Components.Forms</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [<span data-ttu-id="fc06b-108">Microsoft. AspNetCore. Components. Web</span><span class="sxs-lookup"><span data-stu-id="fc06b-108">Microsoft.AspNetCore.Components.Web</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [<span data-ttu-id="fc06b-109">Microsoft. AspNetCore. Components. webassembly</span><span class="sxs-lookup"><span data-stu-id="fc06b-109">Microsoft.AspNetCore.Components.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [<span data-ttu-id="fc06b-110">Microsoft. AspNetCore. Components. webassembly. Authentication</span><span class="sxs-lookup"><span data-stu-id="fc06b-110">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [<span data-ttu-id="fc06b-111">InteroperabilitàMicrosoft.JS</span><span class="sxs-lookup"><span data-stu-id="fc06b-111">Microsoft.JSInterop</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop)
* [<span data-ttu-id="fc06b-112">Microsoft.JSInterop. webassembly</span><span class="sxs-lookup"><span data-stu-id="fc06b-112">Microsoft.JSInterop.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [<span data-ttu-id="fc06b-113">Microsoft. Authentication. webassembly. MSAL</span><span class="sxs-lookup"><span data-stu-id="fc06b-113">Microsoft.Authentication.WebAssembly.Msal</span></span>](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

<span data-ttu-id="fc06b-114">Per informazioni, vedere il problema GitHub [DotNet/aspnetcore # 23424](https://github.com/dotnet/aspnetcore/issues/23424).</span><span class="sxs-lookup"><span data-stu-id="fc06b-114">For discussion, see GitHub issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fc06b-115">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="fc06b-115">Version introduced</span></span>

<span data-ttu-id="fc06b-116">5,0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="fc06b-116">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="fc06b-117">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="fc06b-117">Old behavior</span></span>

<span data-ttu-id="fc06b-118">In blazer 3,1 e 3,2 i pacchetti hanno come destinazione .NET Standard 2,1 e .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="fc06b-118">In Blazor 3.1 and 3.2, packages target .NET Standard 2.1 and .NET Core 3.1.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="fc06b-119">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="fc06b-119">New behavior</span></span>

<span data-ttu-id="fc06b-120">In ASP.NET Core 5,0 i pacchetti sono destinati a .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="fc06b-120">In ASP.NET Core 5.0, packages target .NET 5.0.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="fc06b-121">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="fc06b-121">Reason for change</span></span>

<span data-ttu-id="fc06b-122">La modifica è stata apportata per una migliore allineamento con i requisiti di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fc06b-122">The change was made to better align with .NET target framework requirements.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fc06b-123">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="fc06b-123">Recommended action</span></span>

<span data-ttu-id="fc06b-124">I progetti webassembly blazer 3,2 devono essere destinati a .NET 5,0 come parte dell'aggiornamento dei riferimenti ai pacchetti a 5. x.x.</span><span class="sxs-lookup"><span data-stu-id="fc06b-124">Blazor 3.2 WebAssembly projects should target .NET 5.0 as part of updating their package references to 5.x.x.</span></span> <span data-ttu-id="fc06b-125">Le librerie che fanno riferimento a uno di questi pacchetti possono essere destinate a .NET 5,0 o a più destinazioni a seconda dei rispettivi requisiti.</span><span class="sxs-lookup"><span data-stu-id="fc06b-125">Libraries that reference one of these packages can either target .NET 5.0 or multi-target depending on their requirements.</span></span>

#### <a name="category"></a><span data-ttu-id="fc06b-126">Categoria</span><span class="sxs-lookup"><span data-stu-id="fc06b-126">Category</span></span>

<span data-ttu-id="fc06b-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fc06b-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fc06b-128">API interessate</span><span class="sxs-lookup"><span data-stu-id="fc06b-128">Affected APIs</span></span>

<span data-ttu-id="fc06b-129">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fc06b-129">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
