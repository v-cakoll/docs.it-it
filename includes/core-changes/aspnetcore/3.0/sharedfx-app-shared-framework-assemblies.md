---
ms.openlocfilehash: d598d8d3203e804e5e935c3564b0053f9fc2e9a6
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84145008"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a><span data-ttu-id="a4541-101">Framework condiviso: assembly rimossi da Microsoft. AspNetCore. app</span><span class="sxs-lookup"><span data-stu-id="a4541-101">Shared framework: Assemblies removed from Microsoft.AspNetCore.App</span></span>

<span data-ttu-id="a4541-102">A partire da ASP.NET Core 3,0, il Framework condiviso ASP.NET Core ( `Microsoft.AspNetCore.App` ) contiene solo assembly di terze parti completamente sviluppati, supportati e utilizzabili da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a4541-102">Starting in ASP.NET Core 3.0, the ASP.NET Core shared framework (`Microsoft.AspNetCore.App`) only contains first-party assemblies that are fully developed, supported, and serviceable by Microsoft.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a4541-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="a4541-103">Change description</span></span>

<span data-ttu-id="a4541-104">Si pensi alla modifica come alla ridefinizione dei limiti per la ASP.NET Core "piattaforma".</span><span class="sxs-lookup"><span data-stu-id="a4541-104">Think of the change as the redefining of boundaries for the ASP.NET Core "platform."</span></span> <span data-ttu-id="a4541-105">Il Framework condiviso sarà [compilabile dall'origine da chiunque tramite GitHub](https://github.com/dotnet/source-build) e continuerà a offrire i vantaggi esistenti dei Framework condivisi di .NET Core alle app.</span><span class="sxs-lookup"><span data-stu-id="a4541-105">The shared framework will be [source-buildable by anybody via GitHub](https://github.com/dotnet/source-build) and will continue to offer the existing benefits of .NET Core shared frameworks to your apps.</span></span> <span data-ttu-id="a4541-106">Alcuni vantaggi includono dimensioni di distribuzione inferiori, patch centralizzate e tempi di avvio più rapidi.</span><span class="sxs-lookup"><span data-stu-id="a4541-106">Some benefits include smaller deployment size, centralized patching, and faster startup time.</span></span>

<span data-ttu-id="a4541-107">Come parte della modifica, alcune modifiche importanti sono state introdotte in `Microsoft.AspNetCore.App` .</span><span class="sxs-lookup"><span data-stu-id="a4541-107">As part of the change, some notable breaking changes are introduced in `Microsoft.AspNetCore.App`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a4541-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a4541-108">Version introduced</span></span>

<span data-ttu-id="a4541-109">3.0</span><span class="sxs-lookup"><span data-stu-id="a4541-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a4541-110">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="a4541-110">Old behavior</span></span>

<span data-ttu-id="a4541-111">Progetti a cui viene fatto riferimento `Microsoft.AspNetCore.App` tramite un `<PackageReference>` elemento nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a4541-111">Projects referenced `Microsoft.AspNetCore.App` via a `<PackageReference>` element in the project file.</span></span>

<span data-ttu-id="a4541-112">Inoltre, `Microsoft.AspNetCore.App` conteneva i componenti sottocomponenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4541-112">Additionally, `Microsoft.AspNetCore.App` contained the following subcomponents:</span></span>

- <span data-ttu-id="a4541-113">Json.NET ( `Newtonsoft.Json` )</span><span class="sxs-lookup"><span data-stu-id="a4541-113">Json.NET (`Newtonsoft.Json`)</span></span>
- <span data-ttu-id="a4541-114">Entity Framework Core (assembly con prefisso `Microsoft.EntityFrameworkCore.` )</span><span class="sxs-lookup"><span data-stu-id="a4541-114">Entity Framework Core (assemblies prefixed with `Microsoft.EntityFrameworkCore.`)</span></span>
- <span data-ttu-id="a4541-115">Roslyn ( `Microsoft.CodeAnalysis` )</span><span class="sxs-lookup"><span data-stu-id="a4541-115">Roslyn (`Microsoft.CodeAnalysis`)</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a4541-116">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="a4541-116">New behavior</span></span>

<span data-ttu-id="a4541-117">Un riferimento a `Microsoft.AspNetCore.App` non richiede più un `<PackageReference>` elemento nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a4541-117">A reference to `Microsoft.AspNetCore.App` no longer requires a `<PackageReference>` element in the project file.</span></span> <span data-ttu-id="a4541-118">Il .NET Core SDK supporta un nuovo elemento denominato `<FrameworkReference>` , che sostituisce l'uso di `<PackageReference>` .</span><span class="sxs-lookup"><span data-stu-id="a4541-118">The .NET Core SDK supports a new element called `<FrameworkReference>`, which replaces the use of `<PackageReference>`.</span></span>

<span data-ttu-id="a4541-119">Per ulteriori informazioni, vedere [DotNet/aspnetcore # 3612](https://github.com/dotnet/aspnetcore/issues/3612).</span><span class="sxs-lookup"><span data-stu-id="a4541-119">For more information, see [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).</span></span>

<span data-ttu-id="a4541-120">Entity Framework Core viene fornito come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4541-120">Entity Framework Core ships as NuGet packages.</span></span> <span data-ttu-id="a4541-121">Questa modifica allinea il modello di spedizione a tutte le altre librerie di accesso ai dati in .NET.</span><span class="sxs-lookup"><span data-stu-id="a4541-121">This change aligns the shipping model with all other data access libraries on .NET.</span></span> <span data-ttu-id="a4541-122">Fornisce Entity Framework Core il percorso più semplice per continuare l'innovazione, supportando al tempo stesso le diverse piattaforme .NET.</span><span class="sxs-lookup"><span data-stu-id="a4541-122">It provides Entity Framework Core the simplest path to continue innovating while supporting the various .NET platforms.</span></span> <span data-ttu-id="a4541-123">Lo spostamento di Entity Framework Core fuori dal Framework condiviso non ha alcun effetto sul suo stato come libreria supportata da Microsoft, supportata e disponibile per il servizio.</span><span class="sxs-lookup"><span data-stu-id="a4541-123">The move of Entity Framework Core out of the shared framework has no impact on its status as a Microsoft-developed, supported, and serviceable library.</span></span> <span data-ttu-id="a4541-124">Il [criterio di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) continua a coprirlo.</span><span class="sxs-lookup"><span data-stu-id="a4541-124">The [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) continues to cover it.</span></span>

<span data-ttu-id="a4541-125">Json.NET e Entity Framework Core continuano a funzionare con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a4541-125">Json.NET and Entity Framework Core continue to work with ASP.NET Core.</span></span> <span data-ttu-id="a4541-126">Non verranno tuttavia inclusi nel Framework condiviso.</span><span class="sxs-lookup"><span data-stu-id="a4541-126">They won't, however, be included in the shared framework.</span></span>

<span data-ttu-id="a4541-127">Per altre informazioni, vedere [il futuro di JSON in .NET Core 3,0](https://github.com/dotnet/announcements/issues/90).</span><span class="sxs-lookup"><span data-stu-id="a4541-127">For more information, see [The future of JSON in .NET Core 3.0](https://github.com/dotnet/announcements/issues/90).</span></span> <span data-ttu-id="a4541-128">Vedere anche [l'elenco completo dei file binari](https://github.com/dotnet/aspnetcore/issues/3755) rimossi dal Framework condiviso.</span><span class="sxs-lookup"><span data-stu-id="a4541-128">Also see [the complete list of binaries](https://github.com/dotnet/aspnetcore/issues/3755) removed from the shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a4541-129">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="a4541-129">Reason for change</span></span>

<span data-ttu-id="a4541-130">Questa modifica semplifica il consumo di `Microsoft.AspNetCore.App` e riduce la duplicazione tra i pacchetti NuGet e i Framework condivisi.</span><span class="sxs-lookup"><span data-stu-id="a4541-130">This change simplifies the consumption of `Microsoft.AspNetCore.App` and reduces the duplication between NuGet packages and shared frameworks.</span></span>

<span data-ttu-id="a4541-131">Per ulteriori informazioni sulla motivazione di questa modifica, vedere [questo post di Blog](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="a4541-131">For more information on the motivation for this change, see [this blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a4541-132">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a4541-132">Recommended action</span></span>

<span data-ttu-id="a4541-133">Non sarà necessario per i progetti utilizzare gli assembly in `Microsoft.AspNetCore.App` come pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4541-133">It won't be necessary for projects to consume assemblies in `Microsoft.AspNetCore.App` as NuGet packages.</span></span> <span data-ttu-id="a4541-134">Per semplificare la destinazione e l'utilizzo di ASP.NET Core Framework condiviso, molti pacchetti NuGet forniti da ASP.NET Core 1,0 non vengono più prodotti.</span><span class="sxs-lookup"><span data-stu-id="a4541-134">To simplify the targeting and usage of the ASP.NET Core shared framework, many NuGet packages shipped since ASP.NET Core 1.0 are no longer produced.</span></span> <span data-ttu-id="a4541-135">Le API fornite dai pacchetti sono ancora disponibili per le app usando un `<FrameworkReference>` a `Microsoft.AspNetCore.App` .</span><span class="sxs-lookup"><span data-stu-id="a4541-135">The APIs those packages provide are still available to apps by using a `<FrameworkReference>` to `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="a4541-136">Esempi di API comuni sono gheppio, MVC e Razor.</span><span class="sxs-lookup"><span data-stu-id="a4541-136">Common API examples include Kestrel, MVC, and Razor.</span></span>

<span data-ttu-id="a4541-137">Questa modifica non si applica a tutti i file binari a cui viene fatto riferimento tramite `Microsoft.AspNetCore.App` in ASP.NET Core 2. x.</span><span class="sxs-lookup"><span data-stu-id="a4541-137">This change doesn't apply to all binaries referenced via `Microsoft.AspNetCore.App` in ASP.NET Core 2.x.</span></span> <span data-ttu-id="a4541-138">Le eccezioni rilevanti includono:</span><span class="sxs-lookup"><span data-stu-id="a4541-138">Notable exceptions include:</span></span>

- <span data-ttu-id="a4541-139">`Microsoft.Extensions`le librerie che continuano a .NET Standard di destinazione saranno disponibili come pacchetti NuGet (vedere <https://github.com/dotnet/extensions> ).</span><span class="sxs-lookup"><span data-stu-id="a4541-139">`Microsoft.Extensions` libraries that continue to target .NET Standard will be available as NuGet packages (see <https://github.com/dotnet/extensions>).</span></span>
- <span data-ttu-id="a4541-140">API prodotte dal team di ASP.NET Core che non fanno parte di `Microsoft.AspNetCore.App` .</span><span class="sxs-lookup"><span data-stu-id="a4541-140">APIs produced by the ASP.NET Core team that aren't part of `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="a4541-141">Ad esempio, i componenti seguenti sono disponibili come pacchetti NuGet:</span><span class="sxs-lookup"><span data-stu-id="a4541-141">For example, the following components are available as NuGet packages:</span></span>
  - <span data-ttu-id="a4541-142">Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="a4541-142">Entity Framework Core</span></span>
  - <span data-ttu-id="a4541-143">API che forniscono integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="a4541-143">APIs that provide third-party integration</span></span>
  - <span data-ttu-id="a4541-144">Funzionalità sperimentali</span><span class="sxs-lookup"><span data-stu-id="a4541-144">Experimental features</span></span>
  - <span data-ttu-id="a4541-145">API con dipendenze che non sono [in grado di soddisfare i requisiti per il Framework condiviso](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)</span><span class="sxs-lookup"><span data-stu-id="a4541-145">APIs with dependencies that couldn't [fulfill the requirements to be in the shared framework](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)</span></span>
- <span data-ttu-id="a4541-146">Estensioni a MVC che gestiscono il supporto per Json.NET.</span><span class="sxs-lookup"><span data-stu-id="a4541-146">Extensions to MVC that maintain support for Json.NET.</span></span> <span data-ttu-id="a4541-147">Un'API verrà fornita come pacchetto NuGet per supportare l'uso di Json.NET e MVC.</span><span class="sxs-lookup"><span data-stu-id="a4541-147">An API will be provided as a NuGet package to support using Json.NET and MVC.</span></span>
- <span data-ttu-id="a4541-148">Il client .NET SignalR continuerà a supportare .NET Standard e spedire come pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4541-148">The SignalR .NET client will continue to support .NET Standard and ship as a NuGet package.</span></span> <span data-ttu-id="a4541-149">È destinata all'uso in molti Runtime .NET, ad esempio Novell e UWP.</span><span class="sxs-lookup"><span data-stu-id="a4541-149">It's intended for use on many .NET runtimes, such as Xamarin and UWP.</span></span>

<span data-ttu-id="a4541-150">Per altre informazioni, vedere [interrompere la produzione di pacchetti per assembly di Framework condivisi in 3,0](https://github.com/dotnet/aspnetcore/issues/3756).</span><span class="sxs-lookup"><span data-stu-id="a4541-150">For more information, see [Stop producing packages for shared framework assemblies in 3.0](https://github.com/dotnet/aspnetcore/issues/3756).</span></span> <span data-ttu-id="a4541-151">Per informazioni, vedere [DotNet/aspnetcore # 3757](https://github.com/dotnet/aspnetcore/issues/3757).</span><span class="sxs-lookup"><span data-stu-id="a4541-151">For discussion, see [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).</span></span>

#### <a name="category"></a><span data-ttu-id="a4541-152">Category</span><span class="sxs-lookup"><span data-stu-id="a4541-152">Category</span></span>

<span data-ttu-id="a4541-153">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a4541-153">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a4541-154">API interessate</span><span class="sxs-lookup"><span data-stu-id="a4541-154">Affected APIs</span></span>

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
