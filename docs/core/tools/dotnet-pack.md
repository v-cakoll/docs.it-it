---
title: Comando dotnet pack
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
ms.date: 12/04/2018
ms.openlocfilehash: c5c00f3bb06e5bc5579c0d3d6bdd39fbdf3db656
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202846"
---
# <a name="dotnet-pack"></a><span data-ttu-id="5d4d2-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="5d4d2-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5d4d2-104">nome</span><span class="sxs-lookup"><span data-stu-id="5d4d2-104">Name</span></span>

<span data-ttu-id="5d4d2-105">`dotnet pack`: comprime il codice in un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5d4d2-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5d4d2-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5d4d2-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5d4d2-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5d4d2-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5d4d2-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="5d4d2-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5d4d2-109">Description</span></span>

<span data-ttu-id="5d4d2-110">Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="5d4d2-111">Il risultato di questo comando è un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="5d4d2-112">Se l'opzione `--include-symbols` è presente, viene creato un altro pacchetto contenente i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="5d4d2-113">Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="5d4d2-114">I riferimenti da progetto a progetto non sono inseriti all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="5d4d2-115">Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="5d4d2-116">Per impostazione predefinita, `dotnet pack` compila prima il progetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="5d4d2-117">Se si vuole evitare questo comportamento, passare l'opzione `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="5d4d2-118">Questa opzione è in genere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration) in cui si sa che il codice è stato compilato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="5d4d2-119">È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="5d4d2-120">Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild).</span><span class="sxs-lookup"><span data-stu-id="5d4d2-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="5d4d2-121">La sezione [Esempi](#examples) illustra come usare l'opzione di MSBuild -p per due diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-121">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="5d4d2-122">Per impostazione predefinita, non è possibile creare un pacchetto dei progetti Web.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-122">Web projects aren't packable by default.</span></span> <span data-ttu-id="5d4d2-123">Per eseguire l'override del comportamento predefinito, aggiungere la proprietà seguente al file con estensione *csproj*:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-123">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="5d4d2-124">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5d4d2-124">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="5d4d2-125">Progetto da comprimere.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-125">The project to pack.</span></span> <span data-ttu-id="5d4d2-126">Può essere un percorso a un [file csproj](csproj.md) o a una directory.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-126">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="5d4d2-127">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-127">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="5d4d2-128">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5d4d2-128">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5d4d2-129">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5d4d2-129">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="5d4d2-130">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-130">Defines the build configuration.</span></span> <span data-ttu-id="5d4d2-131">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-131">The default value is `Debug`.</span></span>

* **`--force`**

  <span data-ttu-id="5d4d2-132">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="5d4d2-133">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="5d4d2-134">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-134">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="5d4d2-135">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-135">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="5d4d2-136">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-136">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="5d4d2-137">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-137">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="5d4d2-138">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-138">Doesn't build the project before packing.</span></span> <span data-ttu-id="5d4d2-139">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-139">It also implicitly sets the `--no-restore` flag.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="5d4d2-140">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-140">Ignores project-to-project references and only restores the root project.</span></span>

* **`--no-restore`**

  <span data-ttu-id="5d4d2-141">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-141">Doesn't execute an implicit restore when running the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="5d4d2-142">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-142">Places the built packages in the directory specified.</span></span>

* **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="5d4d2-143">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-143">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="5d4d2-144">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="5d4d2-144">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="5d4d2-145">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-145">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="5d4d2-146">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="5d4d2-146">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="5d4d2-147">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-147">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5d4d2-148">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5d4d2-149">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5d4d2-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5d4d2-150">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="5d4d2-151">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-151">Defines the build configuration.</span></span> <span data-ttu-id="5d4d2-152">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-152">The default value is `Debug`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="5d4d2-153">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-153">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="5d4d2-154">Include i file di origine nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-154">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="5d4d2-155">I file di origine sono inclusi nella cartella `src` del pacchetto `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-155">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="5d4d2-156">Genera i simboli `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-156">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="5d4d2-157">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-157">Doesn't build the project before packing.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="5d4d2-158">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-158">Places the built packages in the directory specified.</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="5d4d2-159">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-159">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="5d4d2-160">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="5d4d2-160">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="5d4d2-161">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-161">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="5d4d2-162">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5d4d2-163">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="5d4d2-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="5d4d2-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="5d4d2-164">Examples</span></span>

* <span data-ttu-id="5d4d2-165">Comprimere il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-165">Pack the project in the current directory:</span></span>

  ```console
  dotnet pack
  ```

* <span data-ttu-id="5d4d2-166">Comprimere il progetto `app1`:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-166">Pack the `app1` project:</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj
  ```

* <span data-ttu-id="5d4d2-167">Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-167">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```console
  dotnet pack --output nupkgs
  ```

* <span data-ttu-id="5d4d2-168">Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-168">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```console
  dotnet pack --no-build --output nupkgs
  ```

* <span data-ttu-id="5d4d2-169">Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-169">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```console
  dotnet pack --version-suffix "ci-1234"
  ```

* <span data-ttu-id="5d4d2-170">Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-170">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```console
  dotnet pack -p:PackageVersion=2.1.0
  ```

* <span data-ttu-id="5d4d2-171">Comprimere il progetto per un [framework di destinazione](../../standard/frameworks.md) specifico:</span><span class="sxs-lookup"><span data-stu-id="5d4d2-171">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```console
  dotnet pack -p:TargetFrameworks=net45
  ```

* <span data-ttu-id="5d4d2-172">Comprimere il progetto e usare un runtime specifico (Windows 10) per l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="5d4d2-172">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```console
  dotnet pack --runtime win10-x64
  ```

* <span data-ttu-id="5d4d2-173">Comprimere il progetto usando un [file con estensione nuspec](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span><span class="sxs-lookup"><span data-stu-id="5d4d2-173">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj /p:NuspecFile=~/projects/app1/project.nuspec /p:NuspecBasePath=~/projects/app1/nuget
  ```
