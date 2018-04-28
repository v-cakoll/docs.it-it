---
title: Comando dotnet run - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet run offre un modo pratico per eseguire l'applicazione dal codice sorgente.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 18ceb395ed025fa562f295fc2facd00c67a75536
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-run"></a><span data-ttu-id="bb13d-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bb13d-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="bb13d-104">nome</span><span class="sxs-lookup"><span data-stu-id="bb13d-104">Name</span></span>

<span data-ttu-id="bb13d-105">`dotnet run`: esegue il codice sorgente senza comandi espliciti di compilazione o avvio.</span><span class="sxs-lookup"><span data-stu-id="bb13d-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bb13d-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="bb13d-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bb13d-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bb13d-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bb13d-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bb13d-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="bb13d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb13d-109">Description</span></span>

<span data-ttu-id="bb13d-110">Il comando `dotnet run` offre un modo pratico per eseguire l'applicazione dal codice sorgente con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="bb13d-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="bb13d-111">Questo comando è utile per lo sviluppo iterativo veloce dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="bb13d-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="bb13d-112">Il comando dipende dal comando [`dotnet build`](dotnet-build.md) per compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="bb13d-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="bb13d-113">I requisiti per la compilazione, ad esempio il ripristino preliminare del progetto, si applicano anche a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="bb13d-114">I file di output vengono scritti nel percorso predefinito, ovvero `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="bb13d-115">Se ad esempio si ha un'applicazione `netcoreapp1.0` e si esegue `dotnet run`, l'output viene inserito in `bin/Debug/netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="bb13d-116">I file vengono sovrascritti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="bb13d-116">Files are overwritten as needed.</span></span> <span data-ttu-id="bb13d-117">I file temporanei vengono inseriti nella directory `obj`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-117">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="bb13d-118">Se il progetto specifica più framework, l'esecuzione di `dotnet run` genera un errore a meno che non venga usata l'opzione `-f|--framework <FRAMEWORK>` per specificare il framework.</span><span class="sxs-lookup"><span data-stu-id="bb13d-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="bb13d-119">Il comando `dotnet run` viene usato nel contesto dei progetti e non di assembly di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="bb13d-120">Se in alternativa si prova a eseguire la DLL di un'applicazione dipendente da framework, è necessario usare [dotnet](dotnet.md) senza un comando.</span><span class="sxs-lookup"><span data-stu-id="bb13d-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="bb13d-121">Ad esempio, per eseguire `myapp.dll`, usare:</span><span class="sxs-lookup"><span data-stu-id="bb13d-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="bb13d-122">Per altre informazioni sul driver `dotnet`, vedere l'argomento [Strumenti dell'interfaccia della riga di comando di .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="bb13d-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="bb13d-123">Per eseguire l'applicazione, il comando `dotnet run` risolve le dipendenze dell'applicazione esterne al runtime condiviso dalla cache NuGet.</span><span class="sxs-lookup"><span data-stu-id="bb13d-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="bb13d-124">È consigliabile non per usare `dotnet run` per eseguire le applicazioni nell'ambiente di produzione perché questo comando usa dipendenze memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="bb13d-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="bb13d-125">In alternativa, [creare una distribuzione](../deploying/index.md) usando il comando [`dotnet publish`](dotnet-publish.md) e distribuire l'output pubblicato.</span><span class="sxs-lookup"><span data-stu-id="bb13d-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="bb13d-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bb13d-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bb13d-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bb13d-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="bb13d-128">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="bb13d-129">Tutti gli argomenti dopo questo vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="bb13d-130">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-130">Defines the build configuration.</span></span> <span data-ttu-id="bb13d-131">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="bb13d-132">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="bb13d-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bb13d-133">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="bb13d-133">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="bb13d-134">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bb13d-134">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="bb13d-135">Ciò equivale a eliminare *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="bb13d-135">This is equivalent to deleting *project.assets.json*.</span></span>

`-h|--help`

<span data-ttu-id="bb13d-136">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="bb13d-136">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="bb13d-137">Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="bb13d-138">I profili di avvio vengono definiti nel file *launchSettings.json* e in genere vengono denominati `Development`, `Staging` e `Production`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="bb13d-139">Per altre informazioni, vedere [Working with multiple environments](/aspnet/core/fundamentals/environments) (Utilizzo con più ambienti).</span><span class="sxs-lookup"><span data-stu-id="bb13d-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="bb13d-140">Non compila il progetto prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-140">Doesn't build the project before running.</span></span>

`--no-dependencies`

<span data-ttu-id="bb13d-141">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="bb13d-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="bb13d-142">Non tenta di usare *launchSettings.json* per configurare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-142">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="bb13d-143">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="bb13d-143">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="bb13d-144">Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo.</span><span class="sxs-lookup"><span data-stu-id="bb13d-144">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="bb13d-145">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="bb13d-145">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="bb13d-146">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="bb13d-146">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="bb13d-147">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="bb13d-147">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bb13d-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bb13d-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="bb13d-149">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-149">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="bb13d-150">Tutti gli argomenti dopo questo vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-150">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="bb13d-151">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bb13d-151">Defines the build configuration.</span></span> <span data-ttu-id="bb13d-152">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-152">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="bb13d-153">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="bb13d-153">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="bb13d-154">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="bb13d-154">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="bb13d-155">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="bb13d-155">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="bb13d-156">Specifica il percorso e il nome del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="bb13d-156">Specifies the path and name of the project file.</span></span> <span data-ttu-id="bb13d-157">Vedere la nota. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="bb13d-157">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="bb13d-158">Usare il percorso e il nome del file di progetto con l'opzione `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="bb13d-158">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="bb13d-159">Una regressione nell'interfaccia della riga di comando impedisce di specificare un percorso di cartella con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="bb13d-159">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="bb13d-160">Per altre informazioni su questo problema, vedere [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, non è possibile avviare un progetto (dotnet/cli #5992)).</span><span class="sxs-lookup"><span data-stu-id="bb13d-160">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="bb13d-161">Esempi</span><span class="sxs-lookup"><span data-stu-id="bb13d-161">Examples</span></span>

<span data-ttu-id="bb13d-162">Eseguire il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="bb13d-162">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="bb13d-163">Eseguire il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="bb13d-163">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="bb13d-164">Eseguire il progetto nella directory corrente. L'argomento `--help` in questo esempio viene passato all'applicazione perché viene usato l'argomento `--`:</span><span class="sxs-lookup"><span data-stu-id="bb13d-164">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="bb13d-165">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente visualizzando solo il risultato minimo, quindi eseguire il progetto: (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="bb13d-165">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`