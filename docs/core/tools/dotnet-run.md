---
title: Comando dotnet run
description: Il comando dotnet run offre un modo pratico per eseguire l'applicazione dal codice sorgente.
ms.date: 02/19/2020
ms.openlocfilehash: e442ed56d676ffd189ef6d394d840cea671c2dc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157076"
---
# <a name="dotnet-run"></a><span data-ttu-id="95f5c-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="95f5c-103">dotnet run</span></span>

<span data-ttu-id="95f5c-104">**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="95f5c-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="95f5c-105">Nome</span><span class="sxs-lookup"><span data-stu-id="95f5c-105">Name</span></span>

<span data-ttu-id="95f5c-106">`dotnet run`: esegue il codice sorgente senza comandi espliciti di compilazione o avvio.</span><span class="sxs-lookup"><span data-stu-id="95f5c-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="95f5c-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="95f5c-107">Synopsis</span></span>

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile]
    [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project]
    [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

## <a name="description"></a><span data-ttu-id="95f5c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95f5c-108">Description</span></span>

<span data-ttu-id="95f5c-109">Il comando `dotnet run` offre un modo pratico per eseguire l'applicazione dal codice sorgente con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="95f5c-109">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="95f5c-110">Questo comando è utile per lo sviluppo iterativo veloce dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="95f5c-110">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="95f5c-111">Il comando dipende [`dotnet build`](dotnet-build.md) dal comando per compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="95f5c-111">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="95f5c-112">I requisiti per la compilazione, ad esempio il ripristino preliminare del progetto, si applicano anche a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-112">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="95f5c-113">I file di output vengono scritti nel percorso predefinito, ovvero `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-113">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="95f5c-114">Se ad esempio si ha un'applicazione `netcoreapp2.1` e si esegue `dotnet run`, l'output viene inserito in `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-114">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="95f5c-115">I file vengono sovrascritti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="95f5c-115">Files are overwritten as needed.</span></span> <span data-ttu-id="95f5c-116">I file temporanei vengono inseriti nella directory `obj`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-116">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="95f5c-117">Se il progetto specifica più framework, l'esecuzione di `dotnet run` genera un errore a meno che non venga usata l'opzione `-f|--framework <FRAMEWORK>` per specificare il framework.</span><span class="sxs-lookup"><span data-stu-id="95f5c-117">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="95f5c-118">Il comando `dotnet run` viene usato nel contesto dei progetti e non di assembly di compilazione.</span><span class="sxs-lookup"><span data-stu-id="95f5c-118">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="95f5c-119">Se in alternativa si prova a eseguire la DLL di un'applicazione dipendente da framework, è necessario usare [dotnet](dotnet.md) senza un comando.</span><span class="sxs-lookup"><span data-stu-id="95f5c-119">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="95f5c-120">Ad esempio, per eseguire `myapp.dll`, usare:</span><span class="sxs-lookup"><span data-stu-id="95f5c-120">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="95f5c-121">Per altre informazioni sul driver `dotnet`, vedere l'argomento [Strumenti dell'interfaccia della riga di comando di .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="95f5c-121">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="95f5c-122">Per eseguire l'applicazione, il comando `dotnet run` risolve le dipendenze dell'applicazione esterne al runtime condiviso dalla cache NuGet.</span><span class="sxs-lookup"><span data-stu-id="95f5c-122">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="95f5c-123">È consigliabile non per usare `dotnet run` per eseguire le applicazioni nell'ambiente di produzione perché questo comando usa dipendenze memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="95f5c-123">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="95f5c-124">In alternativa, [creare una distribuzione](../deploying/index.md) usando il comando [`dotnet publish`](dotnet-publish.md) e distribuire l'output pubblicato.</span><span class="sxs-lookup"><span data-stu-id="95f5c-124">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="95f5c-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="95f5c-125">Options</span></span>

- **`--`**

  <span data-ttu-id="95f5c-126">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95f5c-126">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="95f5c-127">Tutti gli argomenti dopo questo delimitatore vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95f5c-127">All arguments after this delimiter are passed to the application run.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="95f5c-128">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="95f5c-128">Defines the build configuration.</span></span> <span data-ttu-id="95f5c-129">L'impostazione predefinita `Debug`per la maggior parte dei progetti è , ma è possibile eseguire l'override delle impostazioni di configurazione della compilazione nel progetto.</span><span class="sxs-lookup"><span data-stu-id="95f5c-129">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="95f5c-130">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="95f5c-130">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="95f5c-131">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="95f5c-131">The framework must be specified in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="95f5c-132">Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="95f5c-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="95f5c-133">La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="95f5c-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="95f5c-134">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="95f5c-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="95f5c-135">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).</span><span class="sxs-lookup"><span data-stu-id="95f5c-135">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="95f5c-136">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="95f5c-136">Available since .NET Core 3.0 SDK.</span></span>

- **`--launch-profile <NAME>`**

  <span data-ttu-id="95f5c-137">Il nome del profilo di avvio, se presente, da usare all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="95f5c-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="95f5c-138">I profili di avvio sono definiti nel `Development`file `Staging` *launchSettings.json* e sono in genere denominati , , e `Production`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="95f5c-139">Per ulteriori informazioni, consultate [Operazioni con più ambienti.](/aspnet/core/fundamentals/environments)</span><span class="sxs-lookup"><span data-stu-id="95f5c-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

- **`--no-build`**

  <span data-ttu-id="95f5c-140">Non compila il progetto prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95f5c-140">Doesn't build the project before running.</span></span> <span data-ttu-id="95f5c-141">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-141">It also implicit sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="95f5c-142">Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="95f5c-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--no-launch-profile`**

  <span data-ttu-id="95f5c-143">Non tenta di usare *launchSettings.json* per configurare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="95f5c-143">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

- **`--no-restore`**

  <span data-ttu-id="95f5c-144">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="95f5c-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-p|--project <PATH>`**

  <span data-ttu-id="95f5c-145">Specifica il percorso del file di progetto da eseguire: nome della cartella o percorso completo.</span><span class="sxs-lookup"><span data-stu-id="95f5c-145">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="95f5c-146">Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="95f5c-146">If not specified, it defaults to the current directory.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="95f5c-147">Specifica il runtime di destinazione per cui ripristinare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="95f5c-147">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="95f5c-148">Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="95f5c-148">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="95f5c-149">`-r`breve opzione disponibile dopo .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="95f5c-149">`-r` short option available since .NET Core 3.0 SDK.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="95f5c-150">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="95f5c-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="95f5c-151">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="95f5c-152">Il valore predefinito è `m`.</span><span class="sxs-lookup"><span data-stu-id="95f5c-152">The default value is `m`.</span></span> <span data-ttu-id="95f5c-153">Disponibile da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="95f5c-153">Available since .NET Core 2.1 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="95f5c-154">Esempi</span><span class="sxs-lookup"><span data-stu-id="95f5c-154">Examples</span></span>

- <span data-ttu-id="95f5c-155">Eseguire il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="95f5c-155">Run the project in the current directory:</span></span>

  ```dotnetcli
  dotnet run
  ```

- <span data-ttu-id="95f5c-156">Eseguire il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="95f5c-156">Run the specified project:</span></span>

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- <span data-ttu-id="95f5c-157">Eseguire il progetto nella directory corrente. L'argomento `--help` in questo esempio viene passato all'applicazione perché viene usata l'opzione `--` vuota:</span><span class="sxs-lookup"><span data-stu-id="95f5c-157">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- <span data-ttu-id="95f5c-158">Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente visualizzando solo il risultato minimo, quindi eseguire il progetto: (.NET Core SDK 2.0 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="95f5c-158">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

  ```dotnetcli
  dotnet run --verbosity m
  ```
