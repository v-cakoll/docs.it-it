---
ms.openlocfilehash: d7a93cb539baee6a70f75d3afe52fd7546ac2399
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507085"
---
### <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="5f8ed-101">Estensioni: modifiche dei riferimenti al pacchetto che interessano alcuni pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="5f8ed-101">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="5f8ed-102">Con la migrazione di alcuni `Microsoft.Extensions.*` pacchetti NuGet dal repository [DotNet/Extensions](https://github.com/dotnet/extensions) a [DotNet/Runtime](https://github.com/dotnet/runtime), come descritto in [ASPNET/annunciations # 411](https://github.com/aspnet/Announcements/issues/411), le modifiche al pacchetto vengono applicate ad alcuni pacchetti migrati.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-102">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="5f8ed-103">Per informazioni su questo problema, vedere [DotNet/aspnetcore # 21033](https://github.com/dotnet/aspnetcore/issues/21033).</span><span class="sxs-lookup"><span data-stu-id="5f8ed-103">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5f8ed-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="5f8ed-104">Version introduced</span></span>

<span data-ttu-id="5f8ed-105">5,0 Anteprima 4</span><span class="sxs-lookup"><span data-stu-id="5f8ed-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5f8ed-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="5f8ed-106">Old behavior</span></span>

<span data-ttu-id="5f8ed-107">Alcuni `Microsoft.Extensions.*` pacchetti includono riferimenti ai pacchetti per le API in cui si è basata l'app.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-107">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5f8ed-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="5f8ed-108">New behavior</span></span>

<span data-ttu-id="5f8ed-109">È possibile che l'app debba `Microsoft.Extensions.*` aggiungere dipendenze del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-109">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5f8ed-110">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="5f8ed-110">Reason for change</span></span>

<span data-ttu-id="5f8ed-111">I criteri di creazione dei pacchetti sono stati aggiornati per un migliore allineamento con il repository *DotNet/Runtime* .</span><span class="sxs-lookup"><span data-stu-id="5f8ed-111">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="5f8ed-112">In base ai nuovi criteri, i riferimenti ai pacchetti non utilizzati vengono rimossi dai file con *estensione nupkg* durante la creazione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-112">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5f8ed-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="5f8ed-113">Recommended action</span></span>

<span data-ttu-id="5f8ed-114">I consumer dei pacchetti interessati devono aggiungere una dipendenza diretta dalla dipendenza del pacchetto rimossa nel progetto se vengono usate le API di rimozione delle dipendenze del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-114">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="5f8ed-115">Nella tabella seguente sono elencati i pacchetti interessati e le modifiche corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-115">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="5f8ed-116">Nome del pacchetto</span><span class="sxs-lookup"><span data-stu-id="5f8ed-116">Package name</span></span>|<span data-ttu-id="5f8ed-117">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="5f8ed-117">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="5f8ed-118">Microsoft. Extensions. Configuration. Binder</span><span class="sxs-lookup"><span data-stu-id="5f8ed-118">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="5f8ed-119">Riferimento rimosso a`Microsoft.Extensions.Configuration`</span><span class="sxs-lookup"><span data-stu-id="5f8ed-119">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="5f8ed-120">Microsoft. Extensions. Configuration. JSON</span><span class="sxs-lookup"><span data-stu-id="5f8ed-120">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="5f8ed-121">Riferimento rimosso a`System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="5f8ed-121">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="5f8ed-122">Microsoft. Extensions. Hosting. abstracts</span><span class="sxs-lookup"><span data-stu-id="5f8ed-122">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="5f8ed-123">Riferimento rimosso a`Microsoft.Extensions.Logging.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="5f8ed-123">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="5f8ed-124">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="5f8ed-124">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="5f8ed-125">Riferimento rimosso a`Microsoft.Extensions.Configuration.Binder`</span><span class="sxs-lookup"><span data-stu-id="5f8ed-125">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="5f8ed-126">Microsoft. Extensions. Logging. console</span><span class="sxs-lookup"><span data-stu-id="5f8ed-126">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="5f8ed-127">Riferimento rimosso a`Microsoft.Extensions.Configuration.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="5f8ed-127">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="5f8ed-128">Microsoft. Extensions. Logging. EventLog</span><span class="sxs-lookup"><span data-stu-id="5f8ed-128">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="5f8ed-129">Rimosso riferimento a `System.Diagnostics.EventLog` per il .NET Framework moniker del Framework di destinazione 4.6.1</span><span class="sxs-lookup"><span data-stu-id="5f8ed-129">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="5f8ed-130">Microsoft. Extensions. Logging. EventSource</span><span class="sxs-lookup"><span data-stu-id="5f8ed-130">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="5f8ed-131">Riferimento rimosso a`System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="5f8ed-131">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="5f8ed-132">Microsoft. Extensions. Options</span><span class="sxs-lookup"><span data-stu-id="5f8ed-132">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="5f8ed-133">Riferimento rimosso a`System.ComponentModel.Annotations`</span><span class="sxs-lookup"><span data-stu-id="5f8ed-133">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="5f8ed-134">Ad esempio, il riferimento al pacchetto `Microsoft.Extensions.Configuration` a è stato `Microsoft.Extensions.Configuration.Binder`rimosso da.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-134">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="5f8ed-135">Nel pacchetto non è stata usata alcuna API dalla dipendenza.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-135">No API from the dependency was used in the package.</span></span> <span data-ttu-id="5f8ed-136">Gli utenti `Microsoft.Extensions.Configuration.Binder` che dipendono dalle `Microsoft.Extensions.Configuration` API di devono aggiungere un riferimento diretto al progetto.</span><span class="sxs-lookup"><span data-stu-id="5f8ed-136">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

#### <a name="category"></a><span data-ttu-id="5f8ed-137">Category</span><span class="sxs-lookup"><span data-stu-id="5f8ed-137">Category</span></span>

<span data-ttu-id="5f8ed-138">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5f8ed-138">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5f8ed-139">API interessate</span><span class="sxs-lookup"><span data-stu-id="5f8ed-139">Affected APIs</span></span>

<span data-ttu-id="5f8ed-140">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5f8ed-140">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
