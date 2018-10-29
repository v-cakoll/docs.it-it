---
title: Comando dotnet pack - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 434f1c97af24d1417cd79edd52b63814fd4c6512
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48840472"
---
# <a name="dotnet-pack"></a><span data-ttu-id="55cc5-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="55cc5-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="55cc5-104">nome</span><span class="sxs-lookup"><span data-stu-id="55cc5-104">Name</span></span>

<span data-ttu-id="55cc5-105">`dotnet pack`: comprime il codice in un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="55cc5-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="55cc5-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="55cc5-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="55cc5-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="55cc5-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="55cc5-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="55cc5-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="55cc5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55cc5-109">Description</span></span>

<span data-ttu-id="55cc5-110">Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="55cc5-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="55cc5-111">Il risultato di questo comando è un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="55cc5-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="55cc5-112">Se l'opzione `--include-symbols` è presente, viene creato un altro pacchetto contenente i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="55cc5-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="55cc5-113">Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="55cc5-114">I riferimenti da progetto a progetto non sono inseriti all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="55cc5-115">Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="55cc5-116">Per impostazione predefinita, `dotnet pack` compila prima il progetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="55cc5-117">Se si vuole evitare questo comportamento, passare l'opzione `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="55cc5-118">Questa opzione è in genere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration) in cui si sa che il codice è stato compilato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="55cc5-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="55cc5-119">È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione.</span><span class="sxs-lookup"><span data-stu-id="55cc5-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="55cc5-120">Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild).</span><span class="sxs-lookup"><span data-stu-id="55cc5-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="55cc5-121">La sezione [Esempi](#examples) illustra come usare l'opzione di MSBuild -p per due diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="55cc5-121">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="55cc5-122">Argomenti</span><span class="sxs-lookup"><span data-stu-id="55cc5-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="55cc5-123">Progetto da comprimere.</span><span class="sxs-lookup"><span data-stu-id="55cc5-123">The project to pack.</span></span> <span data-ttu-id="55cc5-124">Può essere un percorso a un [file csproj](csproj.md) o a una directory.</span><span class="sxs-lookup"><span data-stu-id="55cc5-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="55cc5-125">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="55cc5-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="55cc5-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="55cc5-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="55cc5-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="55cc5-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="55cc5-128">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="55cc5-128">Defines the build configuration.</span></span> <span data-ttu-id="55cc5-129">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-129">The default value is `Debug`.</span></span>

`--force`

<span data-ttu-id="55cc5-130">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="55cc5-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="55cc5-131">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="55cc5-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="55cc5-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="55cc5-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="55cc5-133">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="55cc5-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="55cc5-134">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="55cc5-135">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="55cc5-136">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="55cc5-136">Doesn't build the project before packing.</span></span> <span data-ttu-id="55cc5-137">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="55cc5-138">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="55cc5-138">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="55cc5-139">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="55cc5-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="55cc5-140">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="55cc5-140">Places the built packages in the directory specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="55cc5-141">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="55cc5-141">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="55cc5-142">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="55cc5-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="55cc5-143">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-143">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="55cc5-144">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="55cc5-144">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="55cc5-145">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-145">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="55cc5-146">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="55cc5-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="55cc5-147">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

> [!NOTE]
> <span data-ttu-id="55cc5-148">Per impostazione predefinita, non è possibile creare un pacchetto dei progetti Web.</span><span class="sxs-lookup"><span data-stu-id="55cc5-148">Web projects aren't packable by default.</span></span> <span data-ttu-id="55cc5-149">Per eseguire l'override del comportamento predefinito, aggiungere la proprietà seguente al file con estensione *csproj*:</span><span class="sxs-lookup"><span data-stu-id="55cc5-149">To override the default behavior, add the following property to your *.csproj* file:</span></span>
> ```xml
> <PropertyGroup>
>    <IsPackable>true</IsPackable>
> </PropertyGroup>
> ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="55cc5-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="55cc5-150">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="55cc5-151">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="55cc5-151">Defines the build configuration.</span></span> <span data-ttu-id="55cc5-152">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-152">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="55cc5-153">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="55cc5-153">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="55cc5-154">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="55cc5-154">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="55cc5-155">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-155">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="55cc5-156">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-156">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="55cc5-157">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="55cc5-157">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="55cc5-158">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="55cc5-158">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="55cc5-159">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-159">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="55cc5-160">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="55cc5-160">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="55cc5-161">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="55cc5-161">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="55cc5-162">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="55cc5-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="55cc5-163">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="55cc5-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="55cc5-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="55cc5-164">Examples</span></span>

<span data-ttu-id="55cc5-165">Comprimere il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="55cc5-165">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="55cc5-166">Comprimere il progetto `app1`:</span><span class="sxs-lookup"><span data-stu-id="55cc5-166">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`

<span data-ttu-id="55cc5-167">Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="55cc5-167">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="55cc5-168">Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:</span><span class="sxs-lookup"><span data-stu-id="55cc5-168">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="55cc5-169">Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:</span><span class="sxs-lookup"><span data-stu-id="55cc5-169">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="55cc5-170">Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="55cc5-170">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack -p:PackageVersion=2.1.0`

<span data-ttu-id="55cc5-171">Comprimere il progetto per un [framework di destinazione](../../standard/frameworks.md) specifico:</span><span class="sxs-lookup"><span data-stu-id="55cc5-171">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack -p:TargetFrameworks=net45`

<span data-ttu-id="55cc5-172">Comprimere il progetto e usare un runtime specifico (Windows 10) per l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="55cc5-172">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet pack --runtime win10-x64`
