---
title: Comando dotnet-pack - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-pack consente di creare pacchetti NuGet per il progetto .NET Core.
keywords: dotnet-pack, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 04b967fdf6578098caae8c21604c5d6160eb6775
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-pack"></a><span data-ttu-id="2e4ed-104">dotnet-pack</span><span class="sxs-lookup"><span data-stu-id="2e4ed-104">dotnet-pack</span></span>

## <a name="name"></a><span data-ttu-id="2e4ed-105">Nome</span><span class="sxs-lookup"><span data-stu-id="2e4ed-105">Name</span></span>

<span data-ttu-id="2e4ed-106">`dotnet-pack`: comprime il codice in un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-106">`dotnet-pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2e4ed-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2e4ed-107">Synopsis</span></span>

`dotnet pack [<PROJECT>] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix <VERSION_SUFFIX>] [-s|--serviceable] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="2e4ed-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e4ed-108">Description</span></span>

<span data-ttu-id="2e4ed-109">Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="2e4ed-110">Il risultato di questo comando è un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-110">The result of this command is a NuGet package.</span></span> <span data-ttu-id="2e4ed-111">Se l'opzione `--include-symbols` è presente, viene creato un altro pacchetto contenente i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-111">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span> 

<span data-ttu-id="2e4ed-112">Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-112">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="2e4ed-113">I riferimenti da progetto a progetto non sono inseriti all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-113">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="2e4ed-114">Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-114">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="2e4ed-115">Per impostazione predefinita, `dotnet pack` compila prima il progetto.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-115">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="2e4ed-116">Se si vuole evitare questo comportamento, passare l'opzione `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-116">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="2e4ed-117">Questo può essere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration), in cui si sa che il codice è stato compilato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-117">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="2e4ed-118">È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-118">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="2e4ed-119">Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild).</span><span class="sxs-lookup"><span data-stu-id="2e4ed-119">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="arguments"></a><span data-ttu-id="2e4ed-120">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2e4ed-120">Arguments</span></span>

`PROJECT` 
    
<span data-ttu-id="2e4ed-121">Progetto da comprimere.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-121">The project to pack.</span></span> <span data-ttu-id="2e4ed-122">Può essere un percorso a un [file csproj](csproj.md) o a una directory.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-122">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="2e4ed-123">Se omesso, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-123">If omitted, it defaults to the current directory.</span></span> 

## <a name="options"></a><span data-ttu-id="2e4ed-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2e4ed-124">Options</span></span>

`-h|--help`

<span data-ttu-id="2e4ed-125">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-125">Prints out a short help for the command.</span></span>  

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="2e4ed-126">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-126">Places the built packages in the directory specified.</span></span> 

`--no-build`

<span data-ttu-id="2e4ed-127">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-127">Don't build the project before packing.</span></span> 

`--include-symbols`

<span data-ttu-id="2e4ed-128">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-128">Generates the symbols `nupkg`.</span></span> 

`--include-source`

<span data-ttu-id="2e4ed-129">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-129">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="2e4ed-130">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-130">The sources files are included in the `src` folder within the `nupkg`.</span></span> 

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="2e4ed-131">Configurazione da usare durante la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-131">Configuration to use when building the project.</span></span> <span data-ttu-id="2e4ed-132">Se non è specificata, per impostazione predefinita viene usata `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-132">If not specified, configuration defaults to `Debug`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="2e4ed-133">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-133">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-s|--serviceable`

<span data-ttu-id="2e4ed-134">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-134">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="2e4ed-135">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="2e4ed-135">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="2e4ed-136">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-136">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2e4ed-137">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2e4ed-137">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="2e4ed-138">Esempi</span><span class="sxs-lookup"><span data-stu-id="2e4ed-138">Examples</span></span>

<span data-ttu-id="2e4ed-139">Comprimere il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="2e4ed-139">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="2e4ed-140">Comprimere il progetto `app1`:</span><span class="sxs-lookup"><span data-stu-id="2e4ed-140">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="2e4ed-141">Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="2e4ed-141">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="2e4ed-142">Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:</span><span class="sxs-lookup"><span data-stu-id="2e4ed-142">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="2e4ed-143">Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:</span><span class="sxs-lookup"><span data-stu-id="2e4ed-143">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="2e4ed-144">Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="2e4ed-144">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

