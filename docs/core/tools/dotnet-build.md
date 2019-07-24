---
title: Comando dotnet build
description: Il comando dotnet build consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 04/24/2019
ms.openlocfilehash: db2c859529d3dd21d2cd43445419b99a4256b42e
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331055"
---
# <a name="dotnet-build"></a><span data-ttu-id="cbdd7-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="cbdd7-103">dotnet build</span></span>

<span data-ttu-id="cbdd7-104">**Questo articolo si applica a: ✓** .NET Core 1.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="cbdd7-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="cbdd7-105">nome</span><span class="sxs-lookup"><span data-stu-id="cbdd7-105">Name</span></span>

<span data-ttu-id="cbdd7-106">`dotnet build`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cbdd7-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cbdd7-107">Synopsis</span></span>

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--nologo] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="cbdd7-108">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="cbdd7-108">Description</span></span>

<span data-ttu-id="cbdd7-109">Il comando `dotnet build` compila il progetto e le relative dipendenze in un set di file binari.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="cbdd7-110">I file binari includono il codice del progetto in Intermediate Language (IL) con estensione *dll* e i file di simboli usati per il debug con estensione *pdb*.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="cbdd7-111">Viene generato un file JSON di dipendenze ( *.deps.json*) con l'elenco delle dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-111">A dependencies JSON file (*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="cbdd7-112">Viene generato un file *.runtimeconfig.json* che specifica il runtime condiviso e la relativa versione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-112">A *.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="cbdd7-113">Se il progetto ha dipendenze di terze parti, ad esempio librerie di NuGet, queste dipendenze vengono risolte dalla cache NuGet e non sono disponibili con l'output compilato del progetto.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="cbdd7-114">Per queste ragioni, il prodotto di `dotnet build` non è pronto per essere trasferito in un altro computer per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="cbdd7-115">Questo comportamento si differenzia da quello di .NET Framework in cui la compilazione di un progetto eseguibile (un'applicazione) genera un output che è possibile eseguire in qualsiasi computer in cui è installato .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="cbdd7-116">Per ottenere un'esperienza simile in .NET Core, usare il comando [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-116">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="cbdd7-117">Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="cbdd7-118">Per la compilazione è necessario il file *project.assets.json*, che elenca le dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="cbdd7-119">Il file viene creato quando [`dotnet restore`](dotnet-restore.md) viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-119">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="cbdd7-120">Senza il file di asset sul posto, gli strumenti non possono risolvere gli assembly di riferimento, generando così errori.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-120">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="cbdd7-121">Con .NET Core 1.x SDK, era necessario eseguire in modo esplicito `dotnet restore` prima di eseguire `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-121">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="cbdd7-122">A partire da .NET Core 2.0 SDK, `dotnet restore` viene eseguito in modo implicito quando viene eseguito `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-122">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="cbdd7-123">Se si desidera disabilitare ripristino implicito quando si esegue il comando di compilazione, è possibile passare l’opzione `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-123">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="cbdd7-124">La proprietà `<OutputType>` nel file di progetto determina se il progetto è eseguibile o meno.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-124">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="cbdd7-125">L'esempio seguente descrive un progetto che produce codice eseguibile:</span><span class="sxs-lookup"><span data-stu-id="cbdd7-125">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="cbdd7-126">Per generare una libreria, omettere la proprietà `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-126">To produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="cbdd7-127">La differenza principale nell'output di compilazione è che la DLL di linguaggio intermedio per una libreria non contiene punti di ingresso e non può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-127">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="cbdd7-128">MSBuild</span><span class="sxs-lookup"><span data-stu-id="cbdd7-128">MSBuild</span></span>

<span data-ttu-id="cbdd7-129">Poiché `dotnet build` usa MSBuild per compilare il progetto, sono supportate le compilazioni parallele e incrementali.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-129">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="cbdd7-130">Per altre informazioni, vedere [Compilazioni incrementali](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-130">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="cbdd7-131">In aggiunta alle proprie opzioni, il comando `dotnet build` accetta anche le opzioni di MSBuild, ad esempio `-p` per l'impostazione delle proprietà o `-l` per la definizione di un logger.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-131">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="cbdd7-132">Per altre informazioni su queste opzioni, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-132">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="cbdd7-133">In alternativa è anche possibile usare il comando [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-133">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="cbdd7-134">L'esecuzione di `dotnet build` equivale a `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-134">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="cbdd7-135">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cbdd7-135">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="cbdd7-136">File di progetto o di soluzione da compilare.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-136">The project or solution file to build.</span></span> <span data-ttu-id="cbdd7-137">Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-137">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="cbdd7-138">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cbdd7-138">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="cbdd7-139">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-139">Defines the build configuration.</span></span> <span data-ttu-id="cbdd7-140">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-140">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="cbdd7-141">Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-141">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cbdd7-142">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-142">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="cbdd7-143">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="cbdd7-144">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="cbdd7-145">Disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-145">Available since .NET Core 2.0 SDK.</span></span>

* **`-h|--help`**

  <span data-ttu-id="cbdd7-146">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-146">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="cbdd7-147">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="cbdd7-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="cbdd7-148">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-148">For example, to complete authentication.</span></span> <span data-ttu-id="cbdd7-149">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-149">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="cbdd7-150">Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-150">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="cbdd7-151">Contrassegna la compilazione come non sicura per la compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-151">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="cbdd7-152">Questo flag disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-152">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-logo`**

  <span data-ttu-id="cbdd7-153">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-153">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="cbdd7-154">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-154">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-restore`**

  <span data-ttu-id="cbdd7-155">Non esegue un ripristino implicito durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-155">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="cbdd7-156">Disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-156">Available since .NET Core 2.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="cbdd7-157">Directory in cui inserire i file binari compilati.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-157">Directory in which to place the built binaries.</span></span> <span data-ttu-id="cbdd7-158">È necessario definire anche `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-158">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="cbdd7-159">Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-159">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="cbdd7-160">Specifica il runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-160">Specifies the target runtime.</span></span> <span data-ttu-id="cbdd7-161">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-161">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="cbdd7-162">Imposta il livello di dettaglio di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-162">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="cbdd7-163">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="cbdd7-164">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-164">The default is `minimal`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="cbdd7-165">Imposta il valore della proprietà `$(VersionSuffix)` da usare durante la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-165">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="cbdd7-166">Funziona solo se la proprietà `$(Version)` non è impostata.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-166">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="cbdd7-167">La proprietà `$(Version)` viene quindi impostata su `$(VersionPrefix)` combinata con `$(VersionSuffix)`, separati da un trattino.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-167">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="cbdd7-168">Esempi</span><span class="sxs-lookup"><span data-stu-id="cbdd7-168">Examples</span></span>

* <span data-ttu-id="cbdd7-169">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="cbdd7-169">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="cbdd7-170">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="cbdd7-170">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="cbdd7-171">Compilare un progetto e le relative dipendenze per un runtime specifico ( in questo esempio, Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="cbdd7-171">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.18.04-x64
  ```

* <span data-ttu-id="cbdd7-172">Compilare il progetto e usare l'origine del pacchetto NuGet specificato durante l'operazione di ripristino (.NET Core 2.0 SDK e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="cbdd7-172">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="cbdd7-173">Compilare il progetto e impostare la versione 1.2.3.4 come parametro di compilazione usando l'[opzione MSBuild](#msbuild) `-p`:</span><span class="sxs-lookup"><span data-stu-id="cbdd7-173">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```
