---
title: Comando dotnet build - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet build consente di compilare un progetto e tutte le relative dipendenze.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: c9d1478e3d3e298b01e707242cc7ad5cd924a9b3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200554"
---
# <a name="dotnet-build"></a><span data-ttu-id="e9bac-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e9bac-103">dotnet build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e9bac-104">nome</span><span class="sxs-lookup"><span data-stu-id="e9bac-104">Name</span></span>

<span data-ttu-id="e9bac-105">`dotnet build`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="e9bac-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e9bac-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e9bac-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e9bac-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e9bac-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e9bac-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e9bac-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="e9bac-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9bac-109">Description</span></span>

<span data-ttu-id="e9bac-110">Il comando `dotnet build` compila il progetto e le relative dipendenze in un set di file binari.</span><span class="sxs-lookup"><span data-stu-id="e9bac-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="e9bac-111">I file binari includono il codice del progetto in Intermediate Language (IL) con estensione *dll* e i file di simboli usati per il debug con estensione *pdb*.</span><span class="sxs-lookup"><span data-stu-id="e9bac-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="e9bac-112">Viene generato un file JSON di dipendenze (*\*.deps.json*) con l'elenco delle dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="e9bac-113">Viene generato un file *\*.runtimeconfig.json* che specifica il runtime condiviso e la relativa versione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="e9bac-114">Se il progetto ha dipendenze di terze parti, ad esempio librerie di NuGet, queste dipendenze vengono risolte dalla cache NuGet e non sono disponibili con l'output compilato del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9bac-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="e9bac-115">Per queste ragioni, il prodotto di `dotnet build` non è pronto per essere trasferito in un altro computer per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="e9bac-116">Questo comportamento si differenzia da quello di .NET Framework in cui la compilazione di un progetto eseguibile (un'applicazione) genera un output che è possibile eseguire in qualsiasi computer in cui è installato .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9bac-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="e9bac-117">Per ottenere un'esperienza simile in .NET Core, usare il comando [dotnet publish](dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="e9bac-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="e9bac-118">Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="e9bac-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="e9bac-119">Per la compilazione è necessario il file *project.assets.json*, che elenca le dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="e9bac-120">Il file viene creato quando [`dotnet restore`](dotnet-restore.md) viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="e9bac-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="e9bac-121">Senza il file di asset sul posto, gli strumenti non sono in grado di risolvere gli assembly di riferimento, generando così errori.</span><span class="sxs-lookup"><span data-stu-id="e9bac-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="e9bac-122">Con .NET Core 1.x SDK, era necessario eseguire in modo esplicito `dotnet restore` prima di eseguire `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="e9bac-123">A partire da .NET Core 2.0 SDK, `dotnet restore` viene eseguito in modo implicito quando viene eseguito `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="e9bac-124">Se si desidera disabilitare ripristino implicito quando si esegue il comando di compilazione, è possibile passare l’opzione `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="e9bac-125">Poiché `dotnet build` usa MSBuild per compilare il progetto, sono supportate le compilazioni parallele e incrementali.</span><span class="sxs-lookup"><span data-stu-id="e9bac-125">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="e9bac-126">Per altre informazioni, vedere [Compilazioni incrementali](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="e9bac-126">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="e9bac-127">In aggiunta alle proprie opzioni, il comando `dotnet build` accetta anche le opzioni di MSBuild, ad esempio `-p` per l'impostazione delle proprietà o `-l` per la definizione di un logger.</span><span class="sxs-lookup"><span data-stu-id="e9bac-127">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="e9bac-128">Per altre informazioni su queste opzioni, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="e9bac-128">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="e9bac-129">La proprietà `<OutputType>` nel file di progetto determina se il progetto è eseguibile o meno.</span><span class="sxs-lookup"><span data-stu-id="e9bac-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="e9bac-130">L'esempio seguente descrive un progetto che produce codice eseguibile:</span><span class="sxs-lookup"><span data-stu-id="e9bac-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="e9bac-131">Per generare una libreria, omettere la proprietà `<OutputType>`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-131">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="e9bac-132">La differenza principale nell'output di compilazione è che la DLL di linguaggio intermedio per una libreria non contiene punti di ingresso e non può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="e9bac-132">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

## <a name="arguments"></a><span data-ttu-id="e9bac-133">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e9bac-133">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="e9bac-134">File di progetto o di soluzione da compilare.</span><span class="sxs-lookup"><span data-stu-id="e9bac-134">The project or solution file to build.</span></span> <span data-ttu-id="e9bac-135">Se non viene specificato alcun file di progetto o di soluzione, MSBuild cerca nella directory di lavoro corrente un file con estensione *proj* o *sln* e usa questo file.</span><span class="sxs-lookup"><span data-stu-id="e9bac-135">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="e9bac-136">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e9bac-136">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e9bac-137">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e9bac-137">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e9bac-138">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-138">Defines the build configuration.</span></span> <span data-ttu-id="e9bac-139">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-139">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e9bac-140">Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="e9bac-140">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e9bac-141">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="e9bac-141">The framework must be defined in the [project file](csproj.md).</span></span>

`--force`

<span data-ttu-id="e9bac-142">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e9bac-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="e9bac-143">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e9bac-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="e9bac-144">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e9bac-144">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="e9bac-145">Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato.</span><span class="sxs-lookup"><span data-stu-id="e9bac-145">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="e9bac-146">Contrassegna la compilazione come non sicura per la compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="e9bac-146">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="e9bac-147">Questo flag disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9bac-147">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-restore`

<span data-ttu-id="e9bac-148">Non esegue un ripristino implicito durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-148">Doesn't execute an implicit restore during build.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e9bac-149">Directory in cui inserire i file binari compilati.</span><span class="sxs-lookup"><span data-stu-id="e9bac-149">Directory in which to place the built binaries.</span></span> <span data-ttu-id="e9bac-150">È necessario definire anche `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-150">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e9bac-151">Specifica il runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-151">Specifies the target runtime.</span></span> <span data-ttu-id="e9bac-152">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e9bac-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e9bac-153">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="e9bac-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e9bac-154">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="e9bac-155">Definisce il suffisso di versione per un asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-155">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="e9bac-156">Il formato rispetta le linee guida della versione NuGet.</span><span class="sxs-lookup"><span data-stu-id="e9bac-156">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e9bac-157">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e9bac-157">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e9bac-158">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-158">Defines the build configuration.</span></span> <span data-ttu-id="e9bac-159">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-159">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e9bac-160">Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="e9bac-160">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e9bac-161">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="e9bac-161">The framework must be defined in the [project file](csproj.md).</span></span>

`-h|--help`

<span data-ttu-id="e9bac-162">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e9bac-162">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="e9bac-163">Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato.</span><span class="sxs-lookup"><span data-stu-id="e9bac-163">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="e9bac-164">Contrassegna la compilazione come non sicura per la compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="e9bac-164">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="e9bac-165">Questo flag disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="e9bac-165">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e9bac-166">Directory in cui inserire i file binari compilati.</span><span class="sxs-lookup"><span data-stu-id="e9bac-166">Directory in which to place the built binaries.</span></span> <span data-ttu-id="e9bac-167">È necessario definire anche `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-167">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e9bac-168">Specifica il runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-168">Specifies the target runtime.</span></span> <span data-ttu-id="e9bac-169">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e9bac-169">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e9bac-170">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="e9bac-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e9bac-171">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="e9bac-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="e9bac-172">Definisce il suffisso di versione per un asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="e9bac-172">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="e9bac-173">Il formato rispetta le linee guida della versione NuGet.</span><span class="sxs-lookup"><span data-stu-id="e9bac-173">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="e9bac-174">Esempi</span><span class="sxs-lookup"><span data-stu-id="e9bac-174">Examples</span></span>

<span data-ttu-id="e9bac-175">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="e9bac-175">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="e9bac-176">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="e9bac-176">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="e9bac-177">Compilare un progetto e le relative dipendenze per un runtime specifico ( in questo esempio, Ubuntu 16.04):</span><span class="sxs-lookup"><span data-stu-id="e9bac-177">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`

<span data-ttu-id="e9bac-178">Compilare il progetto e usare l'origine del pacchetto NuGet specificato durante l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="e9bac-178">Build the project and use the specified NuGet package source during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet build --source c:\packages\mypackages`