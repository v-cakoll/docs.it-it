---
title: Comando dotnet run
description: Il comando dotnet run offre un modo pratico per eseguire l'applicazione dal codice sorgente.
ms.date: 10/31/2019
ms.openlocfilehash: 5920f0d1f04204b286fdf6f51f5fd13644846390
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734112"
---
# <a name="dotnet-run"></a><span data-ttu-id="a053c-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="a053c-103">dotnet run</span></span>

<span data-ttu-id="a053c-104">**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="a053c-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="a053c-105">Name</span><span class="sxs-lookup"><span data-stu-id="a053c-105">Name</span></span>

<span data-ttu-id="a053c-106">`dotnet run`: esegue il codice sorgente senza comandi espliciti di compilazione o avvio.</span><span class="sxs-lookup"><span data-stu-id="a053c-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a053c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a053c-107">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="a053c-108">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a053c-108">.NET Core 3.0</span></span>](#tab/netcore30)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a053c-109">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a053c-109">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a053c-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a053c-110">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a053c-111">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a053c-111">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="a053c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a053c-112">Description</span></span>

<span data-ttu-id="a053c-113">Il comando `dotnet run` offre un modo pratico per eseguire l'applicazione dal codice sorgente con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-113">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="a053c-114">Questo comando è utile per lo sviluppo iterativo veloce dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-114">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="a053c-115">Il comando dipende dal comando [`dotnet build`](dotnet-build.md) per compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="a053c-115">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="a053c-116">I requisiti per la compilazione, ad esempio il ripristino preliminare del progetto, si applicano anche a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a053c-116">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="a053c-117">I file di output vengono scritti nel percorso predefinito, ovvero `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="a053c-117">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="a053c-118">Se ad esempio si ha un'applicazione `netcoreapp2.1` e si esegue `dotnet run`, l'output viene inserito in `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="a053c-118">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="a053c-119">I file vengono sovrascritti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a053c-119">Files are overwritten as needed.</span></span> <span data-ttu-id="a053c-120">I file temporanei vengono inseriti nella directory `obj`.</span><span class="sxs-lookup"><span data-stu-id="a053c-120">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="a053c-121">Se il progetto specifica più framework, l'esecuzione di `dotnet run` genera un errore a meno che non venga usata l'opzione `-f|--framework <FRAMEWORK>` per specificare il framework.</span><span class="sxs-lookup"><span data-stu-id="a053c-121">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="a053c-122">Il comando `dotnet run` viene usato nel contesto dei progetti e non di assembly di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-122">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="a053c-123">Se in alternativa si prova a eseguire la DLL di un'applicazione dipendente da framework, è necessario usare [dotnet](dotnet.md) senza un comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-123">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="a053c-124">Ad esempio, per eseguire `myapp.dll`, usare:</span><span class="sxs-lookup"><span data-stu-id="a053c-124">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="a053c-125">Per altre informazioni sul driver `dotnet`, vedere l'argomento [Strumenti dell'interfaccia della riga di comando di .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="a053c-125">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="a053c-126">Per eseguire l'applicazione, il comando `dotnet run` risolve le dipendenze dell'applicazione esterne al runtime condiviso dalla cache NuGet.</span><span class="sxs-lookup"><span data-stu-id="a053c-126">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="a053c-127">È consigliabile non per usare `dotnet run` per eseguire le applicazioni nell'ambiente di produzione perché questo comando usa dipendenze memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="a053c-127">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="a053c-128">In alternativa, [creare una distribuzione](../deploying/index.md) usando il comando [`dotnet publish`](dotnet-publish.md) e distribuire l'output pubblicato.</span><span class="sxs-lookup"><span data-stu-id="a053c-128">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="a053c-129">Options</span><span class="sxs-lookup"><span data-stu-id="a053c-129">Options</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="a053c-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a053c-130">.NET Core 3.0</span></span>](#tab/netcore30)

`--`

<span data-ttu-id="a053c-131">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-131">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="a053c-132">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-132">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a053c-133">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-133">Defines the build configuration.</span></span> <span data-ttu-id="a053c-134">Il valore predefinito per la maggior parte dei progetti è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="a053c-134">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a053c-135">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="a053c-135">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="a053c-136">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a053c-136">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="a053c-137">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a053c-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="a053c-138">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="a053c-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="a053c-139">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-139">Prints out a short help for the command.</span></span>

`--interactive`

<span data-ttu-id="a053c-140">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="a053c-140">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="a053c-141">Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-141">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="a053c-142">I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`.</span><span class="sxs-lookup"><span data-stu-id="a053c-142">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="a053c-143">Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).</span><span class="sxs-lookup"><span data-stu-id="a053c-143">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="a053c-144">Non compila il progetto prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-144">Doesn't build the project before running.</span></span> <span data-ttu-id="a053c-145">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="a053c-145">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="a053c-146">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a053c-146">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="a053c-147">Non tenta di usare *launchSettings.json* per configurare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-147">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="a053c-148">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-148">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="a053c-149">Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo.</span><span class="sxs-lookup"><span data-stu-id="a053c-149">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="a053c-150">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a053c-150">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="a053c-151">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="a053c-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="a053c-152">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a053c-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a053c-153">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a053c-154">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a053c-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a053c-155">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a053c-155">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="a053c-156">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-156">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="a053c-157">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-157">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a053c-158">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-158">Defines the build configuration.</span></span> <span data-ttu-id="a053c-159">Il valore predefinito per la maggior parte dei progetti è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="a053c-159">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a053c-160">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="a053c-160">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="a053c-161">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a053c-161">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="a053c-162">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a053c-162">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="a053c-163">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="a053c-163">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="a053c-164">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-164">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="a053c-165">Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-165">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="a053c-166">I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`.</span><span class="sxs-lookup"><span data-stu-id="a053c-166">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="a053c-167">Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).</span><span class="sxs-lookup"><span data-stu-id="a053c-167">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="a053c-168">Non compila il progetto prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-168">Doesn't build the project before running.</span></span> <span data-ttu-id="a053c-169">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="a053c-169">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="a053c-170">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a053c-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="a053c-171">Non tenta di usare *launchSettings.json* per configurare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-171">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="a053c-172">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-172">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="a053c-173">Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo.</span><span class="sxs-lookup"><span data-stu-id="a053c-173">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="a053c-174">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a053c-174">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="a053c-175">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="a053c-175">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="a053c-176">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a053c-176">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a053c-177">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-177">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a053c-178">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a053c-178">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a053c-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a053c-179">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="a053c-180">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-180">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="a053c-181">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-181">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a053c-182">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-182">Defines the build configuration.</span></span> <span data-ttu-id="a053c-183">Il valore predefinito per la maggior parte dei progetti è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="a053c-183">The default for most projects value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a053c-184">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="a053c-184">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="a053c-185">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a053c-185">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="a053c-186">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a053c-186">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="a053c-187">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="a053c-187">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="a053c-188">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-188">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="a053c-189">Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-189">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="a053c-190">I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`.</span><span class="sxs-lookup"><span data-stu-id="a053c-190">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="a053c-191">Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).</span><span class="sxs-lookup"><span data-stu-id="a053c-191">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="a053c-192">Non compila il progetto prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-192">Doesn't build the project before running.</span></span> <span data-ttu-id="a053c-193">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="a053c-193">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="a053c-194">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a053c-194">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="a053c-195">Non tenta di usare *launchSettings.json* per configurare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-195">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="a053c-196">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-196">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="a053c-197">Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo.</span><span class="sxs-lookup"><span data-stu-id="a053c-197">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="a053c-198">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a053c-198">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="a053c-199">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="a053c-199">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="a053c-200">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="a053c-200">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a053c-201">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a053c-201">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="a053c-202">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-202">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="a053c-203">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a053c-203">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a053c-204">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a053c-204">Defines the build configuration.</span></span> <span data-ttu-id="a053c-205">Il valore predefinito per la maggior parte dei progetti è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="a053c-205">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a053c-206">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="a053c-206">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="a053c-207">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a053c-207">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="a053c-208">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a053c-208">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="a053c-209">Specifica il percorso e il nome del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="a053c-209">Specifies the path and name of the project file.</span></span> <span data-ttu-id="a053c-210">(Vedere la nota). Se non specificato, viene impostato come predefinito la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a053c-210">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="a053c-211">Usare il percorso e il nome del file di progetto con l'opzione `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="a053c-211">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="a053c-212">Una regressione nell'interfaccia della riga di comando impedisce di specificare un percorso di cartella con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="a053c-212">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="a053c-213">Per altre informazioni su questo problema, vedere [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, non è possibile avviare un progetto (dotnet/cli #5992)).</span><span class="sxs-lookup"><span data-stu-id="a053c-213">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="a053c-214">Esempi</span><span class="sxs-lookup"><span data-stu-id="a053c-214">Examples</span></span>

<span data-ttu-id="a053c-215">Eseguire il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a053c-215">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="a053c-216">Eseguire il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="a053c-216">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="a053c-217">Eseguire il progetto nella directory corrente. L'argomento `--help` in questo esempio viene passato all'applicazione perché viene usata l'opzione `--` vuota:</span><span class="sxs-lookup"><span data-stu-id="a053c-217">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="a053c-218">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente visualizzando solo il risultato minimo, quindi eseguire il progetto: (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="a053c-218">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
