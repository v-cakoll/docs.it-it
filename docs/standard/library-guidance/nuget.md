---
title: Librerie di NuGet e .NET
description: Le procedure consigliate per la creazione di pacchetti con NuGet per librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374502"
---
# <a name="nuget"></a><span data-ttu-id="3f8ac-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="3f8ac-103">NuGet</span></span>

<span data-ttu-id="3f8ac-104">NuGet è una gestione pacchetti per l'ecosistema .NET e agli sviluppatori il modo principale individuano e acquisire le librerie open source di .NET.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="3f8ac-105">[NuGet.org](https://www.nuget.org/), un servizio gratuito fornito da Microsoft per l'hosting dei pacchetti NuGet, è l'host primario per i pacchetti NuGet pubblici, ma è possibile pubblicare in servizi di NuGet personalizzati, ad esempio [MyGet](https://www.myget.org/) e [gli artefatti di Azure ](https://azure.microsoft.com/services/devops/artifacts/).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="3f8ac-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="3f8ac-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="3f8ac-107">Creare un pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="3f8ac-107">Create a NuGet package</span></span>

<span data-ttu-id="3f8ac-108">Un pacchetto NuGet (`*.nupkg`) è un file zip che contiene gli assembly .NET e i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="3f8ac-109">Esistono due modi principali per creare un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="3f8ac-110">Il modo più recente e consigliato consiste nel creare un pacchetto da un progetto in stile SDK (file di progetto il cui contenuto viene avviato con `<Project Sdk="Microsoft.NET.Sdk">`).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="3f8ac-111">Obiettivi e gli assembly vengono aggiunti automaticamente al pacchetto e rimanente dei metadati viene aggiunto al file di MSBuild, ad esempio numero di nome e la versione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="3f8ac-112">La compilazione con il [ `dotnet pack` ](../../core/tools/dotnet-pack.md) comando output un `*.nupkg` file anziché gli assembly.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="3f8ac-113">È il modo meno recente di creazione di un pacchetto NuGet con un `*.nuspec` file e il `nuget.exe` lo strumento da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="3f8ac-114">Un file nuspec offre uno straordinario controllo ma è necessario specificare attentamente quali assembly e le destinazioni da includere nel pacchetto NuGet finale.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="3f8ac-115">È facile commette un errore o per un utente a dimenticare di aggiornare il file nuspec, quando si apportano modifiche.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="3f8ac-116">Il vantaggio di un file nuspec è consente di creare pacchetti NuGet per i framework che ancora non supportano un file di progetto basato su SDK.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="3f8ac-117">**Provare a ✔️** utilizzando un file di progetto basato su SDK per creare il pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="3f8ac-118">**Provare a ✔️** configurazione SourceLink per aggiungere metadati di controllo di origine per l'assembly e il pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="3f8ac-119">Dipendenze dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="3f8ac-119">Package dependencies</span></span>

<span data-ttu-id="3f8ac-120">Dipendenze dei pacchetti NuGet sono trattate in dettaglio nel [dipendenze](./dependencies.md) articolo.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="3f8ac-121">Metadati del pacchetto NuGet importanti</span><span class="sxs-lookup"><span data-stu-id="3f8ac-121">Important NuGet package metadata</span></span>

<span data-ttu-id="3f8ac-122">Un pacchetto NuGet supporta molte [le proprietà dei metadati](/nuget/reference/nuspec).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="3f8ac-123">Nella tabella seguente contiene i metadati di core che devono fornire tutti i progetti open source:</span><span class="sxs-lookup"><span data-stu-id="3f8ac-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="3f8ac-124">Nome della proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="3f8ac-124">MSBuild Property name</span></span>              | <span data-ttu-id="3f8ac-125">Nome del file Nuspec</span><span class="sxs-lookup"><span data-stu-id="3f8ac-125">Nuspec name</span></span>              | <span data-ttu-id="3f8ac-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f8ac-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="3f8ac-127">L'identificatore del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-127">The package identifier.</span></span> <span data-ttu-id="3f8ac-128">Un prefisso dall'identificatore può essere riservato se soddisfa le [criteri](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="3f8ac-129">Versione del pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-129">NuGet package version.</span></span> <span data-ttu-id="3f8ac-130">Per altre informazioni, vedere [versione del pacchetto NuGet](./versioning.md#nuget-package-version).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="3f8ac-131">Un titolo Converto del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-131">A human-friendly title of the package.</span></span> <span data-ttu-id="3f8ac-132">Per impostazione predefinita il `PackageId`.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="3f8ac-133">Descrizione lunga del pacchetto visualizzato nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="3f8ac-134">Elenco delimitato dalla virgola di autori di pacchetti, corrispondenti ai nomi di profilo in nuget.org.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="3f8ac-135">Elenco delimitato da spazi di tag e parole chiave che descrivono il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="3f8ac-136">I tag vengono usati durante la ricerca di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="3f8ac-137">Un URL di un'immagine da usare come icona per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="3f8ac-138">L'URL deve essere HTTPS e l'immagine deve essere di 64 x 64 e uno sfondo trasparente.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="3f8ac-139">Un URL per il repository di origine o della home page del progetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="3f8ac-140">Un URL della licenza di progetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-140">A URL to the project license.</span></span> <span data-ttu-id="3f8ac-141">Può essere l'URL per il `LICENSE` file nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="3f8ac-142">**Provare a ✔️** scegliendo un nome del pacchetto NuGet con un prefisso che soddisfi prenotazione del prefisso di NuGet [criteri](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="3f8ac-143">**✔️ si consiglia** usando il `LICENSE` file nel controllo del codice sorgente come il `LicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="3f8ac-144">Ad esempio, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f8ac-145">Un progetto senza una licenza per impostazione predefinita [copyright esclusivo](https://choosealicense.com/no-permission/), rendendo impossibile la uso ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="3f8ac-146">**Eseguire operazioni ✔️** usano un href HTTPS per l'icona del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="3f8ac-147">Siti come NuGet.org eseguano con abilitato per HTTPS e la visualizzazione di un'immagine non HTTPS creerà un avviso di contenuto misto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="3f8ac-148">**Eseguire operazioni ✔️** usare un'immagine icona pacchetto 64 x 64 e con uno sfondo trasparente per ottenere una migliore visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="3f8ac-149">Pacchetti in versione non definitiva</span><span class="sxs-lookup"><span data-stu-id="3f8ac-149">Pre-release packages</span></span>

<span data-ttu-id="3f8ac-150">I pacchetti NuGet con un suffisso di versione sono considerati [definitive](/nuget/create-packages/prerelease-packages).</span><span class="sxs-lookup"><span data-stu-id="3f8ac-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="3f8ac-151">Per impostazione predefinita, la UI Gestione pacchetti NuGet Mostra versioni stabili, a meno che un utente sceglie di versioni non definitive dei pacchetti, pacchetti di versioni non definitive le rendono ideali per i test di utente con limitazioni.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="3f8ac-152">Una stabile del pacchetto non può dipendere da un versione preliminare del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="3f8ac-153">È necessario verificare che il proprio pacchetto di versioni non definitive o dipendono da una versione stabile precedente.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="3f8ac-154">![Dipendenza del pacchetto di versioni non definitive NuGet](./media/nuget/nuget-prerelease-package.png "dipendenza versione preliminare del pacchetto NuGet")</span><span class="sxs-lookup"><span data-stu-id="3f8ac-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="3f8ac-155">**Eseguire operazioni ✔️** pubblicare un versione preliminare del pacchetto durante la verifica, la visualizzazione in anteprima o la sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="3f8ac-156">**Eseguire operazioni ✔️** pubblicare un pacchetto stabile quando pronto in modo gli altri pacchetti stabili possono farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="3f8ac-157">Pacchetti di simboli</span><span class="sxs-lookup"><span data-stu-id="3f8ac-157">Symbol packages</span></span>

<span data-ttu-id="3f8ac-158">NuGet supporta [generazione di un pacchetto di simboli separati](/nuget/create-packages/symbol-packages) contenente il debug di file PDB insieme al pacchetto principale che contiene gli assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-158">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing debug PDB files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="3f8ac-159">L'idea di pacchetti di simboli è che siano ospitate in un server di simboli e vengono scaricati solo da uno strumento come Visual Studio su richiesta.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-159">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="3f8ac-160">Attualmente l'host pubblica principale per i simboli - [SymbolSource](http://www.symbolsource.org/) -non supporta i file PDB portatili creato dallo stile di SDK progetti e pacchetti di simboli non sono utili.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-160">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the portable PDBs created by SDK-style projects and symbol packages aren't useful.</span></span>

<span data-ttu-id="3f8ac-161">**Provare a ✔️** incorporamento di PDB nel pacchetto NuGet principale.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-161">**✔️ CONSIDER** embedding PDBs in the main NuGet package.</span></span>

<span data-ttu-id="3f8ac-162">**Si consiglia di evitare ❌** creazione di un pacchetto di simboli che contiene i file PDB.</span><span class="sxs-lookup"><span data-stu-id="3f8ac-162">**❌ AVOID** creating a symbols package containing PDBs.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="3f8ac-163">[Precedente](./strong-naming.md)
[Successivo](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="3f8ac-163">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
