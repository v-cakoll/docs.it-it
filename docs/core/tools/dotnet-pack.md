---
title: Comando dotnet pack - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 8594c863d67baf0237b63e61f28ca9ee315eeddf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-pack"></a><span data-ttu-id="af26e-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="af26e-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="af26e-104">Nome</span><span class="sxs-lookup"><span data-stu-id="af26e-104">Name</span></span>

<span data-ttu-id="af26e-105">`dotnet pack`: comprime il codice in un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="af26e-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="af26e-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="af26e-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="af26e-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="af26e-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies] [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af26e-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af26e-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="af26e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af26e-109">Description</span></span>

<span data-ttu-id="af26e-110">Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="af26e-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="af26e-111">Il risultato di questo comando è un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="af26e-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="af26e-112">Se l'opzione `--include-symbols` è presente, viene creato un altro pacchetto contenente i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="af26e-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="af26e-113">Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="af26e-114">I riferimenti da progetto a progetto non sono inseriti all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="af26e-115">Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="af26e-116">Per impostazione predefinita, `dotnet pack` compila prima il progetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="af26e-117">Se si vuole evitare questo comportamento, passare l'opzione `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="af26e-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="af26e-118">Questo può essere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration), in cui si sa che il codice è stato compilato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="af26e-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="af26e-119">È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione.</span><span class="sxs-lookup"><span data-stu-id="af26e-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="af26e-120">Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild).</span><span class="sxs-lookup"><span data-stu-id="af26e-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="arguments"></a><span data-ttu-id="af26e-121">Argomenti</span><span class="sxs-lookup"><span data-stu-id="af26e-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="af26e-122">Progetto da comprimere.</span><span class="sxs-lookup"><span data-stu-id="af26e-122">The project to pack.</span></span> <span data-ttu-id="af26e-123">Può essere un percorso a un [file csproj](csproj.md) o a una directory.</span><span class="sxs-lookup"><span data-stu-id="af26e-123">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="af26e-124">Se omesso, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="af26e-124">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="af26e-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="af26e-125">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="af26e-126">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="af26e-126">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="af26e-127">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="af26e-127">Defines the build configuration.</span></span> <span data-ttu-id="af26e-128">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="af26e-128">The default value is `Debug`.</span></span>

<span data-ttu-id="af26e-129">`--force` Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="af26e-129">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="af26e-130">Ciò equivale a eliminare il file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="af26e-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="af26e-131">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="af26e-131">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="af26e-132">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="af26e-132">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="af26e-133">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="af26e-133">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="af26e-134">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="af26e-134">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="af26e-135">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="af26e-135">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="af26e-136">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="af26e-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="af26e-137">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="af26e-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="af26e-138">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="af26e-138">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="af26e-139">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="af26e-139">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="af26e-140">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="af26e-140">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="af26e-141">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-141">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="af26e-142">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="af26e-142">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="af26e-143">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-143">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="af26e-144">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="af26e-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="af26e-145">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="af26e-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af26e-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af26e-146">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="af26e-147">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="af26e-147">Defines the build configuration.</span></span> <span data-ttu-id="af26e-148">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="af26e-148">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="af26e-149">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="af26e-149">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="af26e-150">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="af26e-150">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="af26e-151">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="af26e-151">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="af26e-152">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="af26e-152">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="af26e-153">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="af26e-153">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="af26e-154">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="af26e-154">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="af26e-155">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-155">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="af26e-156">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="af26e-156">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="af26e-157">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="af26e-157">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="af26e-158">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="af26e-158">Sets the verbosity level of the command.</span></span> <span data-ttu-id="af26e-159">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="af26e-159">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="af26e-160">Esempi</span><span class="sxs-lookup"><span data-stu-id="af26e-160">Examples</span></span>

<span data-ttu-id="af26e-161">Comprimere il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="af26e-161">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="af26e-162">Comprimere il progetto `app1`:</span><span class="sxs-lookup"><span data-stu-id="af26e-162">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="af26e-163">Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="af26e-163">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="af26e-164">Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:</span><span class="sxs-lookup"><span data-stu-id="af26e-164">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="af26e-165">Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:</span><span class="sxs-lookup"><span data-stu-id="af26e-165">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="af26e-166">Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="af26e-166">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`
