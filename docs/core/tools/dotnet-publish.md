---
title: Comando dotnet publish
description: Il comando dotnet publish pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: 26dda33d04f3f7a23805627708b55233ef4e87ef
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242842"
---
# <a name="dotnet-publish"></a><span data-ttu-id="8cb83-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="8cb83-103">dotnet publish</span></span>

<span data-ttu-id="8cb83-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="8cb83-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8cb83-105">Nome</span><span class="sxs-lookup"><span data-stu-id="8cb83-105">Name</span></span>

<span data-ttu-id="8cb83-106">`dotnet publish`- Pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.- Publishes the application and its dependencies to a folder for deployment to a hosting system.</span><span class="sxs-lookup"><span data-stu-id="8cb83-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8cb83-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="8cb83-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-p:PublishReadyToRun] [-p:PublishSingleFile]
    [-p:PublishTrimmed] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8cb83-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cb83-108">Description</span></span>

<span data-ttu-id="8cb83-109">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="8cb83-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="8cb83-110">L'output include gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cb83-110">The output includes the following assets:</span></span>

- <span data-ttu-id="8cb83-111">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="8cb83-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="8cb83-112">Un file *.deps.json* che include tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="8cb83-113">Un file *.runtimeconfig.json* che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime (ad esempio, tipo di Garbage Collection).</span><span class="sxs-lookup"><span data-stu-id="8cb83-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="8cb83-114">Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="8cb83-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="8cb83-115">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="8cb83-116">È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="8cb83-117">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="8cb83-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="8cb83-118">Per altre informazioni, vedere [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="8cb83-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="msbuild"></a><span data-ttu-id="8cb83-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="8cb83-119">MSBuild</span></span>

<span data-ttu-id="8cb83-120">Il comando `dotnet publish` chiama MSBuild che richiama la destinazione `Publish`.</span><span class="sxs-lookup"><span data-stu-id="8cb83-120">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="8cb83-121">Tutti i parametri passati a `dotnet publish` vengono passati a MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8cb83-121">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="8cb83-122">I parametri `-c` e `-o` sono mappati rispettivamente alle proprietà `Configuration` e `OutputPath` di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8cb83-122">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `OutputPath` properties, respectively.</span></span>

<span data-ttu-id="8cb83-123">Il `dotnet publish` comando accetta le opzioni `-p` MSBuild, `-l` ad esempio per l'impostazione delle proprietà e per definire un logger.</span><span class="sxs-lookup"><span data-stu-id="8cb83-123">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="8cb83-124">Ad esempio, è possibile impostare una proprietà `-p:<NAME>=<VALUE>`MSBuild utilizzando il formato: .</span><span class="sxs-lookup"><span data-stu-id="8cb83-124">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span> <span data-ttu-id="8cb83-125">È inoltre possibile impostare le proprietà relative alla pubblicazione facendo riferimento a un file pubxml, ad esempio:You can also set publish-related properties by referring to a *.pubxml* file, for example:</span><span class="sxs-lookup"><span data-stu-id="8cb83-125">You can also set publish-related properties by referring to a *.pubxml* file, for example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

<span data-ttu-id="8cb83-126">Per altre informazioni, vedere le seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="8cb83-126">For more information, see the following resources:</span></span>

- [<span data-ttu-id="8cb83-127">Riferimenti alla riga di comando di MSBuild</span><span class="sxs-lookup"><span data-stu-id="8cb83-127">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="8cb83-128">Profili di pubblicazione di Visual Studio (pubxml) per la distribuzione di app ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8cb83-128">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="8cb83-129">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="8cb83-129">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="8cb83-130">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8cb83-130">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="8cb83-131">Progetto o soluzione da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="8cb83-131">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="8cb83-132">`PROJECT`è il percorso e il nome del file di un file di progetto di [C,](csproj.md)F o Visual Basic oppure il percorso di una directory che contiene un file di progetto C, F o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8cb83-132">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="8cb83-133">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8cb83-133">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="8cb83-134">`SOLUTION`è il percorso e il nome file di un file di soluzione (estensione*sln)* o il percorso di una directory che contiene un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-134">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="8cb83-135">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8cb83-135">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="8cb83-136">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="8cb83-136">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="8cb83-137">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8cb83-137">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="8cb83-138">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-138">Defines the build configuration.</span></span> <span data-ttu-id="8cb83-139">L'impostazione predefinita `Debug`per la maggior parte dei progetti è , ma è possibile eseguire l'override delle impostazioni di configurazione della compilazione nel progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-139">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8cb83-140">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="8cb83-140">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8cb83-141">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-141">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="8cb83-142">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8cb83-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="8cb83-143">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8cb83-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8cb83-144">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="8cb83-144">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="8cb83-145">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="8cb83-145">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="8cb83-146">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-146">For example, to complete authentication.</span></span> <span data-ttu-id="8cb83-147">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="8cb83-147">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="8cb83-148">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="8cb83-148">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="8cb83-149">Il file manifesto fa parte [ `dotnet store` ](dotnet-store.md)dell'output del comando .</span><span class="sxs-lookup"><span data-stu-id="8cb83-149">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="8cb83-150">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-150">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="8cb83-151">Non compila il progetto prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-151">Doesn't build the project before publishing.</span></span> <span data-ttu-id="8cb83-152">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="8cb83-152">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="8cb83-153">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="8cb83-153">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="8cb83-154">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="8cb83-154">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="8cb83-155">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="8cb83-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="8cb83-156">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="8cb83-156">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8cb83-157">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="8cb83-157">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="8cb83-158">Se non specificato, il valore predefinito è *[project_file_folder]./bin/[configuration]/[framework]/publish/* per un eseguibile dipendente dal runtime e file binari multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="8cb83-158">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="8cb83-159">Il valore predefinito è *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* per un eseguibile autonomo.</span><span class="sxs-lookup"><span data-stu-id="8cb83-159">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="8cb83-160">In un progetto Web, se la cartella di `dotnet publish` output si trova nella cartella del progetto, i comandi successivi generano cartelle di output nidificate.</span><span class="sxs-lookup"><span data-stu-id="8cb83-160">In a web project, if the output folder is in the project folder, successive `dotnet publish` commands result in nested output folders.</span></span> <span data-ttu-id="8cb83-161">Ad esempio, se la cartella del progetto è *myproject*e la cartella `dotnet publish` dell'output di pubblicazione è *myproject/publish*e viene eseguita due volte, la seconda esecuzione inserisce i file di contenuto, ad esempio i file *con estensione config* e *json,* nei file *myproject/publish/publish*.</span><span class="sxs-lookup"><span data-stu-id="8cb83-161">For example, if the project folder is *myproject*, and the publish output folder is *myproject/publish*, and you run `dotnet publish` twice, the second run puts content files such as *.config* and *.json* files in *myproject/publish/publish*.</span></span> <span data-ttu-id="8cb83-162">Per evitare di nidificare le cartelle di pubblicazione, specificare una cartella di pubblicazione che non si trova direttamente sotto la cartella del progetto o escludere la cartella di pubblicazione dal progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-162">To avoid nesting publish folders, specify a publish folder that is not directly under the project folder, or exclude the publish folder from the project.</span></span> <span data-ttu-id="8cb83-163">Per escludere una cartella di pubblicazione denominata `PropertyGroup` *publishoutput*, aggiungere il seguente elemento a un elemento nel file con estensione *csproj:*</span><span class="sxs-lookup"><span data-stu-id="8cb83-163">To exclude a publish folder named *publishoutput*, add the following element to a `PropertyGroup` element in the *.csproj* file:</span></span>

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - <span data-ttu-id="8cb83-164">.NET Core 3.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="8cb83-164">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="8cb83-165">Se viene specificato un percorso relativo durante la pubblicazione di un progetto, la directory di output generata è relativa alla directory di lavoro corrente, non al percorso del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-165">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="8cb83-166">Se viene specificato un percorso relativo durante la pubblicazione di una soluzione, tutto l'output per tutti i progetti viene inserito nella cartella specificata rispetto alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="8cb83-166">If a relative path is specified when publishing a solution, all output for all projects go into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="8cb83-167">Per fare in modo che l'output di pubblicazione vada a `PublishDir` cartelle separate `--output` per ogni progetto, specificare un percorso relativo utilizzando la proprietà msbuild anziché l'opzione .</span><span class="sxs-lookup"><span data-stu-id="8cb83-167">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="8cb83-168">Ad esempio, `dotnet publish -p:PublishDir=.\publish` invia l'output `publish` di pubblicazione per ogni progetto in una cartella all'altra della cartella che contiene il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-168">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="8cb83-169">.NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="8cb83-169">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="8cb83-170">Se durante la pubblicazione di un progetto viene specificato un percorso relativo, la directory di output generata è relativa al percorso del file di progetto, non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="8cb83-170">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="8cb83-171">Se viene specificato un percorso relativo durante la pubblicazione di una soluzione, l'output di ogni progetto viene inserito in una cartella separata rispetto al percorso del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-171">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="8cb83-172">Se viene specificato un percorso assoluto durante la pubblicazione di una soluzione, tutto l'output di pubblicazione per tutti i progetti viene inserito nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="8cb83-172">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`-p:PublishReadyToRun`**

  <span data-ttu-id="8cb83-173">Compila gli assembly dell'applicazione in formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="8cb83-173">Compiles application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="8cb83-174">R2R è un formato di compilazione AOT (Ahead-of-time).</span><span class="sxs-lookup"><span data-stu-id="8cb83-174">R2R is a form of ahead-of-time (AOT) compilation.</span></span> <span data-ttu-id="8cb83-175">Per ulteriori informazioni, vedere [Immagini ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="8cb83-175">For more information, see [ReadyToRun images](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span> <span data-ttu-id="8cb83-176">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="8cb83-176">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8cb83-177">È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cb83-177">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="8cb83-178">Per ulteriori informazioni, vedere [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="8cb83-178">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishSingleFile`**

  <span data-ttu-id="8cb83-179">Crea un pacchetto dell'app in un eseguibile a file singolo specifico della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="8cb83-179">Packages the app into a platform-specific single-file executable.</span></span> <span data-ttu-id="8cb83-180">L'eseguibile è autoestraente e contiene tutte le dipendenze (incluso nativo) necessarie per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="8cb83-180">The executable is self-extracting and contains all dependencies (including native) that are required to run the app.</span></span> <span data-ttu-id="8cb83-181">Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-181">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="8cb83-182">L'avvio dell'applicazione sarà più veloce alla successiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-182">Startup is faster when the application is run again.</span></span> <span data-ttu-id="8cb83-183">L'applicazione non ha bisogno di estrarre se stessa una seconda volta a meno che non viene utilizzata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-183">The application doesn't need to extract itself a second time unless a new version is used.</span></span> <span data-ttu-id="8cb83-184">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="8cb83-184">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8cb83-185">Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="8cb83-185">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

  <span data-ttu-id="8cb83-186">È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cb83-186">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="8cb83-187">Per ulteriori informazioni, vedere [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="8cb83-187">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishTrimmed`**

  <span data-ttu-id="8cb83-188">Taglia le librerie inutilizzate per ridurre le dimensioni di distribuzione di un'app durante la pubblicazione di un eseguibile autonomo.</span><span class="sxs-lookup"><span data-stu-id="8cb83-188">Trims unused libraries to reduce the deployment size of an app when publishing a self-contained executable.</span></span> <span data-ttu-id="8cb83-189">Per ulteriori informazioni, consultate [Tagliare distribuzioni ed eseguibili indipendenti.](../deploying/trim-self-contained.md)</span><span class="sxs-lookup"><span data-stu-id="8cb83-189">For more information, see [Trim self-contained deployments and executables](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="8cb83-190">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="8cb83-190">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="8cb83-191">È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cb83-191">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="8cb83-192">Per ulteriori informazioni, vedere [MSBuild](#msbuild).</span><span class="sxs-lookup"><span data-stu-id="8cb83-192">For more information, see [MSBuild](#msbuild).</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="8cb83-193">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-193">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="8cb83-194">L'impostazione predefinita è `true` se viene specificato un identificatore di runtime e il progetto è un progetto eseguibile (non un progetto di libreria).</span><span class="sxs-lookup"><span data-stu-id="8cb83-194">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="8cb83-195">Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .</span><span class="sxs-lookup"><span data-stu-id="8cb83-195">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="8cb83-196">Se questa opzione viene `true` utilizzata `false`senza specificare o , il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="8cb83-196">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="8cb83-197">In tal caso, non inserire la soluzione `--self-contained`o `true` l'argomento del progetto immediatamente dopo , perché o `false` è previsto in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-197">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="8cb83-198">È equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="8cb83-198">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="8cb83-199">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="8cb83-199">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="8cb83-200">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="8cb83-200">Publishes the application for a given runtime.</span></span> <span data-ttu-id="8cb83-201">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8cb83-201">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="8cb83-202">Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .</span><span class="sxs-lookup"><span data-stu-id="8cb83-202">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8cb83-203">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="8cb83-203">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8cb83-204">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8cb83-204">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8cb83-205">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="8cb83-205">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="8cb83-206">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="8cb83-206">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="8cb83-207">Esempi</span><span class="sxs-lookup"><span data-stu-id="8cb83-207">Examples</span></span>

- <span data-ttu-id="8cb83-208">Creare un file binario multipiattaforma dipendente dal runtime per il progetto nella directory corrente:Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span><span class="sxs-lookup"><span data-stu-id="8cb83-208">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="8cb83-209">A partire da .NET Core 3.0 SDK, questo esempio crea anche un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="8cb83-209">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="8cb83-210">Creare un eseguibile indipendente per il progetto nella directory corrente, per un runtime specifico:Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span><span class="sxs-lookup"><span data-stu-id="8cb83-210">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="8cb83-211">Il RID deve essere nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-211">The RID must be in the project file.</span></span>

- <span data-ttu-id="8cb83-212">Creare un eseguibile dipendente dal runtime per il progetto nella directory corrente, per una piattaforma specifica:Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span><span class="sxs-lookup"><span data-stu-id="8cb83-212">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="8cb83-213">Il RID deve essere nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="8cb83-213">The RID must be in the project file.</span></span> <span data-ttu-id="8cb83-214">Questo esempio si applica a .NET Core 3.0 SDK e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8cb83-214">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="8cb83-215">Pubblicare il progetto nella directory corrente, per un runtime e un framework di destinazione specifici:Publish the project in the current directory, for a specific runtime and target framework:</span><span class="sxs-lookup"><span data-stu-id="8cb83-215">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="8cb83-216">Pubblicare il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="8cb83-216">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="8cb83-217">Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), solo il progetto radice durante l'operazione di ripristino:</span><span class="sxs-lookup"><span data-stu-id="8cb83-217">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="8cb83-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cb83-218">See also</span></span>

- [<span data-ttu-id="8cb83-219">Panoramica della pubblicazione delle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="8cb83-219">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="8cb83-220">Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET CorePublish .NET Core apps with the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="8cb83-220">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="8cb83-221">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="8cb83-221">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="8cb83-222">Catalogo dei runtime IDentifier (RID)</span><span class="sxs-lookup"><span data-stu-id="8cb83-222">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="8cb83-223">Lavorare con la notarizzazione di catalina di macOS</span><span class="sxs-lookup"><span data-stu-id="8cb83-223">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="8cb83-224">Struttura di directory di un'applicazione pubblicata</span><span class="sxs-lookup"><span data-stu-id="8cb83-224">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
- [<span data-ttu-id="8cb83-225">Riferimenti alla riga di comando di MSBuild</span><span class="sxs-lookup"><span data-stu-id="8cb83-225">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="8cb83-226">Profili di pubblicazione di Visual Studio (pubxml) per la distribuzione di app ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8cb83-226">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="8cb83-227">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="8cb83-227">dotnet msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="8cb83-228">ILLInk.Tasks</span><span class="sxs-lookup"><span data-stu-id="8cb83-228">ILLInk.Tasks</span></span>](https://aka.ms/dotnet-illink)
