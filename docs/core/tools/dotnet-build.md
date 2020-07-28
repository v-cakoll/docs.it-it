---
title: Comando dotnet build
description: Il comando dotnet build consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 02/14/2020
ms.openlocfilehash: 6f33b449301f40949ff5dfe4077564344a9de8ec
ms.sourcegitcommit: c8c3e1c63a00b7d27f76f5e50ee6469e6bdc8987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251166"
---
# <a name="dotnet-build"></a><span data-ttu-id="6b96a-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6b96a-103">dotnet build</span></span>

<span data-ttu-id="6b96a-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="6b96a-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6b96a-105">Nome</span><span class="sxs-lookup"><span data-stu-id="6b96a-105">Name</span></span>

<span data-ttu-id="6b96a-106">`dotnet build`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="6b96a-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6b96a-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="6b96a-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--source <SOURCE>]
    [-v|--verbosity <LEVEL>] [--version-suffix <VERSION_SUFFIX>]

dotnet build -h|--help
```

## <a name="description"></a><span data-ttu-id="6b96a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b96a-108">Description</span></span>

<span data-ttu-id="6b96a-109">Il comando `dotnet build` compila il progetto e le relative dipendenze in un set di file binari.</span><span class="sxs-lookup"><span data-stu-id="6b96a-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="6b96a-110">I file binari includono il codice del progetto nei file Intermediate Language (IL) con estensione *. dll* .</span><span class="sxs-lookup"><span data-stu-id="6b96a-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension.</span></span>  <span data-ttu-id="6b96a-111">A seconda del tipo di progetto e delle impostazioni, è possibile includere altri file, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6b96a-111">Depending on the project type and settings, other files may be included, such as:</span></span>

- <span data-ttu-id="6b96a-112">Eseguibile che può essere usato per eseguire l'applicazione, se il tipo di progetto è un file eseguibile destinato a .NET Core 3,0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="6b96a-112">An executable that can be used to run the application, if the project type is an executable targeting .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="6b96a-113">File di simboli usati per il debug con estensione *PDB* .</span><span class="sxs-lookup"><span data-stu-id="6b96a-113">Symbol files used for debugging with a *.pdb* extension.</span></span>
- <span data-ttu-id="6b96a-114">*.deps.jssu* file, che elenca le dipendenze dell'applicazione o della libreria.</span><span class="sxs-lookup"><span data-stu-id="6b96a-114">A *.deps.json* file, which lists the dependencies of the application or library.</span></span>
- <span data-ttu-id="6b96a-115">*.runtimeconfig.jsnel* file, che specifica il runtime condiviso e la relativa versione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-115">A *.runtimeconfig.json* file, which specifies the shared runtime and its version for an application.</span></span>
- <span data-ttu-id="6b96a-116">Altre librerie da cui dipende il progetto (tramite i riferimenti al progetto o i riferimenti ai pacchetti NuGet).</span><span class="sxs-lookup"><span data-stu-id="6b96a-116">Other libraries that the project depends on (via project references or NuGet package references).</span></span>

<span data-ttu-id="6b96a-117">Per i progetti eseguibili destinati a versioni precedenti a .NET Core 3,0, le dipendenze della libreria da NuGet non vengono in genere copiate nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="6b96a-117">For executable projects targeting versions earlier than .NET Core 3.0, library dependencies from NuGet are typically NOT copied to the output folder.</span></span>  <span data-ttu-id="6b96a-118">Vengono risolti dalla cartella pacchetti globali NuGet in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-118">They're resolved from the NuGet global packages folder at run time.</span></span> <span data-ttu-id="6b96a-119">Per queste ragioni, il prodotto di `dotnet build` non è pronto per essere trasferito in un altro computer per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-119">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="6b96a-120">Per creare una versione dell'applicazione che può essere distribuita, è necessario pubblicarla, ad esempio con il comando [DotNet Publish](dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="6b96a-120">To create a version of the application that can be deployed, you need to publish it (for example, with the [dotnet publish](dotnet-publish.md) command).</span></span> <span data-ttu-id="6b96a-121">Per altre informazioni, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="6b96a-121">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="6b96a-122">Per i progetti eseguibili destinati a .NET Core 3,0 e versioni successive, le dipendenze della libreria vengono copiate nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="6b96a-122">For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.</span></span> <span data-ttu-id="6b96a-123">Ciò significa che se non sono presenti altre logiche specifiche per la pubblicazione, ad esempio i progetti web, l'output di compilazione deve essere distribuibile.</span><span class="sxs-lookup"><span data-stu-id="6b96a-123">This means that if there isn't any other publish-specific logic (such as Web projects have), the build output should be deployable.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="6b96a-124">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="6b96a-124">Implicit restore</span></span>

<span data-ttu-id="6b96a-125">Per la compilazione è necessario il file *project.assets.json*, che elenca le dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-125">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="6b96a-126">Il file viene creato quando [`dotnet restore`](dotnet-restore.md) viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="6b96a-126">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="6b96a-127">Senza il file di asset sul posto, gli strumenti non possono risolvere gli assembly di riferimento, generando così errori.</span><span class="sxs-lookup"><span data-stu-id="6b96a-127">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

### <a name="executable-or-library-output"></a><span data-ttu-id="6b96a-128">Eseguibile o output della libreria</span><span class="sxs-lookup"><span data-stu-id="6b96a-128">Executable or library output</span></span>

<span data-ttu-id="6b96a-129">La proprietà `<OutputType>` nel file di progetto determina se il progetto è eseguibile o meno.</span><span class="sxs-lookup"><span data-stu-id="6b96a-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="6b96a-130">L'esempio seguente descrive un progetto che produce codice eseguibile:</span><span class="sxs-lookup"><span data-stu-id="6b96a-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="6b96a-131">Per produrre una libreria, omettere la `<OutputType>` proprietà o modificarne il valore in `Library` .</span><span class="sxs-lookup"><span data-stu-id="6b96a-131">To produce a library, omit the `<OutputType>` property or change its value to `Library`.</span></span> <span data-ttu-id="6b96a-132">La DLL il per una libreria non contiene punti di ingresso e non può essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="6b96a-132">The IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="6b96a-133">MSBuild</span><span class="sxs-lookup"><span data-stu-id="6b96a-133">MSBuild</span></span>

<span data-ttu-id="6b96a-134">Poiché `dotnet build` usa MSBuild per compilare il progetto, sono supportate le compilazioni parallele e incrementali.</span><span class="sxs-lookup"><span data-stu-id="6b96a-134">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="6b96a-135">Per altre informazioni, vedere [Compilazioni incrementali](/visualstudio/msbuild/incremental-builds).</span><span class="sxs-lookup"><span data-stu-id="6b96a-135">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="6b96a-136">In aggiunta alle proprie opzioni, il comando `dotnet build` accetta anche le opzioni di MSBuild, ad esempio `-p` per l'impostazione delle proprietà o `-l` per la definizione di un logger.</span><span class="sxs-lookup"><span data-stu-id="6b96a-136">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="6b96a-137">Per altre informazioni su queste opzioni, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="6b96a-137">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="6b96a-138">In alternativa è anche possibile usare il comando [dotnet msbuild](dotnet-msbuild.md).</span><span class="sxs-lookup"><span data-stu-id="6b96a-138">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="6b96a-139">`dotnet build`L'esecuzione di equivale all'esecuzione di `dotnet msbuild -restore` ; tuttavia, il livello di dettaglio predefinito dell'output è diverso.</span><span class="sxs-lookup"><span data-stu-id="6b96a-139">Running `dotnet build` is equivalent to running `dotnet msbuild -restore`; however, the default verbosity of the output is different.</span></span>

## <a name="arguments"></a><span data-ttu-id="6b96a-140">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6b96a-140">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="6b96a-141">File di progetto o di soluzione da compilare.</span><span class="sxs-lookup"><span data-stu-id="6b96a-141">The project or solution file to build.</span></span> <span data-ttu-id="6b96a-142">Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.</span><span class="sxs-lookup"><span data-stu-id="6b96a-142">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="6b96a-143">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6b96a-143">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="6b96a-144">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-144">Defines the build configuration.</span></span> <span data-ttu-id="6b96a-145">Il valore predefinito per la maggior parte dei progetti è `Debug` , ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.</span><span class="sxs-lookup"><span data-stu-id="6b96a-145">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6b96a-146">Esegue la compilazione per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="6b96a-146">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="6b96a-147">Il framework deve essere definito nel [file di progetto](csproj.md).</span><span class="sxs-lookup"><span data-stu-id="6b96a-147">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="6b96a-148">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6b96a-148">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="6b96a-149">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="6b96a-149">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6b96a-150">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="6b96a-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="6b96a-151">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="6b96a-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="6b96a-152">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-152">For example, to complete authentication.</span></span> <span data-ttu-id="6b96a-153">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6b96a-153">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="6b96a-154">Ignora i riferimenti da progetto a progetto e compila solo il progetto radice specificato.</span><span class="sxs-lookup"><span data-stu-id="6b96a-154">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="6b96a-155">Contrassegna la compilazione come non sicura per la compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="6b96a-155">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="6b96a-156">Questo flag disattiva la compilazione incrementale e impone una ricompilazione pulita del grafico delle dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="6b96a-156">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="6b96a-157">Non esegue un ripristino implicito durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-157">Doesn't execute an implicit restore during build.</span></span>

- **`--nologo`**

  <span data-ttu-id="6b96a-158">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="6b96a-158">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="6b96a-159">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="6b96a-159">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="6b96a-160">Directory in cui inserire i file binari compilati.</span><span class="sxs-lookup"><span data-stu-id="6b96a-160">Directory in which to place the built binaries.</span></span> <span data-ttu-id="6b96a-161">Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="6b96a-161">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="6b96a-162">Per i progetti con più framework di destinazione (tramite la `TargetFrameworks` proprietà), è necessario definire anche `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-162">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="6b96a-163">Specifica il runtime di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6b96a-163">Specifies the target runtime.</span></span> <span data-ttu-id="6b96a-164">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="6b96a-164">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`--source <SOURCE>`**

  <span data-ttu-id="6b96a-165">URI dell'origine del pacchetto NuGet da usare durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="6b96a-165">The URI of the NuGet package source to use during the restore operation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="6b96a-166">Imposta il livello di dettaglio di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="6b96a-166">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="6b96a-167">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6b96a-167">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6b96a-168">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="6b96a-168">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="6b96a-169">Imposta il valore della proprietà `$(VersionSuffix)` da usare durante la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="6b96a-169">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="6b96a-170">Funziona solo se la proprietà `$(Version)` non è impostata.</span><span class="sxs-lookup"><span data-stu-id="6b96a-170">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="6b96a-171">La proprietà `$(Version)` viene quindi impostata su `$(VersionPrefix)` combinata con `$(VersionSuffix)`, separati da un trattino.</span><span class="sxs-lookup"><span data-stu-id="6b96a-171">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="6b96a-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="6b96a-172">Examples</span></span>

- <span data-ttu-id="6b96a-173">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="6b96a-173">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="6b96a-174">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="6b96a-174">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="6b96a-175">Compilare un progetto e le relative dipendenze per un runtime specifico ( in questo esempio, Ubuntu 18.04):</span><span class="sxs-lookup"><span data-stu-id="6b96a-175">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="6b96a-176">Compilare il progetto e usare l'origine del pacchetto NuGet specificato durante l'operazione di ripristino (.NET Core 2.0 SDK e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="6b96a-176">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="6b96a-177">Compilare il progetto e impostare la versione 1.2.3.4 come parametro di compilazione usando l' [opzione MSBuild](#msbuild)`-p`:</span><span class="sxs-lookup"><span data-stu-id="6b96a-177">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
