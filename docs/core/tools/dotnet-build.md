---
title: Comando dotnet build
description: Il comando dotnet build consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 02/14/2020
ms.openlocfilehash: 9f9a78ec0a6a25c54c8a727c05081ce6835514ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503770"
---
# <a name="dotnet-build"></a><span data-ttu-id="c3f8e-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c3f8e-103">dotnet build</span></span>

<span data-ttu-id="c3f8e-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="c3f8e-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c3f8e-105">Nome</span><span class="sxs-lookup"><span data-stu-id="c3f8e-105">Name</span></span>

<span data-ttu-id="c3f8e-106">`dotnet build`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c3f8e-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c3f8e-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force]
    [--interactive] [--no-dependencies] [--no-incremental] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c3f8e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3f8e-108">Description</span></span>

<span data-ttu-id="c3f8e-109">Il comando `dotnet build` compila il progetto e le relative dipendenze in un set di file binari.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="c3f8e-110">I file binari includono il codice del progetto nei file IL (Intermediate Language) con estensione *dll.*</span><span class="sxs-lookup"><span data-stu-id="c3f8e-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension.</span></span>  <span data-ttu-id="c3f8e-111">A seconda del tipo di progetto e delle impostazioni, possono essere inclusi altri file, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3f8e-111">Depending on the project type and settings, other files may be included, such as:</span></span>

- <span data-ttu-id="c3f8e-112">Un eseguibile che può essere utilizzato per eseguire l'applicazione, se il tipo di progetto è un eseguibile destinato a .NET Core 3.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-112">An executable that can be used to run the application, if the project type is an executable targeting .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="c3f8e-113">File di simboli utilizzati per il debug con estensione *pdb.*</span><span class="sxs-lookup"><span data-stu-id="c3f8e-113">Symbol files used for debugging with a *.pdb* extension.</span></span>
- <span data-ttu-id="c3f8e-114">Un file *.deps.json,* che elenca le dipendenze dell'applicazione o della libreria.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-114">A *.deps.json* file, which lists the dependencies of the application or library.</span></span>
- <span data-ttu-id="c3f8e-115">Un file *.runtimeconfig.json,* che specifica il runtime condiviso e la relativa versione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-115">A *.runtimeconfig.json* file, which specifies the shared runtime and its version for an application.</span></span>
- <span data-ttu-id="c3f8e-116">Altre librerie da cui dipende il progetto (tramite riferimenti al progetto o riferimenti al pacchetto NuGet).</span><span class="sxs-lookup"><span data-stu-id="c3f8e-116">Other libraries that the project depends on (via project references or NuGet package references).</span></span>

<span data-ttu-id="c3f8e-117">Per i progetti eseguibili destinati a versioni precedenti a .NET Core 3.0, le dipendenze della libreria da NuGet non vengono in genere copiate nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-117">For executable projects targeting versions earlier than .NET Core 3.0, library dependencies from NuGet are typically NOT copied to the output folder.</span></span>  <span data-ttu-id="c3f8e-118">Vengono risolti dalla cartella dei pacchetti globali NuGet in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-118">They're resolved from the NuGet global packages folder at run time.</span></span> <span data-ttu-id="c3f8e-119">Per queste ragioni, il prodotto di `dotnet build` non è pronto per essere trasferito in un altro computer per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-119">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="c3f8e-120">Per creare una versione dell'applicazione che può essere distribuita, è necessario pubblicarla, ad esempio con il comando [dotnet publish.](dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="c3f8e-120">To create a version of the application that can be deployed, you need to publish it (for example, with the [dotnet publish](dotnet-publish.md) command).</span></span> <span data-ttu-id="c3f8e-121">Per ulteriori informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c3f8e-121">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="c3f8e-122">Per i progetti eseguibili destinati a .NET Core 3.0 e versioni successive, le dipendenze della libreria vengono copiate nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-122">For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.</span></span> <span data-ttu-id="c3f8e-123">Ciò significa che se non sono presenti altre logiche specifiche della pubblicazione (ad esempio i progetti Web), l'output di compilazione deve essere distribuibile.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-123">This means that if there isn't any other publish-specific logic (such as Web projects have), the build output should be deployable.</span></span>

<span data-ttu-id="c3f8e-124">Per la compilazione è necessario il file *project.assets.json*, che elenca le dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-124">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="c3f8e-125">Il file viene [`dotnet restore`](dotnet-restore.md) creato quando viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-125">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="c3f8e-126">Senza il file di asset sul posto, gli strumenti non possono risolvere gli assembly di riferimento, generando così errori.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-126">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="c3f8e-127">Con .NET Core 1.x SDK, `dotnet restore` era `dotnet build`necessario eseguire in modo esplicito prima dell'esecuzione .</span><span class="sxs-lookup"><span data-stu-id="c3f8e-127">With .NET Core 1.x SDK, you needed to explicitly run `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="c3f8e-128">A partire da .NET Core 2.0 SDK, `dotnet restore` viene eseguito in modo implicito quando viene eseguito `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-128">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="c3f8e-129">Se si desidera disabilitare ripristino implicito quando si esegue il comando di compilazione, è possibile passare l’opzione `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-129">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="c3f8e-130">La proprietà `<OutputType>` nel file di progetto determina se il progetto è eseguibile o meno.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-130">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="c3f8e-131">L'esempio seguente descrive un progetto che produce codice eseguibile:</span><span class="sxs-lookup"><span data-stu-id="c3f8e-131">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="c3f8e-132">Per produrre una libreria, `<OutputType>` omettere la proprietà `Library`o modificarne il valore in .</span><span class="sxs-lookup"><span data-stu-id="c3f8e-132">To produce a library, omit the `<OutputType>` property or change its value to `Library`.</span></span> <span data-ttu-id="c3f8e-133">La DLL IL per una libreria non contiene punti di ingresso e non può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-133">The IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="c3f8e-134">MSBuild</span><span class="sxs-lookup"><span data-stu-id="c3f8e-134">MSBuild</span></span>

<span data-ttu-id="c3f8e-135">Poiché `dotnet build` usa MSBuild per compilare il progetto, sono supportate le compilazioni parallele e incrementali.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-135">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="c3f8e-136">Per altre informazioni, vedere [Compilazioni incrementali](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="c3f8e-136">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="c3f8e-137">In aggiunta alle proprie opzioni, il comando `dotnet build` accetta anche le opzioni di MSBuild, ad esempio `-p` per l'impostazione delle proprietà o `-l` per la definizione di un logger.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-137">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="c3f8e-138">Per altre informazioni su queste opzioni, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="c3f8e-138">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="c3f8e-139">In alternativa è anche possibile usare il comando [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="c3f8e-139">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="c3f8e-140">L'esecuzione `dotnet build` equivale `dotnet msbuild -restore`all'esecuzione di ; tuttavia, il livello di dettaglio predefinito dell'output è diverso.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-140">Running `dotnet build` is equivalent to running `dotnet msbuild -restore`; however, the default verbosity of the output is different.</span></span>

## <a name="arguments"></a><span data-ttu-id="c3f8e-141">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c3f8e-141">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="c3f8e-142">File di progetto o di soluzione da compilare.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-142">The project or solution file to build.</span></span> <span data-ttu-id="c3f8e-143">Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-143">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="c3f8e-144">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c3f8e-144">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="c3f8e-145">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-145">Defines the build configuration.</span></span> <span data-ttu-id="c3f8e-146">L'impostazione predefinita `Debug`per la maggior parte dei progetti è , ma è possibile eseguire l'override delle impostazioni di configurazione della compilazione nel progetto.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-146">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c3f8e-147">Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-147">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="c3f8e-148">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="c3f8e-148">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="c3f8e-149">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-149">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c3f8e-150">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-150">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c3f8e-151">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-151">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="c3f8e-152">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="c3f8e-152">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="c3f8e-153">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-153">For example, to complete authentication.</span></span> <span data-ttu-id="c3f8e-154">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-154">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="c3f8e-155">Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-155">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="c3f8e-156">Contrassegna la compilazione come non sicura per la compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-156">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="c3f8e-157">Questo flag disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-157">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c3f8e-158">Non esegue un ripristino implicito durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-158">Doesn't execute an implicit restore during build.</span></span>

- **`--nologo`**

  <span data-ttu-id="c3f8e-159">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-159">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="c3f8e-160">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-160">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c3f8e-161">Directory in cui inserire i file binari compilati.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-161">Directory in which to place the built binaries.</span></span> <span data-ttu-id="c3f8e-162">Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-162">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="c3f8e-163">Per i progetti con più `TargetFrameworks` framework di destinazione (tramite la proprietà), è inoltre necessario definire `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-163">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c3f8e-164">Specifica il runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-164">Specifies the target runtime.</span></span> <span data-ttu-id="c3f8e-165">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c3f8e-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c3f8e-166">Imposta il livello di dettaglio di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-166">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="c3f8e-167">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-167">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c3f8e-168">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-168">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="c3f8e-169">Imposta il valore della proprietà `$(VersionSuffix)` da usare durante la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-169">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="c3f8e-170">Funziona solo se la proprietà `$(Version)` non è impostata.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-170">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="c3f8e-171">La proprietà `$(Version)` viene quindi impostata su `$(VersionPrefix)` combinata con `$(VersionSuffix)`, separati da un trattino.</span><span class="sxs-lookup"><span data-stu-id="c3f8e-171">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="c3f8e-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="c3f8e-172">Examples</span></span>

- <span data-ttu-id="c3f8e-173">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="c3f8e-173">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="c3f8e-174">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="c3f8e-174">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="c3f8e-175">Compilare un progetto e le relative dipendenze per un runtime specifico ( in questo esempio, Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="c3f8e-175">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="c3f8e-176">Compilare il progetto e usare l'origine del pacchetto NuGet specificato durante l'operazione di ripristino (.NET Core 2.0 SDK e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="c3f8e-176">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="c3f8e-177">Compilare il progetto e impostare la versione 1.2.3.4 come parametro di compilazione usando l' [opzione MSBuild](#msbuild)`-p`:</span><span class="sxs-lookup"><span data-stu-id="c3f8e-177">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
