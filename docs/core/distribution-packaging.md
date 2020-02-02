---
title: Creazione di pacchetti di distribuzione di .NET Core
description: Informazione su come creare pacchetti e assegnare nome e versione ai pacchetti per la distribuzione di .NET Core.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: a345aeded29b3058c6c56abbff439ea26cbc7afb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920867"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="e1c70-103">Creazione di pacchetti di distribuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="e1c70-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="e1c70-104">Dato che .NET Core è disponibile in un numero sempre maggiore di piattaforme, è utile imparare a creare un pacchetto e assegnarvi un nome e una versione.</span><span class="sxs-lookup"><span data-stu-id="e1c70-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="e1c70-105">In questo modo, coloro che si occupano della manutenzione dei pacchetti possono garantire un'esperienza coerente indipendentemente dalla piattaforma scelta dagli utenti per l'esecuzione di .NET.</span><span class="sxs-lookup"><span data-stu-id="e1c70-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="e1c70-106">Questo articolo è utile per gli utenti che:</span><span class="sxs-lookup"><span data-stu-id="e1c70-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="e1c70-107">Stanno cercando di compilare .NET Core dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e1c70-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="e1c70-108">Vogliono apportare modifiche all'interfaccia della riga di comando di .NET Core che possono avere effetti sul layout risultante o sui pacchetti prodotti.</span><span class="sxs-lookup"><span data-stu-id="e1c70-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="e1c70-109">Layout del disco</span><span class="sxs-lookup"><span data-stu-id="e1c70-109">Disk layout</span></span>

<span data-ttu-id="e1c70-110">Quando viene installato, .NET Core è costituito da diversi componenti che vengono disposti nel file system come segue:</span><span class="sxs-lookup"><span data-stu-id="e1c70-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="e1c70-111">(1) **dotnet** L'host, noto anche come "muxer", ha due ruoli distinti: attivare un runtime per avviare un'applicazione e attivare un SDK per inviare comandi all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1c70-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="e1c70-112">L'host è un file eseguibile nativo (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="e1c70-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="e1c70-113">Benché sia presente un singolo host, la maggior parte degli altri componenti si trova in directory con versioni (2,3,5,6).</span><span class="sxs-lookup"><span data-stu-id="e1c70-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="e1c70-114">Questo significa che nel sistema possono essere presenti più versioni installate side-by-side.</span><span class="sxs-lookup"><span data-stu-id="e1c70-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="e1c70-115">(2) **host/fxr/\<versione fxr>** contiene la logica di risoluzione del framework usata dall'host.</span><span class="sxs-lookup"><span data-stu-id="e1c70-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="e1c70-116">L'host usa la versione di hostfxr più recente installata.</span><span class="sxs-lookup"><span data-stu-id="e1c70-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="e1c70-117">Hostfxr è responsabile della selezione del runtime appropriato durante l'esecuzione di un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1c70-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="e1c70-118">Ad esempio, un'applicazione compilata per .NET Core 2.0.0 usa il runtime 2.0.5 quando è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e1c70-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="e1c70-119">Analogamente, hostfxr seleziona l'SDK appropriato durante lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e1c70-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="e1c70-120">(3) **sdk/\<versione sdk>** L'SDK, noto anche come "strumenti", è un set di strumenti gestiti che vengono usati per scrivere e compilare applicazioni e librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1c70-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="e1c70-121">L'SDK include le interfaccia della riga di comando di .NET Core, i compilatori di linguaggi gestiti, MSBuild e le attività e le destinazioni di compilazione associate, NuGet, nuovi modelli di progetto e così via.</span><span class="sxs-lookup"><span data-stu-id="e1c70-121">The SDK includes the .NET Core CLI, the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="e1c70-122">(4) **sdk/NuGetFallbackFolder** contiene una cache dei pacchetti NuGet usati da un SDK durante un'operazione di ripristino, come ad esempio l'esecuzione di `dotnet restore` o di `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build`.</span></span> <span data-ttu-id="e1c70-123">Questa cartella viene usata solo prima di .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="e1c70-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="e1c70-124">Non può essere compilato dall'origine perché contiene risorse binarie predefinite da `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="e1c70-125">La cartella **shared** contiene i framework.</span><span class="sxs-lookup"><span data-stu-id="e1c70-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="e1c70-126">Un framework condiviso offre un set di librerie in una posizione centrale per consentirne l'uso da parte di applicazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="e1c70-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="e1c70-127">(5) **shared/Microsoft.NETCore.App/\<versione runtime>** Questo framework contiene il runtime di .NET Core e il supporto delle librerie gestite.</span><span class="sxs-lookup"><span data-stu-id="e1c70-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="e1c70-128">(6) **Shared/Microsoft. AspNetCore. { App, all}/\<versione di aspnetcore >** contiene le librerie di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1c70-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="e1c70-129">Le librerie in `Microsoft.AspNetCore.App` vengono sviluppate e supportate come parte del progetto .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1c70-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="e1c70-130">Le librerie in `Microsoft.AspNetCore.All` sono un superset che contiene anche le librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e1c70-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="e1c70-131">(7) la **versione dell'app desktop Shared/Microsoft. desktop. app/\<** contiene le librerie desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="e1c70-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="e1c70-132">Questa operazione non è inclusa nelle piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="e1c70-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="e1c70-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** sono rispettivamente le licenze di .NET Core e le licenze delle librerie di terze parti usate in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1c70-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="e1c70-134">(9, 10) **dotnet. 1. gz, dotnet** `dotnet.1.gz` è la pagina manuale dotnet.</span><span class="sxs-lookup"><span data-stu-id="e1c70-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="e1c70-135">`dotnet` è un collegamento simbolico all'host dotnet (1).</span><span class="sxs-lookup"><span data-stu-id="e1c70-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="e1c70-136">Questi file vengono installati in percorsi ben noti per l'integrazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="e1c70-136">These files are installed at well-known locations for system integration.</span></span>

- <span data-ttu-id="e1c70-137">(11, 12) **Microsoft. NETCore. app. Ref, Microsoft. AspNetCore. app. Ref** descrivono l'API di una versione `x.y` di .NET Core e ASP.NET Core rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e1c70-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="e1c70-138">Questi pacchetti vengono usati durante la compilazione per le versioni di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e1c70-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="e1c70-139">(13) **Microsoft. NETCore. app. host.\<rid >** contiene un file binario nativo per `rid`della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e1c70-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="e1c70-140">Questo file binario è un modello quando si compila un'applicazione .NET Core in un file binario nativo per tale piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e1c70-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="e1c70-141">(14) **Microsoft. WindowsDesktop. app. Ref** descrive l'API della versione `x.y` delle applicazioni desktop di Windows.</span><span class="sxs-lookup"><span data-stu-id="e1c70-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="e1c70-142">Questi file vengono usati durante la compilazione per la destinazione.</span><span class="sxs-lookup"><span data-stu-id="e1c70-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="e1c70-143">Questa opzione non è disponibile nelle piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="e1c70-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="e1c70-144">(15) **NETStandard. Library. Ref** descrive l'API NETStandard `x.y`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="e1c70-145">Questi file vengono usati durante la compilazione per la destinazione.</span><span class="sxs-lookup"><span data-stu-id="e1c70-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="e1c70-146">(16) **/etc/dotnet/install_location** è un file che contiene il percorso completo per `{dotnet_root}`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-146">(16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`.</span></span> <span data-ttu-id="e1c70-147">Il percorso può terminare con una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="e1c70-147">The path may end with a newline.</span></span> <span data-ttu-id="e1c70-148">Non è necessario aggiungere questo file quando viene `/usr/share/dotnet`la radice.</span><span class="sxs-lookup"><span data-stu-id="e1c70-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="e1c70-149">(17) i **modelli** contengono i modelli usati dall'SDK.</span><span class="sxs-lookup"><span data-stu-id="e1c70-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="e1c70-150">Ad esempio, `dotnet new` trova qui i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="e1c70-150">For example, `dotnet new` finds project templates here.</span></span>

<span data-ttu-id="e1c70-151">Le cartelle contrassegnate con `(*)` vengono utilizzate da più pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e1c70-151">The folders marked with `(*)` are used by multiple packages.</span></span> <span data-ttu-id="e1c70-152">Alcuni formati di pacchetto (ad esempio `rpm`) richiedono una gestione speciale di tali cartelle.</span><span class="sxs-lookup"><span data-stu-id="e1c70-152">Some package formats (for example, `rpm`) require special handling of such folders.</span></span> <span data-ttu-id="e1c70-153">Il gestore del pacchetto deve occuparsi di questo.</span><span class="sxs-lookup"><span data-stu-id="e1c70-153">The package maintainer must take care of this.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="e1c70-154">Pacchetti consigliati</span><span class="sxs-lookup"><span data-stu-id="e1c70-154">Recommended packages</span></span>

<span data-ttu-id="e1c70-155">Il controllo delle versioni di .NET Core è basato sui numeri di versione `[major].[minor]` del componente di runtime.</span><span class="sxs-lookup"><span data-stu-id="e1c70-155">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="e1c70-156">La versione dell'SDK usa gli stessi elementi `[major].[minor]` e ha un elemento `[patch]` indipendente che combina la semantica della versione definitiva e della versione patch per l'SDK.</span><span class="sxs-lookup"><span data-stu-id="e1c70-156">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="e1c70-157">Ad esempio, l'SDK versione 2.2.302 è la seconda versione della versione della terza funzionalità dell'SDK che supporta il runtime di 2,2.</span><span class="sxs-lookup"><span data-stu-id="e1c70-157">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="e1c70-158">Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](./versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="e1c70-158">For more information about how versioning works, see [.NET Core versioning overview](./versions/index.md).</span></span>

<span data-ttu-id="e1c70-159">Alcuni pacchetti includono parte del numero di versione nel nome.</span><span class="sxs-lookup"><span data-stu-id="e1c70-159">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="e1c70-160">Questo consente di installare una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="e1c70-160">This allows you to install a specific version.</span></span>
<span data-ttu-id="e1c70-161">La parte rimanente della versione non è inclusa nel nome della versione.</span><span class="sxs-lookup"><span data-stu-id="e1c70-161">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="e1c70-162">Ciò consente alla gestione pacchetti del sistema operativo di aggiornare i pacchetti, ad esempio installando automaticamente le correzioni per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e1c70-162">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="e1c70-163">La gestione pacchetti supportata è specifica per Linux.</span><span class="sxs-lookup"><span data-stu-id="e1c70-163">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="e1c70-164">Di seguito sono elencati i pacchetti consigliati:</span><span class="sxs-lookup"><span data-stu-id="e1c70-164">The following lists the recommended packages:</span></span>

- <span data-ttu-id="e1c70-165">`dotnet-sdk-[major].[minor]`-installa l'SDK più recente per un runtime specifico</span><span class="sxs-lookup"><span data-stu-id="e1c70-165">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="e1c70-166">**Versione:** \<versione runtime ></span><span class="sxs-lookup"><span data-stu-id="e1c70-166">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e1c70-167">**Esempio:** DotNet-sdk-2,1</span><span class="sxs-lookup"><span data-stu-id="e1c70-167">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="e1c70-168">**Contiene:** (3), (4)</span><span class="sxs-lookup"><span data-stu-id="e1c70-168">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="e1c70-169">**Dipendenze:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e1c70-169">**Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="e1c70-170">`aspnetcore-runtime-[major].[minor]`-installa un runtime di ASP.NET Core specifico</span><span class="sxs-lookup"><span data-stu-id="e1c70-170">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="e1c70-171">**Versione:** \<versione runtime aspnetcore ></span><span class="sxs-lookup"><span data-stu-id="e1c70-171">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="e1c70-172">**Esempio:** aspnetcore-runtime-2,1</span><span class="sxs-lookup"><span data-stu-id="e1c70-172">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="e1c70-173">**Contiene:** (6)</span><span class="sxs-lookup"><span data-stu-id="e1c70-173">**Contains:** (6)</span></span>
  - <span data-ttu-id="e1c70-174">**Dipendenze:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e1c70-174">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="e1c70-175">`dotnet-runtime-deps-[major].[minor]` _(facoltativo)_ : installa le dipendenze per l'esecuzione di applicazioni autosufficienti</span><span class="sxs-lookup"><span data-stu-id="e1c70-175">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="e1c70-176">**Versione:** \<versione runtime ></span><span class="sxs-lookup"><span data-stu-id="e1c70-176">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e1c70-177">**Esempio:** DotNet-Runtime-deps-2,1</span><span class="sxs-lookup"><span data-stu-id="e1c70-177">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="e1c70-178">**Dipendenze:** _dipendenze specifiche della distribuzione_</span><span class="sxs-lookup"><span data-stu-id="e1c70-178">**Dependencies:** _distribution-specific dependencies_</span></span>

- <span data-ttu-id="e1c70-179">`dotnet-runtime-[major].[minor]`-installa un runtime specifico</span><span class="sxs-lookup"><span data-stu-id="e1c70-179">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="e1c70-180">**Versione:** \<versione runtime ></span><span class="sxs-lookup"><span data-stu-id="e1c70-180">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e1c70-181">**Esempio:** DotNet-runtime-2,1</span><span class="sxs-lookup"><span data-stu-id="e1c70-181">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="e1c70-182">**Contiene:** (5)</span><span class="sxs-lookup"><span data-stu-id="e1c70-182">**Contains:** (5)</span></span>
  - <span data-ttu-id="e1c70-183">**Dipendenze:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e1c70-183">**Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="e1c70-184">dipendenza da `dotnet-hostfxr-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e1c70-184">`dotnet-hostfxr-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="e1c70-185">**Versione:** \<versione runtime ></span><span class="sxs-lookup"><span data-stu-id="e1c70-185">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e1c70-186">**Esempio:** DotNet-hostfxr-3,0</span><span class="sxs-lookup"><span data-stu-id="e1c70-186">**Example:** dotnet-hostfxr-3.0</span></span>
  - <span data-ttu-id="e1c70-187">**Contiene:** (2)</span><span class="sxs-lookup"><span data-stu-id="e1c70-187">**Contains:** (2)</span></span>
  - <span data-ttu-id="e1c70-188">**Dipendenze:** `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="e1c70-188">**Dependencies:** `dotnet-host`</span></span>

- <span data-ttu-id="e1c70-189">dipendenza da `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="e1c70-189">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="e1c70-190">**Versione:** \<versione runtime ></span><span class="sxs-lookup"><span data-stu-id="e1c70-190">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e1c70-191">**Esempio:** DotNet-host</span><span class="sxs-lookup"><span data-stu-id="e1c70-191">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="e1c70-192">**Contiene:** (1), (8), (9), (10), (16)</span><span class="sxs-lookup"><span data-stu-id="e1c70-192">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="e1c70-193">dipendenza da `dotnet-apphost-pack-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="e1c70-193">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="e1c70-194">**Versione:** \<versione runtime ></span><span class="sxs-lookup"><span data-stu-id="e1c70-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e1c70-195">**Contiene:** (13)</span><span class="sxs-lookup"><span data-stu-id="e1c70-195">**Contains:** (13)</span></span>

- <span data-ttu-id="e1c70-196">`dotnet-targeting-pack-[major].[minor]`: consente la destinazione di un runtime non più recente</span><span class="sxs-lookup"><span data-stu-id="e1c70-196">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="e1c70-197">**Versione:** \<versione runtime ></span><span class="sxs-lookup"><span data-stu-id="e1c70-197">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="e1c70-198">**Contiene:** (12)</span><span class="sxs-lookup"><span data-stu-id="e1c70-198">**Contains:** (12)</span></span>

- <span data-ttu-id="e1c70-199">`aspnetcore-targeting-pack-[major].[minor]`: consente la destinazione di un runtime non più recente</span><span class="sxs-lookup"><span data-stu-id="e1c70-199">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="e1c70-200">**Versione:** \<versione runtime aspnetcore ></span><span class="sxs-lookup"><span data-stu-id="e1c70-200">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="e1c70-201">**Contiene:** (11)</span><span class="sxs-lookup"><span data-stu-id="e1c70-201">**Contains:** (11)</span></span>

- <span data-ttu-id="e1c70-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: consente la destinazione di una versione di netstandard</span><span class="sxs-lookup"><span data-stu-id="e1c70-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="e1c70-203">**Versione:** \<versione SDK ></span><span class="sxs-lookup"><span data-stu-id="e1c70-203">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="e1c70-204">**Contiene:** (15)</span><span class="sxs-lookup"><span data-stu-id="e1c70-204">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="e1c70-205">**Versione:** \<versione SDK ></span><span class="sxs-lookup"><span data-stu-id="e1c70-205">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="e1c70-206">**Contiene:** (15)</span><span class="sxs-lookup"><span data-stu-id="e1c70-206">**Contains:** (15)</span></span>

<span data-ttu-id="e1c70-207">Per la `dotnet-runtime-deps-[major].[minor]` è necessario comprendere le _dipendenze specifiche della distribuzione_.</span><span class="sxs-lookup"><span data-stu-id="e1c70-207">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_.</span></span> <span data-ttu-id="e1c70-208">Poiché il sistema di compilazione della distribuzione potrebbe essere in grado di derivare automaticamente questo valore, il pacchetto è facoltativo, nel qual caso queste dipendenze vengono aggiunte direttamente al pacchetto `dotnet-runtime-[major].[minor]`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-208">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="e1c70-209">Quando il contenuto del pacchetto si trova in una cartella con versione, il nome del pacchetto `[major].[minor]` corrisponde al nome della cartella con versione.</span><span class="sxs-lookup"><span data-stu-id="e1c70-209">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="e1c70-210">Per tutti i pacchetti, ad eccezione del `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, questo corrisponde anche alla versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1c70-210">For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="e1c70-211">Le dipendenze tra i pacchetti devono usare un requisito _di versione uguale o maggiore di_ .</span><span class="sxs-lookup"><span data-stu-id="e1c70-211">Dependencies between packages should use an _equal or greater than_ version requirement.</span></span> <span data-ttu-id="e1c70-212">Ad esempio, `dotnet-sdk-2.2:2.2.401` richiede `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-212">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="e1c70-213">In questo modo, l'utente può aggiornare l'installazione tramite un pacchetto radice, ad esempio `dnf update dotnet-sdk-2.2`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-213">This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="e1c70-214">Per la maggior parte delle distribuzioni è necessario che tutti gli elementi vengano compilati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="e1c70-214">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="e1c70-215">Questo ha un certo impatto sui pacchetti:</span><span class="sxs-lookup"><span data-stu-id="e1c70-215">This has some impact on the packages:</span></span>

- <span data-ttu-id="e1c70-216">Le librerie di terze parti in `shared/Microsoft.AspNetCore.All` non possono essere compilate facilmente dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e1c70-216">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="e1c70-217">Quindi la cartella viene omessa dal pacchetto `aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-217">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="e1c70-218">`NuGetFallbackFolder` viene popolato usando elementi binari da `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-218">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="e1c70-219">Deve rimanere vuoto.</span><span class="sxs-lookup"><span data-stu-id="e1c70-219">It should remain empty.</span></span>

<span data-ttu-id="e1c70-220">Più pacchetti `dotnet-sdk` possono contenere gli stessi file per `NuGetFallbackFolder`.</span><span class="sxs-lookup"><span data-stu-id="e1c70-220">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="e1c70-221">Per evitare problemi con la gestione pacchetti, questi file devono essere identici (checksum, data di modifica e così via).</span><span class="sxs-lookup"><span data-stu-id="e1c70-221">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="e1c70-222">Compilazione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="e1c70-222">Building packages</span></span>

<span data-ttu-id="e1c70-223">Il repository [dotnet/source-build](https://github.com/dotnet/source-build) contiene istruzioni su come compilare un file tarball di origine di .NET Core SDK e tutti i relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="e1c70-223">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="e1c70-224">L'output del repository di compilazione dell'origine corrisponde al layout descritto nella prima sezione di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e1c70-224">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
