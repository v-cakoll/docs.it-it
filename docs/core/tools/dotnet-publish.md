---
title: Comando dotnet publish
description: Il dotnet publish comando pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: cf41ee09244faad03feb8ccda19135b8c7780106
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156998"
---
# <a name="dotnet-publish"></a><span data-ttu-id="462e2-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="462e2-103">dotnet publish</span></span>

<span data-ttu-id="462e2-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="462e2-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="462e2-105">Nome</span><span class="sxs-lookup"><span data-stu-id="462e2-105">Name</span></span>

<span data-ttu-id="462e2-106">`dotnet publish`: pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.</span><span class="sxs-lookup"><span data-stu-id="462e2-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="462e2-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="462e2-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration] 
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="462e2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="462e2-108">Description</span></span>

<span data-ttu-id="462e2-109">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="462e2-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="462e2-110">L'output include gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="462e2-110">The output includes the following assets:</span></span>

- <span data-ttu-id="462e2-111">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="462e2-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="462e2-112">Un file con *estensione Deps. JSON* che include tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="462e2-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="462e2-113">Un file *. runtimeconfig. JSON* che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime, ad esempio Garbage Collection tipo.</span><span class="sxs-lookup"><span data-stu-id="462e2-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="462e2-114">Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="462e2-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="462e2-115">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="462e2-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="462e2-116">È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="462e2-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="462e2-117">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="462e2-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span>

## <a name="arguments"></a><span data-ttu-id="462e2-118">Argomenti</span><span class="sxs-lookup"><span data-stu-id="462e2-118">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="462e2-119">Progetto o soluzione da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="462e2-119">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="462e2-120">`PROJECT` è il percorso e il nome file [C#](csproj.md)di F#un file di progetto, o Visual Basic, oppure il percorso di una directory che C#contiene F#un file di progetto, o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="462e2-120">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="462e2-121">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="462e2-121">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="462e2-122">`SOLUTION` è il percorso e il nome file di un file di soluzione (estensione*sln* ) o il percorso di una directory che contiene un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="462e2-122">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="462e2-123">Se la directory non è specificata, il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="462e2-123">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="462e2-124">**Disponibile a partire da .NET Core 3,0 SDK.**</span><span class="sxs-lookup"><span data-stu-id="462e2-124">**Available starting with .NET Core 3.0 SDK.**</span></span> 

## <a name="options"></a><span data-ttu-id="462e2-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="462e2-125">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="462e2-126">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="462e2-126">Defines the build configuration.</span></span> <span data-ttu-id="462e2-127">Il valore predefinito per la maggior parte dei progetti è `Debug`, ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.</span><span class="sxs-lookup"><span data-stu-id="462e2-127">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="462e2-128">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="462e2-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="462e2-129">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="462e2-129">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="462e2-130">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="462e2-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="462e2-131">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="462e2-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="462e2-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="462e2-132">Prints out a short help for the command.</span></span>

- <span data-ttu-id="462e2-133">**`--interactive`** **disponibile a partire da .NET Core 3,0 SDK.**</span><span class="sxs-lookup"><span data-stu-id="462e2-133">**`--interactive`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="462e2-134">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="462e2-134">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="462e2-135">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="462e2-135">For example, to complete authentication.</span></span> 

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="462e2-136">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="462e2-136">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="462e2-137">Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="462e2-137">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="462e2-138">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="462e2-138">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="462e2-139">Non compila il progetto prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="462e2-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="462e2-140">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="462e2-140">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="462e2-141">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="462e2-141">Ignores project-to-project references and only restores the root project.</span></span>

- <span data-ttu-id="462e2-142">**`--nologo`** **disponibile a partire da .NET Core 3,0 SDK.**</span><span class="sxs-lookup"><span data-stu-id="462e2-142">**`--nologo`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="462e2-143">Non visualizza il messaggio di avvio né il messaggio di copyright.</span><span class="sxs-lookup"><span data-stu-id="462e2-143">Doesn't display the startup banner or the copyright message.</span></span> 

- **`--no-restore`**

  <span data-ttu-id="462e2-144">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="462e2-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="462e2-145">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="462e2-145">Specifies the path for the output directory.</span></span> <span data-ttu-id="462e2-146">Se non specificato, il valore predefinito è *./bin/[Configuration]/[Framework]/Publish/* per un file eseguibile dipendente dal runtime e file binari multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="462e2-146">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="462e2-147">Per impostazione predefinita, il valore predefinito è *./bin/[Configuration]/[Framework]/[Runtime]/Publish/* per un file eseguibile autonomo.</span><span class="sxs-lookup"><span data-stu-id="462e2-147">It defaults to *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="462e2-148">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="462e2-148">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="462e2-149">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="462e2-149">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="462e2-150">Il valore predefinito è `true` se viene specificato un identificatore di Runtime.</span><span class="sxs-lookup"><span data-stu-id="462e2-150">Default is `true` if a runtime identifier is specified.</span></span> <span data-ttu-id="462e2-151">Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="462e2-151">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- <span data-ttu-id="462e2-152">**`--no-self-contained`** **disponibile a partire da .NET Core 3,0 SDK.**  </span><span class="sxs-lookup"><span data-stu-id="462e2-152">**`--no-self-contained`**  **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="462e2-153">È equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="462e2-153">Equivalent to `--self-contained false`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="462e2-154">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="462e2-154">Publishes the application for a given runtime.</span></span> <span data-ttu-id="462e2-155">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="462e2-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="462e2-156">Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="462e2-156">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="462e2-157">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="462e2-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="462e2-158">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="462e2-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="462e2-159">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="462e2-159">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="462e2-160">Esempi</span><span class="sxs-lookup"><span data-stu-id="462e2-160">Examples</span></span>

- <span data-ttu-id="462e2-161">Creare un [file binario multipiattaforma dipendente dal runtime](../deploying/index.md#produce-a-cross-platform-binary) per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="462e2-161">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="462e2-162">A partire da .NET Core 3,0 SDK, questo esempio crea anche un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per la piattaforma corrente.</span><span class="sxs-lookup"><span data-stu-id="462e2-162">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="462e2-163">Creare un [eseguibile indipendente](../deploying/index.md#publish-self-contained) per il progetto nella directory corrente, per un runtime specifico:</span><span class="sxs-lookup"><span data-stu-id="462e2-163">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="462e2-164">Il RID deve trovarsi nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="462e2-164">The RID must be in the project file.</span></span>

- <span data-ttu-id="462e2-165">Creare un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per il progetto nella directory corrente, per una piattaforma specifica:</span><span class="sxs-lookup"><span data-stu-id="462e2-165">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="462e2-166">Il RID deve trovarsi nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="462e2-166">The RID must be in the project file.</span></span> <span data-ttu-id="462e2-167">Questo esempio si applica a .NET Core 3,0 SDK e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="462e2-167">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="462e2-168">Pubblicare il progetto nella directory corrente, per un runtime e un Framework di destinazione specifici:</span><span class="sxs-lookup"><span data-stu-id="462e2-168">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="462e2-169">Pubblicare il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="462e2-169">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="462e2-170">Pubblicare l'applicazione corrente, ma non ripristinare i riferimenti da progetto a progetto (P2P), solo il progetto radice durante l'operazione di ripristino:</span><span class="sxs-lookup"><span data-stu-id="462e2-170">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="462e2-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="462e2-171">See also</span></span>

- [<span data-ttu-id="462e2-172">Panoramica della pubblicazione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="462e2-172">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="462e2-173">Pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="462e2-173">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="462e2-174">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="462e2-174">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="462e2-175">Catalogo RID (Runtime IDentifier)</span><span class="sxs-lookup"><span data-stu-id="462e2-175">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- <span data-ttu-id="462e2-176">[Uso dell'autenticazione di MacOS Catalina](../install/macos-notarization-issues.md) Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="462e2-176">[Working with macOS Catalina Notarization](../install/macos-notarization-issues.md) For more information, see he following resources:</span></span>
- [<span data-ttu-id="462e2-177">Struttura di directory di un'applicazione pubblicata</span><span class="sxs-lookup"><span data-stu-id="462e2-177">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
