---
title: Comando dotnet publish - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet publish consente di pubblicare il progetto .NET Core in una directory.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: fca05b22495f41ed85e89b077faad367a901e009
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-publish"></a><span data-ttu-id="422b5-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="422b5-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="422b5-104">nome</span><span class="sxs-lookup"><span data-stu-id="422b5-104">Name</span></span>

<span data-ttu-id="422b5-105">`dotnet publish`: inserisce l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema host.</span><span class="sxs-lookup"><span data-stu-id="422b5-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="422b5-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="422b5-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="422b5-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="422b5-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="422b5-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="422b5-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="422b5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="422b5-109">Description</span></span>

<span data-ttu-id="422b5-110">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="422b5-110">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="422b5-111">L'output conterrà quanto segue:</span><span class="sxs-lookup"><span data-stu-id="422b5-111">The output will contain the following:</span></span>

* <span data-ttu-id="422b5-112">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="422b5-112">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="422b5-113">File *.deps.json* contenente tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="422b5-113">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="422b5-114">File *.runtime.config.json* che specifica il runtime condiviso previsto dall'applicazione e altre opzioni di configurazione per il runtime, ad esempio il tipo di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="422b5-114">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="422b5-115">Dipendenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="422b5-115">The application's dependencies.</span></span> <span data-ttu-id="422b5-116">Questi dati vengono copiati dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="422b5-116">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="422b5-117">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema host (ad esempio un server, un computer PC o Mac o un laptop) per l'esecuzione. Questa è l'unica modalità supportata ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="422b5-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="422b5-118">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="422b5-118">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="422b5-119">Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="422b5-119">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="422b5-120">Per la struttura di directory di un'applicazione pubblicata, vedere [Directory structure](/aspnet/core/hosting/directory-structure) (Struttura di directory).</span><span class="sxs-lookup"><span data-stu-id="422b5-120">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="422b5-121">Argomenti</span><span class="sxs-lookup"><span data-stu-id="422b5-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="422b5-122">Progetto da pubblicare che, se non specificato, corrisponde per impostazione predefinita alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="422b5-122">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="422b5-123">Opzioni</span><span class="sxs-lookup"><span data-stu-id="422b5-123">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="422b5-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="422b5-124">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="422b5-125">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="422b5-125">Defines the build configuration.</span></span> <span data-ttu-id="422b5-126">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="422b5-126">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="422b5-127">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="422b5-127">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="422b5-128">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="422b5-128">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="422b5-129">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="422b5-129">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="422b5-130">Ciò equivale a eliminare il file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="422b5-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="422b5-131">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="422b5-131">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="422b5-132">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="422b5-132">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="422b5-133">Il file manifesto fa parte dell'output del comando [ `dotnet store` ](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="422b5-133">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="422b5-134">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="422b5-134">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="422b5-135">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="422b5-135">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="422b5-136">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="422b5-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="422b5-137">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="422b5-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="422b5-138">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="422b5-138">Specifies the path for the output directory.</span></span> <span data-ttu-id="422b5-139">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="422b5-139">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="422b5-140">Se viene specificato un percorso relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="422b5-140">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="422b5-141">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="422b5-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="422b5-142">Se viene specificato un identificatore di runtime, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="422b5-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="422b5-143">Per altre informazioni sui diversi tipi di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="422b5-143">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="422b5-144">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="422b5-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="422b5-145">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="422b5-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="422b5-146">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="422b5-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="422b5-147">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="422b5-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="422b5-148">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="422b5-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="422b5-149">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="422b5-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="422b5-150">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="422b5-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="422b5-151">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="422b5-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="422b5-152">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="422b5-152">Defines the build configuration.</span></span> <span data-ttu-id="422b5-153">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="422b5-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="422b5-154">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="422b5-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="422b5-155">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="422b5-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="422b5-156">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="422b5-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="422b5-157">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="422b5-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="422b5-158">Il file manifesto fa parte dell'output del comando [ `dotnet store` ](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="422b5-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="422b5-159">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="422b5-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="422b5-160">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="422b5-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="422b5-161">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="422b5-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="422b5-162">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="422b5-162">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="422b5-163">Se viene specificato un percorso relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="422b5-163">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="422b5-164">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="422b5-164">Publishes the application for a given runtime.</span></span> <span data-ttu-id="422b5-165">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="422b5-165">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="422b5-166">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="422b5-166">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="422b5-167">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="422b5-167">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="422b5-168">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="422b5-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="422b5-169">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="422b5-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="422b5-170">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="422b5-170">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="422b5-171">Esempi</span><span class="sxs-lookup"><span data-stu-id="422b5-171">Examples</span></span>

<span data-ttu-id="422b5-172">Pubblicare il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="422b5-172">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="422b5-173">Pubblicare l'applicazione usando il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="422b5-173">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="422b5-174">Pubblicare il progetto nella directory corrente usando il framework `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="422b5-174">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="422b5-175">Pubblicare l'applicazione corrente usando il framework `netcoreapp1.1` e il runtime per `OS X 10.10`. Questo identificatore di runtime deve essere elencato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="422b5-175">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="422b5-176">Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), soltanto il progetto radice durante l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="422b5-176">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="422b5-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="422b5-177">See also</span></span>

* [<span data-ttu-id="422b5-178">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="422b5-178">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="422b5-179">Catalogo RID (Runtime IDentifier)</span><span class="sxs-lookup"><span data-stu-id="422b5-179">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)