---
title: Comando dotnet pack
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
ms.date: 12/04/2018
ms.openlocfilehash: 4b665140f7c660c5851fb68b07ecec2d9391b925
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "58464476"
---
# <a name="dotnet-pack"></a><span data-ttu-id="90c7e-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="90c7e-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="90c7e-104">nome</span><span class="sxs-lookup"><span data-stu-id="90c7e-104">Name</span></span>

<span data-ttu-id="90c7e-105">`dotnet pack`: comprime il codice in un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="90c7e-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="90c7e-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="90c7e-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="90c7e-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="90c7e-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="90c7e-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="90c7e-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="90c7e-109">Description</span><span class="sxs-lookup"><span data-stu-id="90c7e-109">Description</span></span>

<span data-ttu-id="90c7e-110">Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="90c7e-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="90c7e-111">Il risultato di questo comando è un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="90c7e-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="90c7e-112">Se l'opzione `--include-symbols` è presente, viene creato un altro pacchetto contenente i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="90c7e-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="90c7e-113">Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="90c7e-114">I riferimenti da progetto a progetto non sono inseriti all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="90c7e-115">Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="90c7e-116">Per impostazione predefinita, `dotnet pack` compila prima il progetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="90c7e-117">Se si vuole evitare questo comportamento, passare l'opzione `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="90c7e-118">Questa opzione è in genere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration) in cui si sa che il codice è stato compilato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="90c7e-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="90c7e-119">È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione.</span><span class="sxs-lookup"><span data-stu-id="90c7e-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="90c7e-120">Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild).</span><span class="sxs-lookup"><span data-stu-id="90c7e-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="90c7e-121">La sezione [Esempi](#examples) illustra come usare l'opzione di MSBuild -p per due diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="90c7e-121">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="90c7e-122">Argomenti</span><span class="sxs-lookup"><span data-stu-id="90c7e-122">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="90c7e-123">Progetto da comprimere.</span><span class="sxs-lookup"><span data-stu-id="90c7e-123">The project to pack.</span></span> <span data-ttu-id="90c7e-124">Può essere un percorso a un [file csproj](csproj.md) o a una directory.</span><span class="sxs-lookup"><span data-stu-id="90c7e-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="90c7e-125">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="90c7e-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="90c7e-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="90c7e-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="90c7e-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="90c7e-127">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="90c7e-128">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="90c7e-128">Defines the build configuration.</span></span> <span data-ttu-id="90c7e-129">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-129">The default value is `Debug`.</span></span>

* **`--force`**

  <span data-ttu-id="90c7e-130">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="90c7e-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="90c7e-131">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="90c7e-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="90c7e-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="90c7e-132">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="90c7e-133">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="90c7e-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="90c7e-134">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="90c7e-135">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-135">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="90c7e-136">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="90c7e-136">Doesn't build the project before packing.</span></span> <span data-ttu-id="90c7e-137">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-137">It also implicitly sets the `--no-restore` flag.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="90c7e-138">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="90c7e-138">Ignores project-to-project references and only restores the root project.</span></span>

* **`--no-restore`**

  <span data-ttu-id="90c7e-139">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="90c7e-139">Doesn't execute an implicit restore when running the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="90c7e-140">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="90c7e-140">Places the built packages in the directory specified.</span></span>

* **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="90c7e-141">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="90c7e-141">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="90c7e-142">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="90c7e-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="90c7e-143">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-143">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="90c7e-144">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="90c7e-144">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="90c7e-145">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-145">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="90c7e-146">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="90c7e-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="90c7e-147">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

> [!NOTE]
> <span data-ttu-id="90c7e-148">Per impostazione predefinita, non è possibile creare un pacchetto dei progetti Web.</span><span class="sxs-lookup"><span data-stu-id="90c7e-148">Web projects aren't packable by default.</span></span> <span data-ttu-id="90c7e-149">Per eseguire l'override del comportamento predefinito, aggiungere la proprietà seguente al file con estensione *csproj*:</span><span class="sxs-lookup"><span data-stu-id="90c7e-149">To override the default behavior, add the following property to your *.csproj* file:</span></span>
> ```xml
> <PropertyGroup>
>    <IsPackable>true</IsPackable>
> </PropertyGroup>
> ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="90c7e-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="90c7e-150">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="90c7e-151">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="90c7e-151">Defines the build configuration.</span></span> <span data-ttu-id="90c7e-152">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-152">The default value is `Debug`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="90c7e-153">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="90c7e-153">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="90c7e-154">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="90c7e-154">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="90c7e-155">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-155">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="90c7e-156">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-156">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="90c7e-157">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="90c7e-157">Doesn't build the project before packing.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="90c7e-158">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="90c7e-158">Places the built packages in the directory specified.</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="90c7e-159">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-159">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="90c7e-160">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="90c7e-160">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="90c7e-161">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="90c7e-161">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="90c7e-162">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="90c7e-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="90c7e-163">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="90c7e-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="90c7e-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="90c7e-164">Examples</span></span>

* <span data-ttu-id="90c7e-165">Comprimere il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="90c7e-165">Pack the project in the current directory:</span></span>

  ```console
  dotnet pack
  ```

* <span data-ttu-id="90c7e-166">Comprimere il progetto `app1`:</span><span class="sxs-lookup"><span data-stu-id="90c7e-166">Pack the `app1` project:</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj
  ```

* <span data-ttu-id="90c7e-167">Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="90c7e-167">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```console
  dotnet pack --output nupkgs
  ```

* <span data-ttu-id="90c7e-168">Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:</span><span class="sxs-lookup"><span data-stu-id="90c7e-168">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```console
  dotnet pack --no-build --output nupkgs
  ```

* <span data-ttu-id="90c7e-169">Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:</span><span class="sxs-lookup"><span data-stu-id="90c7e-169">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```console
  dotnet pack --version-suffix "ci-1234"
  ```

* <span data-ttu-id="90c7e-170">Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="90c7e-170">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```console
  dotnet pack -p:PackageVersion=2.1.0
  ```

* <span data-ttu-id="90c7e-171">Comprimere il progetto per un [framework di destinazione](../../standard/frameworks.md) specifico:</span><span class="sxs-lookup"><span data-stu-id="90c7e-171">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```console
  dotnet pack -p:TargetFrameworks=net45
  ```

* <span data-ttu-id="90c7e-172">Comprimere il progetto e usare un runtime specifico (Windows 10) per l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="90c7e-172">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```console
  dotnet pack --runtime win10-x64
  ```

* <span data-ttu-id="90c7e-173">Comprimere il progetto usando un [file con estensione nuspec](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span><span class="sxs-lookup"><span data-stu-id="90c7e-173">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```console
  dotnet pack  ~/projects/app1/project.csproj /p:NuspecFile=~/projects/app1/project.nuspec /p:NuspecBasePath=~/projects/app1/nuget
  ```
