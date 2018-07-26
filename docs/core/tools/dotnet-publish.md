---
title: Comando dotnet publish - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet publish consente di pubblicare il progetto .NET Core in una directory.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 38224aa8472f99df107e523667e18892384a20b0
ms.sourcegitcommit: f6343b070f3c66877338a05c8bfb0be9985255e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2018
ms.locfileid: "39220672"
---
# <a name="dotnet-publish"></a><span data-ttu-id="f6833-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f6833-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f6833-104">nome</span><span class="sxs-lookup"><span data-stu-id="f6833-104">Name</span></span>

<span data-ttu-id="f6833-105">`dotnet publish`: inserisce l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema host.</span><span class="sxs-lookup"><span data-stu-id="f6833-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f6833-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f6833-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f6833-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f6833-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f6833-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f6833-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f6833-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f6833-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="f6833-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6833-110">Description</span></span>

<span data-ttu-id="f6833-111">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="f6833-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="f6833-112">L'output include gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6833-112">The output includes the following assets:</span></span>

* <span data-ttu-id="f6833-113">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="f6833-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="f6833-114">File *.deps.json* che contiene tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="f6833-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="f6833-115">File *.runtime.config.json* che specifica il runtime condiviso previsto dall'applicazione e altre opzioni di configurazione per il runtime, ad esempio il tipo di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f6833-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="f6833-116">Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="f6833-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="f6833-117">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f6833-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="f6833-118">È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f6833-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="f6833-119">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="f6833-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="f6833-120">Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="f6833-121">Per la struttura di directory di un'applicazione pubblicata, vedere [Directory structure](/aspnet/core/hosting/directory-structure) (Struttura di directory).</span><span class="sxs-lookup"><span data-stu-id="f6833-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="f6833-122">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f6833-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="f6833-123">Progetto da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="f6833-123">The project to publish.</span></span> <span data-ttu-id="f6833-124">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f6833-124">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="f6833-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f6833-125">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f6833-126">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f6833-126">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f6833-127">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f6833-127">Defines the build configuration.</span></span> <span data-ttu-id="f6833-128">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="f6833-128">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f6833-129">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="f6833-129">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="f6833-130">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="f6833-130">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="f6833-131">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f6833-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="f6833-132">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="f6833-132">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="f6833-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-133">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="f6833-134">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="f6833-134">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="f6833-135">Il file manifesto fa parte dell'output del comando [ `dotnet store` ](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-135">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="f6833-136">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="f6833-136">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="f6833-137">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f6833-137">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="f6833-138">Non compila il progetto prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f6833-138">Doesn't build the project before publishing.</span></span> <span data-ttu-id="f6833-139">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="f6833-139">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="f6833-140">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="f6833-140">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="f6833-141">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-141">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f6833-142">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="f6833-142">Specifies the path for the output directory.</span></span> <span data-ttu-id="f6833-143">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="f6833-143">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="f6833-144">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="f6833-144">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="f6833-145">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f6833-145">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="f6833-146">Se viene specificato un identificatore di runtime, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f6833-146">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="f6833-147">Per altre informazioni sui diversi tipi di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-147">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="f6833-148">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="f6833-148">Publishes the application for a given runtime.</span></span> <span data-ttu-id="f6833-149">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="f6833-149">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="f6833-150">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-150">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="f6833-151">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="f6833-151">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f6833-152">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-152">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f6833-153">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f6833-153">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="f6833-154">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="f6833-154">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f6833-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f6833-155">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f6833-156">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f6833-156">Defines the build configuration.</span></span> <span data-ttu-id="f6833-157">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="f6833-157">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f6833-158">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="f6833-158">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="f6833-159">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="f6833-159">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="f6833-160">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f6833-160">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="f6833-161">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="f6833-161">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="f6833-162">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-162">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="f6833-163">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="f6833-163">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="f6833-164">Il file manifesto fa parte dell'output del comando [ `dotnet store` ](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-164">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="f6833-165">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="f6833-165">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="f6833-166">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f6833-166">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="f6833-167">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="f6833-167">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="f6833-168">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f6833-169">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="f6833-169">Specifies the path for the output directory.</span></span> <span data-ttu-id="f6833-170">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="f6833-170">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="f6833-171">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="f6833-171">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="f6833-172">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f6833-172">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="f6833-173">Se viene specificato un identificatore di runtime, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f6833-173">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="f6833-174">Per altre informazioni sui diversi tipi di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-174">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="f6833-175">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="f6833-175">Publishes the application for a given runtime.</span></span> <span data-ttu-id="f6833-176">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="f6833-176">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="f6833-177">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="f6833-178">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="f6833-178">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f6833-179">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f6833-180">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f6833-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="f6833-181">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="f6833-181">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f6833-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f6833-182">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f6833-183">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f6833-183">Defines the build configuration.</span></span> <span data-ttu-id="f6833-184">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="f6833-184">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f6833-185">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="f6833-185">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="f6833-186">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="f6833-186">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="f6833-187">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-187">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="f6833-188">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="f6833-188">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="f6833-189">Il file manifesto fa parte dell'output del comando [ `dotnet store` ](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-189">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="f6833-190">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="f6833-190">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="f6833-191">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f6833-191">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f6833-192">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="f6833-192">Specifies the path for the output directory.</span></span> <span data-ttu-id="f6833-193">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="f6833-193">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="f6833-194">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="f6833-194">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="f6833-195">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="f6833-195">Publishes the application for a given runtime.</span></span> <span data-ttu-id="f6833-196">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="f6833-196">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="f6833-197">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f6833-197">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="f6833-198">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="f6833-198">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f6833-199">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="f6833-199">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f6833-200">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="f6833-200">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="f6833-201">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="f6833-201">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="f6833-202">Esempi</span><span class="sxs-lookup"><span data-stu-id="f6833-202">Examples</span></span>

<span data-ttu-id="f6833-203">Pubblicare il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="f6833-203">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="f6833-204">Pubblicare l'applicazione usando il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="f6833-204">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="f6833-205">Pubblicare il progetto nella directory corrente usando il framework `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="f6833-205">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="f6833-206">Pubblicare l'applicazione corrente usando il framework `netcoreapp1.1` e il runtime per `OS X 10.10`. Questo identificatore di runtime deve essere elencato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="f6833-206">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="f6833-207">Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), soltanto il progetto radice durante l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="f6833-207">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="f6833-208">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6833-208">See also</span></span>

* [<span data-ttu-id="f6833-209">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="f6833-209">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="f6833-210">Catalogo RID (Runtime IDentifier)</span><span class="sxs-lookup"><span data-stu-id="f6833-210">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
