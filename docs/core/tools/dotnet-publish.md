---
title: Comando dotnet publish
description: Il comando dotnet publish pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: 7e57a7b3cfe72653cc64c90055735795e4616260
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523760"
---
# <a name="dotnet-publish"></a><span data-ttu-id="2ee6b-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2ee6b-103">dotnet publish</span></span>

<span data-ttu-id="2ee6b-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ee6b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="2ee6b-105">Nome</span><span class="sxs-lookup"><span data-stu-id="2ee6b-105">Name</span></span>

<span data-ttu-id="2ee6b-106">`dotnet publish`- Pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.- Publishes the application and its dependencies to a folder for deployment to a hosting system.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2ee6b-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2ee6b-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="2ee6b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ee6b-108">Description</span></span>

<span data-ttu-id="2ee6b-109">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="2ee6b-110">L'output include gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ee6b-110">The output includes the following assets:</span></span>

- <span data-ttu-id="2ee6b-111">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="2ee6b-112">Un file *.deps.json* che include tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="2ee6b-113">Un file *.runtimeconfig.json* che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime (ad esempio, tipo di Garbage Collection).</span><span class="sxs-lookup"><span data-stu-id="2ee6b-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="2ee6b-114">Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="2ee6b-115">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="2ee6b-116">È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="2ee6b-117">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span>

## <a name="arguments"></a><span data-ttu-id="2ee6b-118">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2ee6b-118">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="2ee6b-119">Progetto o soluzione da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-119">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="2ee6b-120">`PROJECT`è il percorso e il nome del file di un file di progetto di [C,](csproj.md)F o Visual Basic oppure il percorso di una directory che contiene un file di progetto C, F o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-120">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="2ee6b-121">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-121">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="2ee6b-122">`SOLUTION`è il percorso e il nome file di un file di soluzione (estensione*sln)* o il percorso di una directory che contiene un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-122">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="2ee6b-123">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-123">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="2ee6b-124">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-124">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="2ee6b-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2ee6b-125">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="2ee6b-126">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-126">Defines the build configuration.</span></span> <span data-ttu-id="2ee6b-127">L'impostazione predefinita `Debug`per la maggior parte dei progetti è , ma è possibile eseguire l'override delle impostazioni di configurazione della compilazione nel progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-127">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="2ee6b-128">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2ee6b-129">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-129">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="2ee6b-130">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2ee6b-131">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2ee6b-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="2ee6b-133">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="2ee6b-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="2ee6b-134">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-134">For example, to complete authentication.</span></span> <span data-ttu-id="2ee6b-135">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-135">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="2ee6b-136">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-136">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="2ee6b-137">Il file manifesto fa parte [ `dotnet store` ](dotnet-store.md)dell'output del comando .</span><span class="sxs-lookup"><span data-stu-id="2ee6b-137">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="2ee6b-138">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-138">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="2ee6b-139">Non compila il progetto prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="2ee6b-140">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-140">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="2ee6b-141">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-141">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="2ee6b-142">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-142">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="2ee6b-143">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2ee6b-144">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="2ee6b-145">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-145">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="2ee6b-146">Se non specificato, il valore predefinito è *[project_file_folder]./bin/[configuration]/[framework]/publish/* per un eseguibile dipendente dal runtime e file binari multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-146">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="2ee6b-147">Il valore predefinito è *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* per un eseguibile autonomo.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-147">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  - <span data-ttu-id="2ee6b-148">.NET Core 3.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ee6b-148">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="2ee6b-149">Se viene specificato un percorso relativo durante la pubblicazione di un progetto, la directory di output generata è relativa alla directory di lavoro corrente, non al percorso del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-149">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="2ee6b-150">Se viene specificato un percorso relativo durante la pubblicazione di una soluzione, tutto l'output per tutti i progetti viene inserito nella cartella specificata rispetto alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-150">If a relative path is specified when publishing a solution, all output for all projects go into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="2ee6b-151">Per fare in modo che l'output di pubblicazione vada a `PublishDir` cartelle separate `--output` per ogni progetto, specificare un percorso relativo utilizzando la proprietà msbuild anziché l'opzione .</span><span class="sxs-lookup"><span data-stu-id="2ee6b-151">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="2ee6b-152">Ad esempio, `dotnet publish -p:PublishDir=.\publish` invia l'output `publish` di pubblicazione per ogni progetto in una cartella all'altra della cartella che contiene il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-152">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="2ee6b-153">.NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="2ee6b-153">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="2ee6b-154">Se durante la pubblicazione di un progetto viene specificato un percorso relativo, la directory di output generata è relativa al percorso del file di progetto, non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-154">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="2ee6b-155">Se viene specificato un percorso relativo durante la pubblicazione di una soluzione, l'output di ogni progetto viene inserito in una cartella separata rispetto al percorso del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-155">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="2ee6b-156">Se viene specificato un percorso assoluto durante la pubblicazione di una soluzione, tutto l'output di pubblicazione per tutti i progetti viene inserito nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-156">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="2ee6b-157">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-157">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="2ee6b-158">Il `true` valore predefinito è se viene specificato un identificatore di runtime.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-158">Default is `true` if a runtime identifier is specified.</span></span> <span data-ttu-id="2ee6b-159">Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .</span><span class="sxs-lookup"><span data-stu-id="2ee6b-159">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="2ee6b-160">È equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-160">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="2ee6b-161">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-161">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="2ee6b-162">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-162">Publishes the application for a given runtime.</span></span> <span data-ttu-id="2ee6b-163">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2ee6b-163">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="2ee6b-164">Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .</span><span class="sxs-lookup"><span data-stu-id="2ee6b-164">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="2ee6b-165">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-165">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2ee6b-166">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-166">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2ee6b-167">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-167">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="2ee6b-168">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-168">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="2ee6b-169">Esempi</span><span class="sxs-lookup"><span data-stu-id="2ee6b-169">Examples</span></span>

- <span data-ttu-id="2ee6b-170">Creare un file binario multipiattaforma dipendente dal runtime per il progetto nella directory corrente:Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span><span class="sxs-lookup"><span data-stu-id="2ee6b-170">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="2ee6b-171">A partire da .NET Core 3.0 SDK, questo esempio crea anche un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-171">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="2ee6b-172">Creare un eseguibile indipendente per il progetto nella directory corrente, per un runtime specifico:Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span><span class="sxs-lookup"><span data-stu-id="2ee6b-172">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="2ee6b-173">Il RID deve essere nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-173">The RID must be in the project file.</span></span>

- <span data-ttu-id="2ee6b-174">Creare un eseguibile dipendente dal runtime per il progetto nella directory corrente, per una piattaforma specifica:Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span><span class="sxs-lookup"><span data-stu-id="2ee6b-174">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="2ee6b-175">Il RID deve essere nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-175">The RID must be in the project file.</span></span> <span data-ttu-id="2ee6b-176">Questo esempio si applica a .NET Core 3.0 SDK e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="2ee6b-176">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="2ee6b-177">Pubblicare il progetto nella directory corrente, per un runtime e un framework di destinazione specifici:Publish the project in the current directory, for a specific runtime and target framework:</span><span class="sxs-lookup"><span data-stu-id="2ee6b-177">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="2ee6b-178">Pubblicare il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="2ee6b-178">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="2ee6b-179">Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), solo il progetto radice durante l'operazione di ripristino:</span><span class="sxs-lookup"><span data-stu-id="2ee6b-179">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="2ee6b-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ee6b-180">See also</span></span>

- [<span data-ttu-id="2ee6b-181">Panoramica della pubblicazione delle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="2ee6b-181">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="2ee6b-182">Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET CorePublish .NET Core apps with the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="2ee6b-182">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="2ee6b-183">Quadri di destinazione</span><span class="sxs-lookup"><span data-stu-id="2ee6b-183">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="2ee6b-184">Catalogo dei runtime IDentifier (RID)</span><span class="sxs-lookup"><span data-stu-id="2ee6b-184">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="2ee6b-185">Lavorare con la notarizzazione di catalina di macOS</span><span class="sxs-lookup"><span data-stu-id="2ee6b-185">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="2ee6b-186">Struttura di directory di un'applicazione pubblicata</span><span class="sxs-lookup"><span data-stu-id="2ee6b-186">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
