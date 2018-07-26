---
title: Comando dotnet run - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet run offre un modo pratico per eseguire l'applicazione dal codice sorgente.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 609ac27f21e6801992b9e10c7d465a805492859e
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245252"
---
# <a name="dotnet-run"></a><span data-ttu-id="89bc0-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="89bc0-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="89bc0-104">nome</span><span class="sxs-lookup"><span data-stu-id="89bc0-104">Name</span></span>

<span data-ttu-id="89bc0-105">`dotnet run`: esegue il codice sorgente senza comandi espliciti di compilazione o avvio.</span><span class="sxs-lookup"><span data-stu-id="89bc0-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="89bc0-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="89bc0-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89bc0-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89bc0-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89bc0-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89bc0-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89bc0-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89bc0-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="89bc0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89bc0-110">Description</span></span>

<span data-ttu-id="89bc0-111">Il comando `dotnet run` offre un modo pratico per eseguire l'applicazione dal codice sorgente con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="89bc0-112">Questo comando è utile per lo sviluppo iterativo veloce dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="89bc0-113">Il comando dipende dal comando [`dotnet build`](dotnet-build.md) per compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="89bc0-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="89bc0-114">I requisiti per la compilazione, ad esempio il ripristino preliminare del progetto, si applicano anche a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="89bc0-115">I file di output vengono scritti nel percorso predefinito, ovvero `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="89bc0-116">Se ad esempio si ha un'applicazione `netcoreapp1.0` e si esegue `dotnet run`, l'output viene inserito in `bin/Debug/netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-116">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="89bc0-117">I file vengono sovrascritti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="89bc0-117">Files are overwritten as needed.</span></span> <span data-ttu-id="89bc0-118">I file temporanei vengono inseriti nella directory `obj`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="89bc0-119">Se il progetto specifica più framework, l'esecuzione di `dotnet run` genera un errore a meno che non venga usata l'opzione `-f|--framework <FRAMEWORK>` per specificare il framework.</span><span class="sxs-lookup"><span data-stu-id="89bc0-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="89bc0-120">Il comando `dotnet run` viene usato nel contesto dei progetti e non di assembly di compilazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="89bc0-121">Se in alternativa si prova a eseguire la DLL di un'applicazione dipendente da framework, è necessario usare [dotnet](dotnet.md) senza un comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="89bc0-122">Ad esempio, per eseguire `myapp.dll`, usare:</span><span class="sxs-lookup"><span data-stu-id="89bc0-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="89bc0-123">Per altre informazioni sul driver `dotnet`, vedere l'argomento [Strumenti dell'interfaccia della riga di comando di .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="89bc0-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="89bc0-124">Per eseguire l'applicazione, il comando `dotnet run` risolve le dipendenze dell'applicazione esterne al runtime condiviso dalla cache NuGet.</span><span class="sxs-lookup"><span data-stu-id="89bc0-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="89bc0-125">È consigliabile non per usare `dotnet run` per eseguire le applicazioni nell'ambiente di produzione perché questo comando usa dipendenze memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="89bc0-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="89bc0-126">In alternativa, [creare una distribuzione](../deploying/index.md) usando il comando [`dotnet publish`](dotnet-publish.md) e distribuire l'output pubblicato.</span><span class="sxs-lookup"><span data-stu-id="89bc0-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="89bc0-127">Opzioni</span><span class="sxs-lookup"><span data-stu-id="89bc0-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89bc0-128">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89bc0-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="89bc0-129">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="89bc0-130">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="89bc0-131">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-131">Defines the build configuration.</span></span> <span data-ttu-id="89bc0-132">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="89bc0-133">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="89bc0-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="89bc0-134">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="89bc0-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="89bc0-135">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="89bc0-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="89bc0-136">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="89bc0-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="89bc0-137">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="89bc0-138">Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="89bc0-139">I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="89bc0-140">Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).</span><span class="sxs-lookup"><span data-stu-id="89bc0-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="89bc0-141">Non compila il progetto prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-141">Doesn't build the project before running.</span></span> <span data-ttu-id="89bc0-142">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="89bc0-143">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="89bc0-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="89bc0-144">Non tenta di usare *launchSettings.json* per configurare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="89bc0-145">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="89bc0-146">Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo.</span><span class="sxs-lookup"><span data-stu-id="89bc0-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="89bc0-147">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="89bc0-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="89bc0-148">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="89bc0-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="89bc0-149">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="89bc0-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="89bc0-150">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="89bc0-151">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89bc0-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89bc0-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="89bc0-153">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="89bc0-154">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="89bc0-155">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-155">Defines the build configuration.</span></span> <span data-ttu-id="89bc0-156">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="89bc0-157">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="89bc0-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="89bc0-158">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="89bc0-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="89bc0-159">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="89bc0-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="89bc0-160">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="89bc0-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="89bc0-161">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="89bc0-162">Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="89bc0-163">I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="89bc0-164">Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).</span><span class="sxs-lookup"><span data-stu-id="89bc0-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="89bc0-165">Non compila il progetto prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-165">Doesn't build the project before running.</span></span> <span data-ttu-id="89bc0-166">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="89bc0-167">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="89bc0-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="89bc0-168">Non tenta di usare *launchSettings.json* per configurare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="89bc0-169">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="89bc0-170">Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo.</span><span class="sxs-lookup"><span data-stu-id="89bc0-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="89bc0-171">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="89bc0-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="89bc0-172">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="89bc0-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="89bc0-173">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="89bc0-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89bc0-174">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89bc0-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="89bc0-175">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="89bc0-176">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="89bc0-177">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="89bc0-177">Defines the build configuration.</span></span> <span data-ttu-id="89bc0-178">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="89bc0-179">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="89bc0-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="89bc0-180">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="89bc0-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="89bc0-181">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="89bc0-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="89bc0-182">Specifica il percorso e il nome del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="89bc0-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="89bc0-183">Vedere la nota. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="89bc0-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="89bc0-184">Usare il percorso e il nome del file di progetto con l'opzione `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="89bc0-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="89bc0-185">Una regressione nell'interfaccia della riga di comando impedisce di specificare un percorso di cartella con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="89bc0-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="89bc0-186">Per altre informazioni su questo problema, vedere [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, non è possibile avviare un progetto (dotnet/cli #5992)).</span><span class="sxs-lookup"><span data-stu-id="89bc0-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="89bc0-187">Esempi</span><span class="sxs-lookup"><span data-stu-id="89bc0-187">Examples</span></span>

<span data-ttu-id="89bc0-188">Eseguire il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="89bc0-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="89bc0-189">Eseguire il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="89bc0-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="89bc0-190">Eseguire il progetto nella directory corrente. L'argomento `--help` in questo esempio viene passato all'applicazione perché viene usata l'opzione `--` vuota:</span><span class="sxs-lookup"><span data-stu-id="89bc0-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="89bc0-191">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente visualizzando solo il risultato minimo, quindi eseguire il progetto: (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="89bc0-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`