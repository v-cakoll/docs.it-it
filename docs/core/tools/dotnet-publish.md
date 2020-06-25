---
title: Comando dotnet publish
description: Il dotnet publish comando pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: 61cfcf06586f3ac66526de69a17b8aef3cf0c795
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365583"
---
# <a name="dotnet-publish"></a><span data-ttu-id="99c08-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="99c08-103">dotnet publish</span></span>

<span data-ttu-id="99c08-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="99c08-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="99c08-105">Nome</span><span class="sxs-lookup"><span data-stu-id="99c08-105">Name</span></span>

<span data-ttu-id="99c08-106">`dotnet publish`-Pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.</span><span class="sxs-lookup"><span data-stu-id="99c08-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="99c08-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="99c08-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-p:PublishReadyToRun=true] [-p:PublishSingleFile=true] [-p:PublishTrimmed=true]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--self-contained [true|false]]
    [--no-self-contained] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

## <a name="description"></a><span data-ttu-id="99c08-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c08-108">Description</span></span>

<span data-ttu-id="99c08-109">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="99c08-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="99c08-110">L'output include gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="99c08-110">The output includes the following assets:</span></span>

- <span data-ttu-id="99c08-111">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="99c08-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="99c08-112">*.deps.jssu* file che include tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="99c08-113">*.runtimeconfig.jsnel* file che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime, ad esempio Garbage Collection tipo.</span><span class="sxs-lookup"><span data-stu-id="99c08-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="99c08-114">Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="99c08-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="99c08-115">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="99c08-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="99c08-116">È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="99c08-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="99c08-117">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="99c08-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="99c08-118">Per altre informazioni, vedere [pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="99c08-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="99c08-119">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="99c08-119">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

### <a name="msbuild"></a><span data-ttu-id="99c08-120">MSBuild</span><span class="sxs-lookup"><span data-stu-id="99c08-120">MSBuild</span></span>

<span data-ttu-id="99c08-121">Il comando `dotnet publish` chiama MSBuild che richiama la destinazione `Publish`.</span><span class="sxs-lookup"><span data-stu-id="99c08-121">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="99c08-122">Tutti i parametri passati a `dotnet publish` vengono passati a MSBuild.</span><span class="sxs-lookup"><span data-stu-id="99c08-122">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="99c08-123">I parametri `-c` e `-o` sono mappati rispettivamente alle proprietà `Configuration` e `PublishDir` di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="99c08-123">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `PublishDir` properties, respectively.</span></span>

<span data-ttu-id="99c08-124">Il `dotnet publish` comando accetta opzioni MSBuild, ad esempio `-p` per l'impostazione delle proprietà e `-l` per la definizione di un logger.</span><span class="sxs-lookup"><span data-stu-id="99c08-124">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="99c08-125">È ad esempio possibile impostare una proprietà MSBuild utilizzando il formato: `-p:<NAME>=<VALUE>` .</span><span class="sxs-lookup"><span data-stu-id="99c08-125">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span> <span data-ttu-id="99c08-126">È anche possibile impostare le proprietà relative alla pubblicazione facendo riferimento a un file con *estensione pubxml* , ad esempio:</span><span class="sxs-lookup"><span data-stu-id="99c08-126">You can also set publish-related properties by referring to a *.pubxml* file, for example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

<span data-ttu-id="99c08-127">Per altre informazioni, vedere le seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="99c08-127">For more information, see the following resources:</span></span>

- [<span data-ttu-id="99c08-128">Riferimenti alla riga di comando di MSBuild</span><span class="sxs-lookup"><span data-stu-id="99c08-128">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="99c08-129">Profili di pubblicazione di Visual Studio (con estensione pubxml) per la distribuzione di app ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="99c08-129">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="99c08-130">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="99c08-130">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="99c08-131">Argomenti</span><span class="sxs-lookup"><span data-stu-id="99c08-131">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="99c08-132">Progetto o soluzione da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="99c08-132">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="99c08-133">`PROJECT`è il percorso e il nome file di un file di progetto [c#](csproj.md), f # o Visual Basic o il percorso di una directory che contiene un file di progetto C#, f # o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="99c08-133">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="99c08-134">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="99c08-134">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="99c08-135">`SOLUTION`è il percorso e il nome file di un file di soluzione (estensione*sln* ) o il percorso di una directory che contiene un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="99c08-135">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="99c08-136">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="99c08-136">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="99c08-137">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99c08-137">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="99c08-138">Opzioni</span><span class="sxs-lookup"><span data-stu-id="99c08-138">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="99c08-139">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="99c08-139">Defines the build configuration.</span></span> <span data-ttu-id="99c08-140">Il valore predefinito per la maggior parte dei progetti è `Debug` , ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-140">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="99c08-141">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="99c08-141">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="99c08-142">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-142">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="99c08-143">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="99c08-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="99c08-144">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="99c08-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="99c08-145">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="99c08-145">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="99c08-146">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="99c08-146">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="99c08-147">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="99c08-147">For example, to complete authentication.</span></span> <span data-ttu-id="99c08-148">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99c08-148">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="99c08-149">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="99c08-149">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="99c08-150">Il file manifesto fa parte dell'output del [ `dotnet store` comando](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="99c08-150">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="99c08-151">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="99c08-151">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="99c08-152">Non compila il progetto prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="99c08-152">Doesn't build the project before publishing.</span></span> <span data-ttu-id="99c08-153">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="99c08-153">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="99c08-154">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="99c08-154">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="99c08-155">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="99c08-155">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="99c08-156">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99c08-156">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="99c08-157">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="99c08-157">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="99c08-158">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="99c08-158">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="99c08-159">Se non specificato, il valore predefinito è *[project_file_folder]./bin/[Configuration]/[Framework]/Publish/* per un eseguibile dipendente dal runtime e binari multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="99c08-159">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="99c08-160">Il valore predefinito è *[project_file_folder]/bin/[Configuration]/[Framework]/[Runtime]/Publish/* per un file eseguibile autonomo.</span><span class="sxs-lookup"><span data-stu-id="99c08-160">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="99c08-161">In un progetto Web, se la cartella di output si trova nella cartella del progetto, i `dotnet publish` comandi successivi generano cartelle di output nidificate.</span><span class="sxs-lookup"><span data-stu-id="99c08-161">In a web project, if the output folder is in the project folder, successive `dotnet publish` commands result in nested output folders.</span></span> <span data-ttu-id="99c08-162">Ad esempio, se la cartella del progetto *è MyProject*e la cartella di output di pubblicazione è *MyProject/Publish*ed è stata eseguita `dotnet publish` due volte, la seconda esecuzione inserisce i file di contenuto, ad esempio i file con *estensione config* e *JSON* , in *MyProject/Publish/Publish*.</span><span class="sxs-lookup"><span data-stu-id="99c08-162">For example, if the project folder is *myproject*, and the publish output folder is *myproject/publish*, and you run `dotnet publish` twice, the second run puts content files such as *.config* and *.json* files in *myproject/publish/publish*.</span></span> <span data-ttu-id="99c08-163">Per evitare di nidificare le cartelle di pubblicazione, specificare una cartella di pubblicazione che non si trovi **direttamente** nella cartella del progetto o escludere la cartella di pubblicazione dal progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-163">To avoid nesting publish folders, specify a publish folder that is not **directly** under the project folder, or exclude the publish folder from the project.</span></span> <span data-ttu-id="99c08-164">Per escludere una cartella di pubblicazione denominata *publishoutput*, aggiungere l'elemento seguente a un `PropertyGroup` elemento nel file con *estensione csproj* :</span><span class="sxs-lookup"><span data-stu-id="99c08-164">To exclude a publish folder named *publishoutput*, add the following element to a `PropertyGroup` element in the *.csproj* file:</span></span>

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - <span data-ttu-id="99c08-165">.NET Core 3. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="99c08-165">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="99c08-166">Se quando si pubblica un progetto viene specificato un percorso relativo, la directory di output generata è relativa alla directory di lavoro corrente, non al percorso del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-166">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="99c08-167">Se viene specificato un percorso relativo durante la pubblicazione di una soluzione, tutti gli output per tutti i progetti vengono inseriti nella cartella specificata rispetto alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="99c08-167">If a relative path is specified when publishing a solution, all output for all projects goes into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="99c08-168">Per fare in modo che l'output di pubblicazione vada in cartelle separate per ogni progetto, specificare un percorso relativo usando la `PublishDir` Proprietà MSBuild anziché l' `--output` opzione.</span><span class="sxs-lookup"><span data-stu-id="99c08-168">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="99c08-169">Ad esempio, `dotnet publish -p:PublishDir=.\publish` Invia l'output di pubblicazione per ogni progetto a una `publish` cartella nella cartella che contiene il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-169">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="99c08-170">SDK di .NET Core 2. x</span><span class="sxs-lookup"><span data-stu-id="99c08-170">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="99c08-171">Se quando si pubblica un progetto viene specificato un percorso relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="99c08-171">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="99c08-172">Se viene specificato un percorso relativo quando si pubblica una soluzione, l'output di ogni progetto viene inserito in una cartella distinta rispetto al percorso del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-172">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="99c08-173">Se viene specificato un percorso assoluto durante la pubblicazione di una soluzione, tutti gli output di pubblicazione per tutti i progetti vengono inseriti nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="99c08-173">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`-p:PublishReadyToRun=true`**

  <span data-ttu-id="99c08-174">Compila gli assembly dell'applicazione come formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="99c08-174">Compiles application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="99c08-175">R2R è un formato di compilazione AOT (Ahead-of-time).</span><span class="sxs-lookup"><span data-stu-id="99c08-175">R2R is a form of ahead-of-time (AOT) compilation.</span></span> <span data-ttu-id="99c08-176">Per altre informazioni, vedere [ReadyToRun images](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="99c08-176">For more information, see [ReadyToRun images](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span> <span data-ttu-id="99c08-177">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99c08-177">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="99c08-178">È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="99c08-178">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="99c08-179">Per ulteriori informazioni, vedere [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="99c08-179">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishSingleFile=true`**

  <span data-ttu-id="99c08-180">Inserisce l'app in un eseguibile di un singolo file specifico della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="99c08-180">Packages the app into a platform-specific single-file executable.</span></span> <span data-ttu-id="99c08-181">Il file eseguibile è autoestraente e contiene tutte le dipendenze (incluso native) necessarie per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="99c08-181">The executable is self-extracting and contains all dependencies (including native) that are required to run the app.</span></span> <span data-ttu-id="99c08-182">Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="99c08-182">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="99c08-183">L'avvio dell'applicazione sarà più veloce alla successiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="99c08-183">Startup is faster when the application is run again.</span></span> <span data-ttu-id="99c08-184">Non è necessario estrarre l'applicazione una seconda volta, a meno che non venga usata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="99c08-184">The application doesn't need to extract itself a second time unless a new version is used.</span></span> <span data-ttu-id="99c08-185">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99c08-185">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="99c08-186">Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="99c08-186">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

  <span data-ttu-id="99c08-187">È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="99c08-187">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="99c08-188">Per ulteriori informazioni, vedere [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="99c08-188">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishTrimmed=true`**

  <span data-ttu-id="99c08-189">Elimina le librerie inutilizzate per ridurre le dimensioni di distribuzione di un'app durante la pubblicazione di un eseguibile autonomo.</span><span class="sxs-lookup"><span data-stu-id="99c08-189">Trims unused libraries to reduce the deployment size of an app when publishing a self-contained executable.</span></span> <span data-ttu-id="99c08-190">Per altre informazioni, vedere [tagliare le distribuzioni e gli eseguibili autonomi](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="99c08-190">For more information, see [Trim self-contained deployments and executables](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="99c08-191">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99c08-191">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="99c08-192">È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="99c08-192">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="99c08-193">Per ulteriori informazioni, vedere [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="99c08-193">For more information, see [MSBuild](#msbuild).</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="99c08-194">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="99c08-194">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="99c08-195">Il valore predefinito è `true` se viene specificato un identificatore di runtime e il progetto è un progetto eseguibile (non un progetto di libreria).</span><span class="sxs-lookup"><span data-stu-id="99c08-195">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="99c08-196">Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="99c08-196">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="99c08-197">Se questa opzione viene utilizzata senza specificare `true` o `false` , il valore predefinito è `true` .</span><span class="sxs-lookup"><span data-stu-id="99c08-197">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="99c08-198">In tal caso, non inserire l'argomento della soluzione o del progetto subito dopo `--self-contained` , perché `true` o `false` è previsto in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="99c08-198">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="99c08-199">È equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="99c08-199">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="99c08-200">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="99c08-200">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="99c08-201">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="99c08-201">Publishes the application for a given runtime.</span></span> <span data-ttu-id="99c08-202">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="99c08-202">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="99c08-203">Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="99c08-203">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="99c08-204">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="99c08-204">Sets the verbosity level of the command.</span></span> <span data-ttu-id="99c08-205">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="99c08-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="99c08-206">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="99c08-206">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="99c08-207">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="99c08-207">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="99c08-208">Esempio</span><span class="sxs-lookup"><span data-stu-id="99c08-208">Examples</span></span>

- <span data-ttu-id="99c08-209">Creare un [file binario multipiattaforma dipendente dal runtime](../deploying/index.md#produce-a-cross-platform-binary) per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="99c08-209">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="99c08-210">A partire da .NET Core 3,0 SDK, questo esempio crea anche un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="99c08-210">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="99c08-211">Creare un [eseguibile indipendente](../deploying/index.md#publish-self-contained) per il progetto nella directory corrente, per un runtime specifico:</span><span class="sxs-lookup"><span data-stu-id="99c08-211">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="99c08-212">Il RID deve trovarsi nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-212">The RID must be in the project file.</span></span>

- <span data-ttu-id="99c08-213">Creare un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per il progetto nella directory corrente, per una piattaforma specifica:</span><span class="sxs-lookup"><span data-stu-id="99c08-213">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="99c08-214">Il RID deve trovarsi nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="99c08-214">The RID must be in the project file.</span></span> <span data-ttu-id="99c08-215">Questo esempio si applica a .NET Core 3,0 SDK e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="99c08-215">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="99c08-216">Pubblicare il progetto nella directory corrente, per un runtime e un Framework di destinazione specifici:</span><span class="sxs-lookup"><span data-stu-id="99c08-216">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="99c08-217">Pubblicare il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="99c08-217">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="99c08-218">Pubblicare l'applicazione corrente, ma non ripristinare i riferimenti da progetto a progetto (P2P), solo il progetto radice durante l'operazione di ripristino:</span><span class="sxs-lookup"><span data-stu-id="99c08-218">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="99c08-219">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="99c08-219">See also</span></span>

- [<span data-ttu-id="99c08-220">Panoramica della pubblicazione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="99c08-220">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="99c08-221">Pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="99c08-221">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="99c08-222">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="99c08-222">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="99c08-223">Catalogo di runtime IDentifier (RID)</span><span class="sxs-lookup"><span data-stu-id="99c08-223">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="99c08-224">Uso dell'autenticazione di macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="99c08-224">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="99c08-225">Struttura di directory di un'applicazione pubblicata</span><span class="sxs-lookup"><span data-stu-id="99c08-225">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
- [<span data-ttu-id="99c08-226">Riferimenti alla riga di comando di MSBuild</span><span class="sxs-lookup"><span data-stu-id="99c08-226">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="99c08-227">Profili di pubblicazione di Visual Studio (con estensione pubxml) per la distribuzione di app ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="99c08-227">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="99c08-228">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="99c08-228">dotnet msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="99c08-229">ILLInk. Tasks</span><span class="sxs-lookup"><span data-stu-id="99c08-229">ILLInk.Tasks</span></span>](https://aka.ms/dotnet-illink)
