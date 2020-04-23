---
title: Comando dotnet pack
description: Il comando dotnet pack consente di creare pacchetti NuGet per il progetto .NET Core.
ms.date: 02/14/2020
ms.openlocfilehash: 2df096a088a177b77256b5d717f31e185507b249
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102814"
---
# <a name="dotnet-pack"></a><span data-ttu-id="299e7-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="299e7-103">dotnet pack</span></span>

<span data-ttu-id="299e7-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="299e7-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="299e7-105">Nome</span><span class="sxs-lookup"><span data-stu-id="299e7-105">Name</span></span>

<span data-ttu-id="299e7-106">`dotnet pack`: comprime il codice in un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="299e7-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="299e7-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="299e7-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a><span data-ttu-id="299e7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="299e7-108">Description</span></span>

<span data-ttu-id="299e7-109">Il comando `dotnet pack` consente di compilare il progetto e creare pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="299e7-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="299e7-110">Il risultato di questo comando è un pacchetto NuGet, ovvero un file *con estensione nupkg.*</span><span class="sxs-lookup"><span data-stu-id="299e7-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span>

<span data-ttu-id="299e7-111">Se si desidera generare un pacchetto che contiene i simboli di debug, sono disponibili due opzioni:If you want to generate a package that contains the debug symbols, you have two options available:</span><span class="sxs-lookup"><span data-stu-id="299e7-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="299e7-112">`--include-symbols`- crea il pacchetto simboli.</span><span class="sxs-lookup"><span data-stu-id="299e7-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="299e7-113">`--include-source`- crea il pacchetto `src` di simboli con una cartella all'interno contenente i file di origine.</span><span class="sxs-lookup"><span data-stu-id="299e7-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="299e7-114">Le dipendenze NuGet del progetto compresso vengono aggiunte al file con estensione *nuspec*, in modo da poter essere risolte durante l'installazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="299e7-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="299e7-115">I riferimenti da progetto a progetto non sono inseriti all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="299e7-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="299e7-116">Attualmente è necessario disporre di un pacchetto per ogni progetto se sono presenti dipendenze da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="299e7-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="299e7-117">Per impostazione predefinita, `dotnet pack` compila prima il progetto.</span><span class="sxs-lookup"><span data-stu-id="299e7-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="299e7-118">Se si vuole evitare questo comportamento, passare l'opzione `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="299e7-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="299e7-119">Questa opzione è in genere utile negli scenari di compilazione di integrazione continua (CI, Continuous Integration) in cui si sa che il codice è stato compilato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="299e7-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

> [!NOTE]
> <span data-ttu-id="299e7-120">In alcuni casi, la compilazione implicita non può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="299e7-120">In some cases, the implicit build cannot be performed.</span></span> <span data-ttu-id="299e7-121">Ciò può `GeneratePackageOnBuild` verificarsi quando è impostato, per evitare una dipendenza ciclica tra le destinazioni di compilazione e di gruppo.</span><span class="sxs-lookup"><span data-stu-id="299e7-121">This can occur when `GeneratePackageOnBuild` is set, to avoid a cyclic dependency between build and pack targets.</span></span> <span data-ttu-id="299e7-122">La compilazione può anche avere esito negativo se è presente un file bloccato o un altro problema.</span><span class="sxs-lookup"><span data-stu-id="299e7-122">The build can also fail if there is a locked file or other issue.</span></span>

<span data-ttu-id="299e7-123">È possibile aggiungere proprietà MSBuild al comando `dotnet pack` per il processo di compressione.</span><span class="sxs-lookup"><span data-stu-id="299e7-123">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="299e7-124">Per altre informazioni, vedere [NuGet metadata properties](csproj.md#nuget-metadata-properties) (Proprietà dei metadati NuGet) e [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) (Informazioni di riferimento sulla riga di comando di MSBuild).</span><span class="sxs-lookup"><span data-stu-id="299e7-124">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="299e7-125">La sezione [Esempi](#examples) illustra come usare l'opzione di MSBuild -p per due diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="299e7-125">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="299e7-126">Per impostazione predefinita, non è possibile creare un pacchetto dei progetti Web.</span><span class="sxs-lookup"><span data-stu-id="299e7-126">Web projects aren't packable by default.</span></span> <span data-ttu-id="299e7-127">Per eseguire l'override del comportamento predefinito, aggiungere la proprietà seguente al file con estensione *csproj*:</span><span class="sxs-lookup"><span data-stu-id="299e7-127">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a><span data-ttu-id="299e7-128">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="299e7-128">Implicit restore</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="299e7-129">Argomenti</span><span class="sxs-lookup"><span data-stu-id="299e7-129">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="299e7-130">Progetto o soluzione da comprimere.</span><span class="sxs-lookup"><span data-stu-id="299e7-130">The project or solution to pack.</span></span> <span data-ttu-id="299e7-131">Si tratta di un percorso a un [file csproj](csproj.md), un file di soluzione o una directory.</span><span class="sxs-lookup"><span data-stu-id="299e7-131">It's either a path to a [csproj file](csproj.md), a solution file, or to a directory.</span></span> <span data-ttu-id="299e7-132">Se non specificato, il comando cerca nella directory corrente un file di progetto o di soluzione.</span><span class="sxs-lookup"><span data-stu-id="299e7-132">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="299e7-133">Opzioni</span><span class="sxs-lookup"><span data-stu-id="299e7-133">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="299e7-134">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="299e7-134">Defines the build configuration.</span></span> <span data-ttu-id="299e7-135">L'impostazione predefinita `Debug`per la maggior parte dei progetti è , ma è possibile eseguire l'override delle impostazioni di configurazione della compilazione nel progetto.</span><span class="sxs-lookup"><span data-stu-id="299e7-135">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`--force`**

  <span data-ttu-id="299e7-136">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="299e7-136">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="299e7-137">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="299e7-137">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="299e7-138">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="299e7-138">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="299e7-139">Include i simboli di debug NuGet pacchetti oltre ai normali pacchetti NuGet nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="299e7-139">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="299e7-140">I file di origine `src` sono inclusi nella cartella all'interno del pacchetto di simboli.</span><span class="sxs-lookup"><span data-stu-id="299e7-140">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="299e7-141">Include i simboli di debug NuGet pacchetti oltre ai normali pacchetti NuGet nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="299e7-141">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="299e7-142">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="299e7-142">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="299e7-143">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="299e7-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="299e7-144">Non compila il progetto prima della compressione.</span><span class="sxs-lookup"><span data-stu-id="299e7-144">Doesn't build the project before packing.</span></span> <span data-ttu-id="299e7-145">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="299e7-145">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="299e7-146">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="299e7-146">Ignores project-to-project references and only restores the root project.</span></span>

- **`--no-restore`**

  <span data-ttu-id="299e7-147">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="299e7-147">Doesn't execute an implicit restore when running the command.</span></span>

- **`--nologo`**

  <span data-ttu-id="299e7-148">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="299e7-148">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="299e7-149">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="299e7-149">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="299e7-150">Inserisce i pacchetti compilati nella directory specificata.</span><span class="sxs-lookup"><span data-stu-id="299e7-150">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="299e7-151">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="299e7-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="299e7-152">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="299e7-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="299e7-153">Imposta il flag utilizzabile dai servizi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="299e7-153">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="299e7-154">Per altre informazioni, vedere [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog .NET: .NET 4.5.1 supporta gli aggiornamenti della sicurezza Microsoft per le librerie NuGet di .NET).</span><span class="sxs-lookup"><span data-stu-id="299e7-154">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="299e7-155">Definisce il valore della proprietà MSBuild `$(VersionSuffix)` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="299e7-155">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="299e7-156">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="299e7-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="299e7-157">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="299e7-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="299e7-158">Esempi</span><span class="sxs-lookup"><span data-stu-id="299e7-158">Examples</span></span>

- <span data-ttu-id="299e7-159">Comprimere il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="299e7-159">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="299e7-160">Comprimere il progetto `app1`:</span><span class="sxs-lookup"><span data-stu-id="299e7-160">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="299e7-161">Comprimere il progetto nella directory corrente e inserire i pacchetti risultanti nella cartella `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="299e7-161">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="299e7-162">Comprimere il progetto nella directory corrente e inserirlo nella cartella `nupkgs`, ignorando il passaggio relativo alla compilazione:</span><span class="sxs-lookup"><span data-stu-id="299e7-162">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="299e7-163">Con il suffisso della versione del progetto configurato come `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` nel file con estensione *csproj*, comprimere il progetto corrente e aggiornare la versione del pacchetto risultante con il suffisso specificato:</span><span class="sxs-lookup"><span data-stu-id="299e7-163">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="299e7-164">Impostare la versione del pacchetto su `2.1.0` con la proprietà MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="299e7-164">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="299e7-165">Comprimere il progetto per un [framework di destinazione](../../standard/frameworks.md) specifico:</span><span class="sxs-lookup"><span data-stu-id="299e7-165">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="299e7-166">Comprimere il progetto e usare un runtime specifico (Windows 10) per l'operazione di ripristino:Pack the project and use a specific runtime (Windows 10) for the restore operation:</span><span class="sxs-lookup"><span data-stu-id="299e7-166">Pack the project and use a specific runtime (Windows 10) for the restore operation:</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="299e7-167">Comprimere il progetto usando un [file con estensione nuspec](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span><span class="sxs-lookup"><span data-stu-id="299e7-167">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
