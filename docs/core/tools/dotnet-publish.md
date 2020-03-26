---
title: Comando dotnet publish
description: Il comando dotnet publish pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: ed5b87b3343210ca81486ef4b9a9d70d1b534464
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80110971"
---
# <a name="dotnet-publish"></a><span data-ttu-id="96e8a-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="96e8a-103">dotnet publish</span></span>

<span data-ttu-id="96e8a-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="96e8a-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="96e8a-105">Nome</span><span class="sxs-lookup"><span data-stu-id="96e8a-105">Name</span></span>

<span data-ttu-id="96e8a-106">`dotnet publish`- Pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.- Publishes the application and its dependencies to a folder for deployment to a hosting system.</span><span class="sxs-lookup"><span data-stu-id="96e8a-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="96e8a-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="96e8a-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="96e8a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96e8a-108">Description</span></span>

<span data-ttu-id="96e8a-109">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="96e8a-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="96e8a-110">L'output include gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="96e8a-110">The output includes the following assets:</span></span>

- <span data-ttu-id="96e8a-111">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="96e8a-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="96e8a-112">Un file *.deps.json* che include tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="96e8a-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="96e8a-113">Un file *.runtimeconfig.json* che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime (ad esempio, tipo di Garbage Collection).</span><span class="sxs-lookup"><span data-stu-id="96e8a-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="96e8a-114">Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="96e8a-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="96e8a-115">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="96e8a-116">È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="96e8a-117">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="96e8a-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span>

## <a name="arguments"></a><span data-ttu-id="96e8a-118">Argomenti</span><span class="sxs-lookup"><span data-stu-id="96e8a-118">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="96e8a-119">Progetto o soluzione da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="96e8a-119">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="96e8a-120">`PROJECT`è il percorso e il nome del file di un file di progetto di [C,](csproj.md)F o Visual Basic oppure il percorso di una directory che contiene un file di progetto C, F o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96e8a-120">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="96e8a-121">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="96e8a-121">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="96e8a-122">`SOLUTION`è il percorso e il nome file di un file di soluzione (estensione*sln)* o il percorso di una directory che contiene un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-122">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="96e8a-123">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="96e8a-123">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="96e8a-124">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="96e8a-124">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="96e8a-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="96e8a-125">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="96e8a-126">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-126">Defines the build configuration.</span></span> <span data-ttu-id="96e8a-127">L'impostazione predefinita `Debug`per la maggior parte dei progetti è , ma è possibile eseguire l'override delle impostazioni di configurazione della compilazione nel progetto.</span><span class="sxs-lookup"><span data-stu-id="96e8a-127">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="96e8a-128">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="96e8a-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="96e8a-129">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="96e8a-129">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="96e8a-130">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="96e8a-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="96e8a-131">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="96e8a-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="96e8a-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="96e8a-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="96e8a-133">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="96e8a-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="96e8a-134">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-134">For example, to complete authentication.</span></span> <span data-ttu-id="96e8a-135">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="96e8a-135">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="96e8a-136">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="96e8a-136">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="96e8a-137">Il file manifesto fa parte [ `dotnet store` ](dotnet-store.md)dell'output del comando .</span><span class="sxs-lookup"><span data-stu-id="96e8a-137">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="96e8a-138">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="96e8a-138">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="96e8a-139">Non compila il progetto prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="96e8a-140">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="96e8a-140">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="96e8a-141">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="96e8a-141">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="96e8a-142">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="96e8a-142">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="96e8a-143">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="96e8a-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="96e8a-144">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="96e8a-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="96e8a-145">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="96e8a-145">Specifies the path for the output directory.</span></span> <span data-ttu-id="96e8a-146">Se non specificato, il valore predefinito è *./bin/[configuration]/[framework]/publish/* per un file eseguibile dipendente dal runtime e file binari tra piattaforme.</span><span class="sxs-lookup"><span data-stu-id="96e8a-146">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="96e8a-147">Il valore predefinito è *./bin/[configuration]/[framework]/[runtime]/publish/* per un eseguibile indipendente.</span><span class="sxs-lookup"><span data-stu-id="96e8a-147">It defaults to *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="96e8a-148">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="96e8a-148">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="96e8a-149">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-149">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="96e8a-150">Il `true` valore predefinito è se viene specificato un identificatore di runtime.</span><span class="sxs-lookup"><span data-stu-id="96e8a-150">Default is `true` if a runtime identifier is specified.</span></span> <span data-ttu-id="96e8a-151">Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .</span><span class="sxs-lookup"><span data-stu-id="96e8a-151">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="96e8a-152">È equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="96e8a-152">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="96e8a-153">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="96e8a-153">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="96e8a-154">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="96e8a-154">Publishes the application for a given runtime.</span></span> <span data-ttu-id="96e8a-155">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="96e8a-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="96e8a-156">Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .</span><span class="sxs-lookup"><span data-stu-id="96e8a-156">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="96e8a-157">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="96e8a-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="96e8a-158">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="96e8a-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="96e8a-159">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="96e8a-159">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="96e8a-160">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="96e8a-160">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="96e8a-161">Esempi</span><span class="sxs-lookup"><span data-stu-id="96e8a-161">Examples</span></span>

- <span data-ttu-id="96e8a-162">Creare un file binario multipiattaforma dipendente dal runtime per il progetto nella directory corrente:Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span><span class="sxs-lookup"><span data-stu-id="96e8a-162">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="96e8a-163">A partire da .NET Core 3.0 SDK, questo esempio crea anche un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="96e8a-163">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="96e8a-164">Creare un eseguibile indipendente per il progetto nella directory corrente, per un runtime specifico:Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span><span class="sxs-lookup"><span data-stu-id="96e8a-164">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="96e8a-165">Il RID deve essere nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="96e8a-165">The RID must be in the project file.</span></span>

- <span data-ttu-id="96e8a-166">Creare un eseguibile dipendente dal runtime per il progetto nella directory corrente, per una piattaforma specifica:Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span><span class="sxs-lookup"><span data-stu-id="96e8a-166">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="96e8a-167">Il RID deve essere nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="96e8a-167">The RID must be in the project file.</span></span> <span data-ttu-id="96e8a-168">Questo esempio si applica a .NET Core 3.0 SDK e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="96e8a-168">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="96e8a-169">Pubblicare il progetto nella directory corrente, per un runtime e un framework di destinazione specifici:Publish the project in the current directory, for a specific runtime and target framework:</span><span class="sxs-lookup"><span data-stu-id="96e8a-169">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="96e8a-170">Pubblicare il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="96e8a-170">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="96e8a-171">Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), solo il progetto radice durante l'operazione di ripristino:</span><span class="sxs-lookup"><span data-stu-id="96e8a-171">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="96e8a-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96e8a-172">See also</span></span>

- [<span data-ttu-id="96e8a-173">Panoramica della pubblicazione delle applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="96e8a-173">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="96e8a-174">Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET CorePublish .NET Core apps with the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="96e8a-174">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="96e8a-175">Quadri di destinazione</span><span class="sxs-lookup"><span data-stu-id="96e8a-175">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="96e8a-176">Catalogo dei runtime IDentifier (RID)</span><span class="sxs-lookup"><span data-stu-id="96e8a-176">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="96e8a-177">Lavorare con la notarizzazione di catalina di macOS</span><span class="sxs-lookup"><span data-stu-id="96e8a-177">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="96e8a-178">Struttura di directory di un'applicazione pubblicata</span><span class="sxs-lookup"><span data-stu-id="96e8a-178">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
