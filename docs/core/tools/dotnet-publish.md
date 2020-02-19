---
title: Comando dotnet publish
description: Il comando dotnet publish consente di pubblicare il progetto .NET Core in una directory.
ms.date: 05/29/2018
ms.openlocfilehash: 0653a7b1e1abd6d7ffd3d21a0410279235b43a28
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451292"
---
# <a name="dotnet-publish"></a><span data-ttu-id="4d9c3-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4d9c3-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4d9c3-104">Name</span><span class="sxs-lookup"><span data-stu-id="4d9c3-104">Name</span></span>

<span data-ttu-id="4d9c3-105">`dotnet publish`: inserisce l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema host.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4d9c3-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4d9c3-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="4d9c3-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4d9c3-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20"></a>[<span data-ttu-id="4d9c3-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4d9c3-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="4d9c3-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4d9c3-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="4d9c3-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d9c3-110">Description</span></span>

<span data-ttu-id="4d9c3-111">`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="4d9c3-112">L'output include gli asset seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d9c3-112">The output includes the following assets:</span></span>

- <span data-ttu-id="4d9c3-113">Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="4d9c3-114">File *.deps.json* che contiene tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="4d9c3-115">File *.runtimeconfig.json* che specifica il runtime condiviso previsto dall'applicazione e altre opzioni di configurazione per il runtime, ad esempio il tipo di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-115">*.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="4d9c3-116">Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="4d9c3-117">L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="4d9c3-118">È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="4d9c3-119">A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="4d9c3-120">Per altre informazioni, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="4d9c3-121">Per la struttura di directory di un'applicazione pubblicata, vedere [Directory structure](/aspnet/core/hosting/directory-structure) (Struttura di directory).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="4d9c3-122">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4d9c3-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="4d9c3-123">Progetto da pubblicare.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-123">The project to publish.</span></span> <span data-ttu-id="4d9c3-124">Si tratta del percorso e del nome di un file di progetto [C#](csproj.md), F# o Visual Basic oppure del percorso di una directory contenente un file di progetto C#, F# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="4d9c3-125">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="4d9c3-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4d9c3-126">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="4d9c3-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4d9c3-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="4d9c3-128">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-128">Defines the build configuration.</span></span> <span data-ttu-id="4d9c3-129">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="4d9c3-130">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="4d9c3-131">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="4d9c3-132">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="4d9c3-133">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="4d9c3-134">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="4d9c3-135">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="4d9c3-136">Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="4d9c3-137">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="4d9c3-138">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="4d9c3-139">Non compila il progetto prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="4d9c3-140">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="4d9c3-141">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="4d9c3-142">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4d9c3-143">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="4d9c3-144">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="4d9c3-145">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="4d9c3-146">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="4d9c3-147">Se viene specificato un identificatore di runtime, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="4d9c3-148">Per altre informazioni sui diversi tipi di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="4d9c3-149">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="4d9c3-150">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="4d9c3-151">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="4d9c3-152">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="4d9c3-153">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4d9c3-154">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="4d9c3-155">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="4d9c3-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4d9c3-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="4d9c3-157">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-157">Defines the build configuration.</span></span> <span data-ttu-id="4d9c3-158">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="4d9c3-159">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="4d9c3-160">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="4d9c3-161">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="4d9c3-162">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="4d9c3-163">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="4d9c3-164">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="4d9c3-165">Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="4d9c3-166">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="4d9c3-167">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="4d9c3-168">Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="4d9c3-169">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4d9c3-170">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="4d9c3-171">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="4d9c3-172">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="4d9c3-173">Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="4d9c3-174">Se viene specificato un identificatore di runtime, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="4d9c3-175">Per altre informazioni sui diversi tipi di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="4d9c3-176">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="4d9c3-177">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="4d9c3-178">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="4d9c3-179">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="4d9c3-180">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4d9c3-181">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="4d9c3-182">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="4d9c3-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4d9c3-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="4d9c3-184">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-184">Defines the build configuration.</span></span> <span data-ttu-id="4d9c3-185">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="4d9c3-186">Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="4d9c3-187">È necessario specificare il framework di destinazione nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="4d9c3-188">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="4d9c3-189">Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="4d9c3-190">Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="4d9c3-191">Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="4d9c3-192">Questa opzione è disponibile a partire da .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4d9c3-193">Specifica il percorso della directory di output.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="4d9c3-194">Se non specificato, il percorso predefinito sarà *./bin/[configuration]/[framework]/publish/* per una distribuzione dipendente da framework o *./bin/[configuration]/[framework]/[runtime]/publish/* per una distribuzione indipendente.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="4d9c3-195">Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="4d9c3-196">Pubblica l'applicazione per un determinato runtime.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="4d9c3-197">Viene usato durante la creazione di una [distribuzione indipendente (SCD, Self-Contained Deployment)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="4d9c3-198">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="4d9c3-199">L'impostazione predefinita prevede la pubblicazione di una [distribuzione dipendente da framework (FDD, Framework-Dependent Deployment)](../deploying/index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="4d9c3-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="4d9c3-200">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4d9c3-201">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="4d9c3-202">Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="4d9c3-203">Esempi</span><span class="sxs-lookup"><span data-stu-id="4d9c3-203">Examples</span></span>

<span data-ttu-id="4d9c3-204">Pubblicare il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="4d9c3-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="4d9c3-205">Pubblicare l'applicazione usando il file di progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="4d9c3-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="4d9c3-206">Pubblicare il progetto nella directory corrente usando il framework `netcoreapp1.1`:</span><span class="sxs-lookup"><span data-stu-id="4d9c3-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="4d9c3-207">Pubblicare l'applicazione corrente usando il framework `netcoreapp1.1` e il runtime per `OS X 10.10`. Questo identificatore di runtime deve essere elencato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4d9c3-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="4d9c3-208">Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), soltanto il progetto radice durante l'operazione di ripristino (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="4d9c3-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="4d9c3-209">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d9c3-209">See also</span></span>

- [<span data-ttu-id="4d9c3-210">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="4d9c3-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="4d9c3-211">Catalogo RID (Runtime IDentifier)</span><span class="sxs-lookup"><span data-stu-id="4d9c3-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
