---
title: Comando dotnet-run - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-run offre un modo pratico per eseguire l'applicazione dal codice sorgente.
keywords: dotnet-run, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f0a6fce4f83808076b7cbcabdaa948badde2cf80
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-run"></a><span data-ttu-id="9a827-104">dotnet-run</span><span class="sxs-lookup"><span data-stu-id="9a827-104">dotnet-run</span></span>

## <a name="name"></a><span data-ttu-id="9a827-105">Nome</span><span class="sxs-lookup"><span data-stu-id="9a827-105">Name</span></span> 

<span data-ttu-id="9a827-106">`dotnet-run`: esegue il codice sorgente senza comandi espliciti di compilazione o avvio.</span><span class="sxs-lookup"><span data-stu-id="9a827-106">`dotnet-run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9a827-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9a827-107">Synopsis</span></span>

`dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]] [-h|--help]`

## <a name="description"></a><span data-ttu-id="9a827-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a827-108">Description</span></span>

<span data-ttu-id="9a827-109">Il comando `dotnet run` offre un modo pratico per eseguire l'applicazione dal codice sorgente con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="9a827-109">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="9a827-110">Questo comando è utile per lo sviluppo iterativo veloce dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="9a827-110">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="9a827-111">Il comando dipende dal comando [`dotnet build`](dotnet-build.md) per compilare il codice.</span><span class="sxs-lookup"><span data-stu-id="9a827-111">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="9a827-112">I requisiti per la compilazione, ad esempio il ripristino preliminare del progetto, si applicano anche a `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="9a827-112">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span> 

<span data-ttu-id="9a827-113">I file di output vengono scritti nel percorso predefinito, ovvero `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="9a827-113">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="9a827-114">Se ad esempio si ha un'applicazione `netcoreapp1.0` e si esegue `dotnet run`, l'output viene inserito in `bin/Debug/netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="9a827-114">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="9a827-115">I file vengono sovrascritti in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9a827-115">Files are overwritten as needed.</span></span> <span data-ttu-id="9a827-116">I file temporanei vengono inseriti nella directory `obj`.</span><span class="sxs-lookup"><span data-stu-id="9a827-116">Temporary files are placed in the `obj` directory.</span></span> 

<span data-ttu-id="9a827-117">Se il progetto specifica più framework, l'esecuzione di `dotnet run` genera un errore a meno che non venga usata l'opzione `-f|--framework <FRAMEWORK>` per specificare il framework.</span><span class="sxs-lookup"><span data-stu-id="9a827-117">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="9a827-118">Il comando `dotnet run` viene usato nel contesto dei progetti e non di assembly di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9a827-118">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="9a827-119">Se in alternativa si prova a eseguire la DLL di un'applicazione dipendente da framework, è necessario usare [dotnet](dotnet.md) senza un comando.</span><span class="sxs-lookup"><span data-stu-id="9a827-119">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="9a827-120">Ad esempio, per eseguire `myapp.dll`, usare:</span><span class="sxs-lookup"><span data-stu-id="9a827-120">For example, to run `myapp.dll`, use:</span></span>
 
```
dotnet myapp.dll
```

<span data-ttu-id="9a827-121">Per altre informazioni sul driver `dotnet`, vedere l'argomento [Strumenti dell'interfaccia della riga di comando di .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="9a827-121">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="9a827-122">Per eseguire l'applicazione, il comando `dotnet run` risolve le dipendenze dell'applicazione esterne al runtime condiviso dalla cache NuGet.</span><span class="sxs-lookup"><span data-stu-id="9a827-122">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="9a827-123">È consigliabile non per usare `dotnet run` per eseguire le applicazioni nell'ambiente di produzione perché questo comando usa dipendenze memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="9a827-123">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="9a827-124">In alternativa, [creare una distribuzione](../deploying/index.md) usando il comando [`dotnet publish`](dotnet-publish.md) e distribuire l'output pubblicato.</span><span class="sxs-lookup"><span data-stu-id="9a827-124">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span> 

## <a name="options"></a><span data-ttu-id="9a827-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9a827-125">Options</span></span>

`--`

<span data-ttu-id="9a827-126">Delimita gli argomenti a `dotnet run` dagli argomenti per l'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9a827-126">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="9a827-127">Tutti gli argomenti dopo questo vengono passati all'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9a827-127">All arguments after this one are passed to the application run.</span></span> 

`-h|--help`

<span data-ttu-id="9a827-128">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="9a827-128">Prints out a short help for the command.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="9a827-129">Configurazione da usare per la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="9a827-129">Configuration to use for building the project.</span></span> <span data-ttu-id="9a827-130">Il valore predefinito è `Debug`.</span><span class="sxs-lookup"><span data-stu-id="9a827-130">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="9a827-131">Compila ed esegue l'app usando il [framework](../../standard/frameworks.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="9a827-131">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="9a827-132">Il framework deve essere specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="9a827-132">The framework must be specified in the project file.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="9a827-133">Specifica il percorso e il nome del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="9a827-133">Specifies the path and name of the project file.</span></span> <span data-ttu-id="9a827-134">Vedere la nota. Se non specificato, per impostazione predefinita il percorso corrisponde alla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="9a827-134">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="9a827-135">Usare il percorso e il nome del file di progetto con l'opzione `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="9a827-135">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="9a827-136">Una regressione nell'interfaccia della riga di comando impedisce di specificare un percorso di cartella in questo momento.</span><span class="sxs-lookup"><span data-stu-id="9a827-136">A regression in the CLI prevents providing a folder path at this time.</span></span> <span data-ttu-id="9a827-137">Per altre informazioni e per tenere traccia di questo problema, vedere [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, non è possibile avviare un progetto (dotnet/cli #5992)).</span><span class="sxs-lookup"><span data-stu-id="9a827-137">For more information and to track this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

## <a name="examples"></a><span data-ttu-id="9a827-138">Esempi</span><span class="sxs-lookup"><span data-stu-id="9a827-138">Examples</span></span>

<span data-ttu-id="9a827-139">Eseguire il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="9a827-139">Run the project in the current directory:</span></span>

`dotnet run` 

<span data-ttu-id="9a827-140">Eseguire il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="9a827-140">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="9a827-141">Eseguire il progetto nella directory corrente. L'argomento `--help` in questo esempio viene passato all'applicazione perché viene usato l'argomento `--`:</span><span class="sxs-lookup"><span data-stu-id="9a827-141">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

