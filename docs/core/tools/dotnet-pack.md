---
title: Comando dotnet pack - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 12/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: ac1ff90cb97fa4802883e70b0abdf4e77b58dd65
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2017
---
# <a name="dotnet-pack"></a><span data-ttu-id="25be8-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="25be8-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="25be8-104">Nome</span><span class="sxs-lookup"><span data-stu-id="25be8-104">Name</span></span>

<span data-ttu-id="25be8-105">`dotnet pack`: comprime il codice in un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="25be8-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="25be8-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="25be8-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="25be8-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="25be8-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies] [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="25be8-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="25be8-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="25be8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25be8-109">Description</span></span>

<span data-ttu-id="25be8-110">Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="25be8-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="25be8-111">Il risultato di questo comando è un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="25be8-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="25be8-112">Se l'opzione `--include-symbols` è presente, viene creato un altro pacchetto contenente i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="25be8-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="25be8-113">Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="25be8-114">I riferimenti da progetto a progetto non sono inseriti all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="25be8-115">Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="25be8-116">Per impostazione predefinita, `dotnet pack` compila prima il progetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="25be8-117">Se si vuole evitare questo comportamento, passare l'opzione `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="25be8-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="25be8-118">Questo può essere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration), in cui si sa che il codice è stato compilato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="25be8-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="25be8-119">È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione.</span><span class="sxs-lookup"><span data-stu-id="25be8-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="25be8-120">Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild).</span><span class="sxs-lookup"><span data-stu-id="25be8-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="25be8-121">La sezione [Esempi](#examples) illustra come usare l'opzione di MSBuild /p per due diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="25be8-121">The [Examples](#examples) section shows how to use the MSBuild /p switch for a couple of different scenarios.</span></span>

## <a name="arguments"></a><span data-ttu-id="25be8-122">Argomenti</span><span class="sxs-lookup"><span data-stu-id="25be8-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="25be8-123">Progetto da comprimere.</span><span class="sxs-lookup"><span data-stu-id="25be8-123">The project to pack.</span></span> <span data-ttu-id="25be8-124">Può essere un percorso a un [file csproj](csproj.md) o a una directory.</span><span class="sxs-lookup"><span data-stu-id="25be8-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="25be8-125">Se omesso, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="25be8-125">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="25be8-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="25be8-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="25be8-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="25be8-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="25be8-128">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="25be8-128">Defines the build configuration.</span></span> <span data-ttu-id="25be8-129">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="25be8-129">The default value is `Debug`.</span></span>

<span data-ttu-id="25be8-130">`--force` Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="25be8-130">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="25be8-131">Ciò equivale a eliminare il file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="25be8-131">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="25be8-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="25be8-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="25be8-133">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="25be8-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="25be8-134">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="25be8-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="25be8-135">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="25be8-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="25be8-136">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="25be8-136">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="25be8-137">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="25be8-137">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="25be8-138">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="25be8-138">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="25be8-139">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="25be8-139">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="25be8-140">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="25be8-140">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="25be8-141">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="25be8-141">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="25be8-142">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-142">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="25be8-143">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="25be8-143">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="25be8-144">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-144">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="25be8-145">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="25be8-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="25be8-146">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="25be8-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="25be8-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="25be8-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="25be8-148">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="25be8-148">Defines the build configuration.</span></span> <span data-ttu-id="25be8-149">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="25be8-149">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="25be8-150">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="25be8-150">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="25be8-151">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="25be8-151">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="25be8-152">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="25be8-152">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="25be8-153">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="25be8-153">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="25be8-154">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="25be8-154">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="25be8-155">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="25be8-155">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="25be8-156">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-156">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="25be8-157">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="25be8-157">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="25be8-158">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="25be8-158">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="25be8-159">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="25be8-159">Sets the verbosity level of the command.</span></span> <span data-ttu-id="25be8-160">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="25be8-160">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="25be8-161">Esempi</span><span class="sxs-lookup"><span data-stu-id="25be8-161">Examples</span></span>

<span data-ttu-id="25be8-162">Comprimere il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="25be8-162">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="25be8-163">Comprimere il progetto `app1`:</span><span class="sxs-lookup"><span data-stu-id="25be8-163">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="25be8-164">Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="25be8-164">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="25be8-165">Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:</span><span class="sxs-lookup"><span data-stu-id="25be8-165">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="25be8-166">Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:</span><span class="sxs-lookup"><span data-stu-id="25be8-166">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="25be8-167">Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="25be8-167">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

<span data-ttu-id="25be8-168">Comprimere il progetto per un [framework di destinazione](../../standard/frameworks.md) specifico:</span><span class="sxs-lookup"><span data-stu-id="25be8-168">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack /p:TargetFrameworks=net45`
