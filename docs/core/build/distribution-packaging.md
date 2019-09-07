---
title: Creazione di pacchetti di distribuzione di .NET Core
description: Informazione su come creare pacchetti e assegnare nome e versione ai pacchetti per la distribuzione di .NET Core.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: d72677cba1e7685f8e05cf479ec508683dd77b55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70394153"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="40998-103">Creazione di pacchetti di distribuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="40998-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="40998-104">Dato che .NET Core è disponibile in un numero sempre maggiore di piattaforme, è utile imparare a creare un pacchetto e assegnarvi un nome e una versione.</span><span class="sxs-lookup"><span data-stu-id="40998-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="40998-105">In questo modo, coloro che si occupano della manutenzione dei pacchetti possono garantire un'esperienza coerente indipendentemente dalla piattaforma scelta dagli utenti per l'esecuzione di .NET.</span><span class="sxs-lookup"><span data-stu-id="40998-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="40998-106">Questo articolo è utile per gli utenti che:</span><span class="sxs-lookup"><span data-stu-id="40998-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="40998-107">Stanno cercando di compilare .NET Core dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="40998-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="40998-108">Vogliono apportare modifiche all'interfaccia della riga di comando di .NET Core che possono avere effetti sul layout risultante o sui pacchetti prodotti.</span><span class="sxs-lookup"><span data-stu-id="40998-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="40998-109">Layout su disco</span><span class="sxs-lookup"><span data-stu-id="40998-109">Disk layout</span></span>

<span data-ttu-id="40998-110">Quando viene installato, .NET Core è costituito da diversi componenti che vengono disposti nel file system come segue:</span><span class="sxs-lookup"><span data-stu-id="40998-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
├── packs
│   ├── Microsoft.AspNetCore.App.Ref
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref
│       └── <netstandard version>        (15)
├── shared
│   ├── Microsoft.NETCore.App
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App
│       └── <desktop app version> (7)
└── templates
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="40998-111">(1) **dotnet** L'host, noto anche come "muxer", ha due ruoli distinti: attivare un runtime per avviare un'applicazione e attivare un SDK per inviare comandi all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40998-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="40998-112">L'host è un file eseguibile nativo (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="40998-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="40998-113">Benché sia presente un singolo host, la maggior parte degli altri componenti si trova in directory con versioni (2,3,5,6).</span><span class="sxs-lookup"><span data-stu-id="40998-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="40998-114">Questo significa che nel sistema possono essere presenti più versioni installate side-by-side.</span><span class="sxs-lookup"><span data-stu-id="40998-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="40998-115">(2) **host/fxr/\<versione fxr>** contiene la logica di risoluzione del framework usata dall'host.</span><span class="sxs-lookup"><span data-stu-id="40998-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="40998-116">L'host usa la versione di hostfxr più recente installata.</span><span class="sxs-lookup"><span data-stu-id="40998-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="40998-117">Hostfxr è responsabile della selezione del runtime appropriato durante l'esecuzione di un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40998-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="40998-118">Ad esempio, un'applicazione compilata per .NET Core 2.0.0 usa il runtime 2.0.5 quando è disponibile.</span><span class="sxs-lookup"><span data-stu-id="40998-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="40998-119">Analogamente, hostfxr seleziona l'SDK appropriato durante lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="40998-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="40998-120">(3) **sdk/\<versione sdk>** L'SDK, noto anche come "strumenti", è un set di strumenti gestiti che vengono usati per scrivere e compilare applicazioni e librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40998-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="40998-121">L'SDK include l'interfaccia della riga di comando (CLI) di .NET Core, i compilatori di linguaggi gestiti, MSBuild, le attività di compilazione e le destinazioni associate, NuGet, nuovi modelli di progetto e così via.</span><span class="sxs-lookup"><span data-stu-id="40998-121">The SDK includes the .NET Core Command-line interface (CLI), the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="40998-122">(4) **sdk/NuGetFallbackFolder** contiene una cache dei pacchetti NuGet usati da un SDK durante un'operazione di ripristino, come ad esempio l'esecuzione di `dotnet restore` o di `dotnet build /t:Restore`.</span><span class="sxs-lookup"><span data-stu-id="40998-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="40998-123">Questa cartella viene usata solo prima di .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="40998-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="40998-124">Non può essere compilato dall'origine perché contiene risorse binarie predefinite da `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="40998-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="40998-125">La cartella **shared** contiene i framework.</span><span class="sxs-lookup"><span data-stu-id="40998-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="40998-126">Un framework condiviso offre un set di librerie in una posizione centrale per consentirne l'uso da parte di applicazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="40998-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="40998-127">(5) **shared/Microsoft.NETCore.App/\<versione runtime>** Questo framework contiene il runtime di .NET Core e il supporto delle librerie gestite.</span><span class="sxs-lookup"><span data-stu-id="40998-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="40998-128">(6) **Shared/Microsoft. AspNetCore. { App, All}/\<aspnetcore versione >** contiene le librerie di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="40998-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="40998-129">Le librerie in `Microsoft.AspNetCore.App` vengono sviluppate e supportate come parte del progetto .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40998-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="40998-130">Le librerie in `Microsoft.AspNetCore.All` sono un superset che contiene anche le librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="40998-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="40998-131">(7) **Shared/Microsoft. desktop. app/\<app desktop version >** contiene le librerie desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="40998-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="40998-132">Questa operazione non è inclusa nelle piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="40998-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="40998-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** sono rispettivamente le licenze di .NET Core e le licenze delle librerie di terze parti usate in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40998-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="40998-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` è la pagina di manuale dotnet.</span><span class="sxs-lookup"><span data-stu-id="40998-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="40998-135">`dotnet` è un collegamento simbolico all'host dotnet (1).</span><span class="sxs-lookup"><span data-stu-id="40998-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="40998-136">Questi file vengono installati in percorsi ben noti per l'integrazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="40998-136">These files are installed at well known locations for system integration.</span></span>

- <span data-ttu-id="40998-137">(11, 12) **Microsoft. NETCore. app. Ref, Microsoft. AspNetCore. app. Ref** descrivono l'API di `x.y` una versione di .NET Core e ASP.NET Core rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="40998-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="40998-138">Questi pacchetti vengono usati durante la compilazione per le versioni di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40998-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="40998-139">(13) **Microsoft. NETCore. app. host.\< RID >** contiene un file binario nativo per `rid`la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="40998-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="40998-140">Questo file binario è un modello quando si compila un'applicazione .NET Core in un file binario nativo per tale piattaforma.</span><span class="sxs-lookup"><span data-stu-id="40998-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="40998-141">(14) **Microsoft. WindowsDesktop. app. Ref** descrive l'API della `x.y` versione delle applicazioni desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="40998-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="40998-142">Questi file vengono usati durante la compilazione per la destinazione.</span><span class="sxs-lookup"><span data-stu-id="40998-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="40998-143">Questa opzione non è disponibile nelle piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="40998-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="40998-144">(15) **NETStandard. Library. Ref** descrive l'API `x.y` NETStandard.</span><span class="sxs-lookup"><span data-stu-id="40998-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="40998-145">Questi file vengono usati durante la compilazione per la destinazione.</span><span class="sxs-lookup"><span data-stu-id="40998-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="40998-146">(16) **/etc/DotNet/install_location** è un file che contiene il percorso completo della cartella che contiene il `dotnet` file binario host.</span><span class="sxs-lookup"><span data-stu-id="40998-146">(16) **/etc/dotnet/install_location** is a file that contains the full path to the folder that contains the `dotnet` host binary.</span></span> <span data-ttu-id="40998-147">Il percorso può terminare con una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="40998-147">The path may be terminated with a newline.</span></span> <span data-ttu-id="40998-148">Non è necessario aggiungere questo file quando la radice è `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="40998-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="40998-149">(17) i **modelli** contengono i modelli usati dall'SDK.</span><span class="sxs-lookup"><span data-stu-id="40998-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="40998-150">Ad esempio, `dotnet new` trova qui i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="40998-150">For example, `dotnet new` finds project templates here.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="40998-151">Pacchetti consigliati</span><span class="sxs-lookup"><span data-stu-id="40998-151">Recommended packages</span></span>

<span data-ttu-id="40998-152">Il controllo delle versioni di .NET Core è basato sui numeri di versione `[major].[minor]` del componente di runtime.</span><span class="sxs-lookup"><span data-stu-id="40998-152">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="40998-153">La versione dell'SDK usa gli stessi elementi `[major].[minor]` e ha un elemento `[patch]` indipendente che combina la semantica della versione definitiva e della versione patch per l'SDK.</span><span class="sxs-lookup"><span data-stu-id="40998-153">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="40998-154">Ad esempio: la versione 2.2.302 dell'SDK è la seconda versione patch della terza versione definitiva dell'SDK che supporta il runtime 2.2.</span><span class="sxs-lookup"><span data-stu-id="40998-154">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="40998-155">Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="40998-155">For more information about how versioning works, see [.NET Core versioning overview](../versions/index.md).</span></span>

<span data-ttu-id="40998-156">Alcuni pacchetti includono parte del numero di versione nel nome.</span><span class="sxs-lookup"><span data-stu-id="40998-156">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="40998-157">Questo consente di installare una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="40998-157">This allows you to install a specific version.</span></span>
<span data-ttu-id="40998-158">La parte rimanente della versione non è inclusa nel nome della versione.</span><span class="sxs-lookup"><span data-stu-id="40998-158">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="40998-159">Ciò consente alla gestione pacchetti del sistema operativo di aggiornare i pacchetti, ad esempio installando automaticamente le correzioni per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="40998-159">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="40998-160">La gestione pacchetti supportata è specifica per Linux.</span><span class="sxs-lookup"><span data-stu-id="40998-160">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="40998-161">Di seguito sono elencati i pacchetti consigliati:</span><span class="sxs-lookup"><span data-stu-id="40998-161">The following lists the recommended packages:</span></span>

- <span data-ttu-id="40998-162">`dotnet-sdk-[major].[minor]`-Installa l'SDK più recente per un runtime specifico</span><span class="sxs-lookup"><span data-stu-id="40998-162">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="40998-163">**Versione:** \<> versione runtime</span><span class="sxs-lookup"><span data-stu-id="40998-163">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="40998-164">**Esempio:** DotNet-sdk-2,1</span><span class="sxs-lookup"><span data-stu-id="40998-164">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="40998-165">**Contiene** (3),(4)</span><span class="sxs-lookup"><span data-stu-id="40998-165">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="40998-166">**Dipendenze:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`,`dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="40998-166">**Dependencies:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="40998-167">`aspnetcore-runtime-[major].[minor]`-Installa un runtime di ASP.NET Core specifico</span><span class="sxs-lookup"><span data-stu-id="40998-167">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="40998-168">**Versione:** \<> versione runtime aspnetcore</span><span class="sxs-lookup"><span data-stu-id="40998-168">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="40998-169">**Esempio:** aspnetcore-runtime-2,1</span><span class="sxs-lookup"><span data-stu-id="40998-169">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="40998-170">**Contiene** (6)</span><span class="sxs-lookup"><span data-stu-id="40998-170">**Contains:** (6)</span></span>
  - <span data-ttu-id="40998-171">**Dipendenze:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="40998-171">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="40998-172">`dotnet-runtime-deps-[major].[minor]` _(Facoltativo)_ : installa le dipendenze per l'esecuzione di applicazioni autosufficienti</span><span class="sxs-lookup"><span data-stu-id="40998-172">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="40998-173">**Versione:** \<> versione runtime</span><span class="sxs-lookup"><span data-stu-id="40998-173">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="40998-174">**Esempio:** DotNet-Runtime-deps-2,1</span><span class="sxs-lookup"><span data-stu-id="40998-174">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="40998-175">**Dipendenze:** _dipendenze specifiche della distribuzione_</span><span class="sxs-lookup"><span data-stu-id="40998-175">**Dependencies:** _distro specific dependencies_</span></span>

- <span data-ttu-id="40998-176">`dotnet-runtime-[major].[minor]`-Installa un runtime specifico</span><span class="sxs-lookup"><span data-stu-id="40998-176">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="40998-177">**Versione:** \<> versione runtime</span><span class="sxs-lookup"><span data-stu-id="40998-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="40998-178">**Esempio:** DotNet-runtime-2,1</span><span class="sxs-lookup"><span data-stu-id="40998-178">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="40998-179">**Contiene** (5)</span><span class="sxs-lookup"><span data-stu-id="40998-179">**Contains:** (5)</span></span>
  - <span data-ttu-id="40998-180">**Dipendenze:** `dotnet-hostfxr:<runtime version>+`,`dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="40998-180">**Dependencies:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="40998-181">`dotnet-hostfxr`-dipendenza</span><span class="sxs-lookup"><span data-stu-id="40998-181">`dotnet-hostfxr` - dependency</span></span>
  - <span data-ttu-id="40998-182">**Versione:** \<> versione runtime</span><span class="sxs-lookup"><span data-stu-id="40998-182">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="40998-183">**Esempio:** DotNet-hostfxr</span><span class="sxs-lookup"><span data-stu-id="40998-183">**Example:** dotnet-hostfxr</span></span>
  - <span data-ttu-id="40998-184">**Contiene** (2)</span><span class="sxs-lookup"><span data-stu-id="40998-184">**Contains:** (2)</span></span>
  - <span data-ttu-id="40998-185">**Dipendenze:** `host:<runtime version>+`</span><span class="sxs-lookup"><span data-stu-id="40998-185">**Dependencies:** `host:<runtime version>+`</span></span>

- <span data-ttu-id="40998-186">`dotnet-host`-dipendenza</span><span class="sxs-lookup"><span data-stu-id="40998-186">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="40998-187">**Versione:** \<> versione runtime</span><span class="sxs-lookup"><span data-stu-id="40998-187">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="40998-188">**Esempio:** DotNet-host</span><span class="sxs-lookup"><span data-stu-id="40998-188">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="40998-189">**Contiene** (1), (8), (9), (10), (16)</span><span class="sxs-lookup"><span data-stu-id="40998-189">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="40998-190">`dotnet-apphost-pack-[major].[minor]`-dipendenza</span><span class="sxs-lookup"><span data-stu-id="40998-190">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="40998-191">**Versione:** \<> versione runtime</span><span class="sxs-lookup"><span data-stu-id="40998-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="40998-192">**Contiene** 13</span><span class="sxs-lookup"><span data-stu-id="40998-192">**Contains:** (13)</span></span>

- <span data-ttu-id="40998-193">`dotnet-targeting-pack-[major].[minor]`-Consente la destinazione di un runtime non più recente</span><span class="sxs-lookup"><span data-stu-id="40998-193">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="40998-194">**Versione:** \<> versione runtime</span><span class="sxs-lookup"><span data-stu-id="40998-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="40998-195">**Contiene** 12</span><span class="sxs-lookup"><span data-stu-id="40998-195">**Contains:** (12)</span></span>

- <span data-ttu-id="40998-196">`aspnetcore-targeting-pack-[major].[minor]`-Consente la destinazione di un runtime non più recente</span><span class="sxs-lookup"><span data-stu-id="40998-196">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="40998-197">**Versione:** \<> versione runtime aspnetcore</span><span class="sxs-lookup"><span data-stu-id="40998-197">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="40998-198">**Contiene** 11</span><span class="sxs-lookup"><span data-stu-id="40998-198">**Contains:** (11)</span></span>

- <span data-ttu-id="40998-199">`netstandard-targeting-pack-[major].[minor]`-Consente la destinazione di una versione di netstandard</span><span class="sxs-lookup"><span data-stu-id="40998-199">`netstandard-targeting-pack-[major].[minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="40998-200">**Versione:** \<versione SDK ></span><span class="sxs-lookup"><span data-stu-id="40998-200">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="40998-201">**Contiene** 15</span><span class="sxs-lookup"><span data-stu-id="40998-201">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="40998-202">**Versione:** \<versione SDK ></span><span class="sxs-lookup"><span data-stu-id="40998-202">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="40998-203">**Contiene** 15</span><span class="sxs-lookup"><span data-stu-id="40998-203">**Contains:** (15)</span></span>

<span data-ttu-id="40998-204">Richiede la comprensione delle _dipendenze specifiche della distribuzione._ `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="40998-204">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro specific dependencies_.</span></span> <span data-ttu-id="40998-205">Poiché il sistema di compilazione della distribuzione potrebbe essere in grado di derivare automaticamente questo valore, il pacchetto è facoltativo, nel qual caso queste dipendenze vengono aggiunte direttamente al `dotnet-runtime-[major].[minor]` pacchetto.</span><span class="sxs-lookup"><span data-stu-id="40998-205">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="40998-206">Quando il contenuto del pacchetto si trova in una cartella con versione, `[major].[minor]` il nome del pacchetto corrisponde al nome della cartella con versione.</span><span class="sxs-lookup"><span data-stu-id="40998-206">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="40998-207">Per tutti i pacchetti, ad `netstandard-targeting-pack-[major].[minor]`eccezione di, corrisponde anche alla versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="40998-207">For all packages, except the `netstandard-targeting-pack-[major].[minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="40998-208">Le dipendenze tra i pacchetti devono usare un requisito _di versione uguale o maggiore di_ .</span><span class="sxs-lookup"><span data-stu-id="40998-208">Dependencies between packages should use a _equal or greater than_ version requirement.</span></span> <span data-ttu-id="40998-209">Ad esempio, `dotnet-sdk-2.2:2.2.401` richiede `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="40998-209">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="40998-210">In questo modo, l'utente può aggiornare l'installazione tramite un pacchetto radice, ad esempio `dnf update dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="40998-210">This makes it possible for the user to upgrade their installation via a root package (e.g. `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="40998-211">Per la maggior parte delle distribuzioni è necessario che tutti gli elementi vengano compilati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="40998-211">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="40998-212">Questo ha un certo impatto sui pacchetti:</span><span class="sxs-lookup"><span data-stu-id="40998-212">This has some impact on the packages:</span></span>

- <span data-ttu-id="40998-213">Le librerie di terze parti in `shared/Microsoft.AspNetCore.All` non possono essere compilate facilmente dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="40998-213">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="40998-214">Quindi la cartella viene omessa dal pacchetto `aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="40998-214">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="40998-215">`NuGetFallbackFolder` viene popolato usando elementi binari da `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="40998-215">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="40998-216">Deve rimanere vuoto.</span><span class="sxs-lookup"><span data-stu-id="40998-216">It should remain empty.</span></span>

<span data-ttu-id="40998-217">Più pacchetti `dotnet-sdk` possono contenere gli stessi file per `NuGetFallbackFolder`.</span><span class="sxs-lookup"><span data-stu-id="40998-217">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="40998-218">Per evitare problemi con la gestione pacchetti, questi file devono essere identici (checksum, data di modifica e così via).</span><span class="sxs-lookup"><span data-stu-id="40998-218">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="40998-219">Compilazione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="40998-219">Building packages</span></span>

<span data-ttu-id="40998-220">Il repository [dotnet/source-build](https://github.com/dotnet/source-build) contiene istruzioni su come compilare un file tarball di origine di .NET Core SDK e tutti i relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="40998-220">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="40998-221">L'output del repository di compilazione dell'origine corrisponde al layout descritto nella prima sezione di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="40998-221">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
