---
title: Comando dotnet
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
ms.date: 06/04/2018
ms.openlocfilehash: 328fd24cd72110bd235c177398f6f147fbb9d144
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373743"
---
# <a name="dotnet-command"></a><span data-ttu-id="18bf8-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="18bf8-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="18bf8-104">Name</span><span class="sxs-lookup"><span data-stu-id="18bf8-104">Name</span></span>

<span data-ttu-id="18bf8-105">`dotnet`: uno strumento per la gestione dei file binari e del codice sorgente di .NET.</span><span class="sxs-lookup"><span data-stu-id="18bf8-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="18bf8-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="18bf8-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18bf8-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18bf8-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18bf8-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18bf8-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18bf8-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18bf8-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="18bf8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18bf8-110">Description</span></span>

<span data-ttu-id="18bf8-111">`dotnet` è uno strumento per la gestione dei file binari e del codice sorgente di .NET.</span><span class="sxs-lookup"><span data-stu-id="18bf8-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="18bf8-112">Espone i comandi che eseguono attività specifiche, come ad esempio [`dotnet build`](dotnet-build.md) e [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="18bf8-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="18bf8-113">Ogni comando definisce i propri argomenti.</span><span class="sxs-lookup"><span data-stu-id="18bf8-113">Each command defines its own arguments.</span></span> <span data-ttu-id="18bf8-114">Digitare `--help` dopo ogni comando per accedere a una breve documentazione della Guida.</span><span class="sxs-lookup"><span data-stu-id="18bf8-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="18bf8-115">`dotnet` può essere usato per eseguire le applicazioni specificando una DLL dell'applicazione, come ad esempio `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="18bf8-116">Per informazioni sulle opzioni di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="18bf8-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="18bf8-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="18bf8-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18bf8-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18bf8-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="18bf8-119">Percorso di un file *.deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="18bf8-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="18bf8-120">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="18bf8-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="18bf8-121">Percorso di un file *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="18bf8-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="18bf8-122">Un file *deps.json* contiene un elenco di dipendenze, le dipendenze di compilazione e le informazioni sulla versione usate per risolvere i conflitti di assembly.</span><span class="sxs-lookup"><span data-stu-id="18bf8-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="18bf8-123">Per altre informazioni su questo file, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="18bf8-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="18bf8-124">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="18bf8-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="18bf8-125">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="18bf8-126">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="18bf8-127">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="18bf8-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="18bf8-128">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18bf8-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="18bf8-129">Visualizza i runtime di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="18bf8-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="18bf8-130">Visualizza i .NET Core SDK installati.</span><span class="sxs-lookup"><span data-stu-id="18bf8-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="18bf8-131">Definisce il comportamento quando il framework condiviso richiesto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="18bf8-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="18bf8-132">`N` può essere:</span><span class="sxs-lookup"><span data-stu-id="18bf8-132">`N` can be:</span></span>
- <span data-ttu-id="18bf8-133">`0` - Disabilitare anche il roll forward per la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="18bf8-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="18bf8-134">`1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale.</span><span class="sxs-lookup"><span data-stu-id="18bf8-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="18bf8-135">Comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="18bf8-135">This is the default behavior.</span></span>
- <span data-ttu-id="18bf8-136">`2` - Eseguire il roll forward per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="18bf8-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="18bf8-137">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="18bf8-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="18bf8-138">Percorso di un file *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="18bf8-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="18bf8-139">Un file *runtimeconfig.json* è un file di configurazione contenente le impostazioni di configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="18bf8-140">Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="18bf8-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18bf8-141">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="18bf8-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18bf8-142">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="18bf8-143">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="18bf8-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="18bf8-144">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="18bf8-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18bf8-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18bf8-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="18bf8-146">Percorso di un file *.deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="18bf8-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="18bf8-147">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="18bf8-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="18bf8-148">Percorso di un file *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="18bf8-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="18bf8-149">Un file *deps.json* contiene un elenco di dipendenze, le dipendenze di compilazione e le informazioni sulla versione usate per risolvere i conflitti di assembly.</span><span class="sxs-lookup"><span data-stu-id="18bf8-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="18bf8-150">Per altri dettagli su questo file, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="18bf8-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="18bf8-151">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="18bf8-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="18bf8-152">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="18bf8-153">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="18bf8-154">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="18bf8-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="18bf8-155">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18bf8-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="18bf8-156">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="18bf8-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="18bf8-157">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="18bf8-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="18bf8-158">Percorso di un file *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="18bf8-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="18bf8-159">Un file *runtimeconfig.json* è un file di configurazione contenente le impostazioni di configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="18bf8-160">Per altri dettagli, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="18bf8-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18bf8-161">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="18bf8-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18bf8-162">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="18bf8-163">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="18bf8-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="18bf8-164">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="18bf8-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18bf8-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18bf8-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="18bf8-166">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="18bf8-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="18bf8-167">Percorso di un file *deps.json*.</span><span class="sxs-lookup"><span data-stu-id="18bf8-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="18bf8-168">Un file *deps.json* contiene un elenco di dipendenze, le dipendenze di compilazione e le informazioni sulla versione usate per risolvere i conflitti di assembly.</span><span class="sxs-lookup"><span data-stu-id="18bf8-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="18bf8-169">Per altri dettagli su questo file, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="18bf8-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="18bf8-170">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="18bf8-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="18bf8-171">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="18bf8-172">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="18bf8-173">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="18bf8-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="18bf8-174">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18bf8-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="18bf8-175">Percorso di un file *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="18bf8-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="18bf8-176">Un file *runtimeconfig.json* è un file di configurazione contenente le impostazioni di configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="18bf8-177">Per altri dettagli, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="18bf8-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18bf8-178">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="18bf8-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18bf8-179">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="18bf8-180">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="18bf8-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="18bf8-181">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="18bf8-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="18bf8-182">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="18bf8-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="18bf8-183">Generale</span><span class="sxs-lookup"><span data-stu-id="18bf8-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18bf8-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18bf8-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="18bf8-185">Comando</span><span class="sxs-lookup"><span data-stu-id="18bf8-185">Command</span></span>                                       | <span data-ttu-id="18bf8-186">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="18bf8-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="18bf8-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="18bf8-188">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18bf8-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="18bf8-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="18bf8-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="18bf8-190">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="18bf8-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="18bf8-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="18bf8-192">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="18bf8-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="18bf8-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="18bf8-194">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="18bf8-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="18bf8-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="18bf8-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="18bf8-196">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="18bf8-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="18bf8-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="18bf8-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="18bf8-198">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="18bf8-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="18bf8-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="18bf8-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="18bf8-200">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="18bf8-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="18bf8-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="18bf8-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="18bf8-202">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="18bf8-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="18bf8-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="18bf8-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="18bf8-204">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="18bf8-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="18bf8-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="18bf8-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="18bf8-206">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="18bf8-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="18bf8-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="18bf8-208">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="18bf8-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="18bf8-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="18bf8-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="18bf8-210">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="18bf8-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="18bf8-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="18bf8-212">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="18bf8-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="18bf8-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="18bf8-214">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="18bf8-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18bf8-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18bf8-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="18bf8-216">Comando</span><span class="sxs-lookup"><span data-stu-id="18bf8-216">Command</span></span>                             | <span data-ttu-id="18bf8-217">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="18bf8-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="18bf8-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="18bf8-219">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18bf8-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="18bf8-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="18bf8-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="18bf8-221">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="18bf8-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="18bf8-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="18bf8-223">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="18bf8-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="18bf8-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="18bf8-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="18bf8-225">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="18bf8-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="18bf8-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="18bf8-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="18bf8-227">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="18bf8-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="18bf8-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="18bf8-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="18bf8-229">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="18bf8-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="18bf8-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="18bf8-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="18bf8-231">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="18bf8-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="18bf8-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="18bf8-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="18bf8-233">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="18bf8-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="18bf8-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="18bf8-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="18bf8-235">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="18bf8-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="18bf8-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="18bf8-237">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="18bf8-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="18bf8-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="18bf8-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="18bf8-239">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="18bf8-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="18bf8-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="18bf8-241">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="18bf8-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="18bf8-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="18bf8-243">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="18bf8-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18bf8-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18bf8-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="18bf8-245">Comando</span><span class="sxs-lookup"><span data-stu-id="18bf8-245">Command</span></span>                             | <span data-ttu-id="18bf8-246">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="18bf8-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="18bf8-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="18bf8-248">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18bf8-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="18bf8-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="18bf8-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="18bf8-250">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="18bf8-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="18bf8-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="18bf8-252">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="18bf8-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="18bf8-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="18bf8-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="18bf8-254">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="18bf8-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="18bf8-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="18bf8-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="18bf8-256">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="18bf8-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="18bf8-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="18bf8-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="18bf8-258">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="18bf8-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="18bf8-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="18bf8-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="18bf8-260">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="18bf8-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="18bf8-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="18bf8-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="18bf8-262">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="18bf8-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="18bf8-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="18bf8-264">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="18bf8-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="18bf8-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="18bf8-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="18bf8-266">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="18bf8-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="18bf8-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="18bf8-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="18bf8-268">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="18bf8-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="18bf8-269">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="18bf8-269">Project references</span></span>

<span data-ttu-id="18bf8-270">Comando</span><span class="sxs-lookup"><span data-stu-id="18bf8-270">Command</span></span> | <span data-ttu-id="18bf8-271">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-271">Function</span></span>
--- | ---
[<span data-ttu-id="18bf8-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="18bf8-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="18bf8-273">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="18bf8-273">Adds a project reference.</span></span>
[<span data-ttu-id="18bf8-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="18bf8-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="18bf8-275">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="18bf8-275">Lists project references.</span></span>
[<span data-ttu-id="18bf8-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="18bf8-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="18bf8-277">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="18bf8-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="18bf8-278">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="18bf8-278">NuGet packages</span></span>

<span data-ttu-id="18bf8-279">Comando</span><span class="sxs-lookup"><span data-stu-id="18bf8-279">Command</span></span> | <span data-ttu-id="18bf8-280">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-280">Function</span></span>
--- | ---
[<span data-ttu-id="18bf8-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="18bf8-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="18bf8-282">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="18bf8-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="18bf8-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="18bf8-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="18bf8-284">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="18bf8-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="18bf8-285">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="18bf8-285">NuGet commands</span></span>

<span data-ttu-id="18bf8-286">Comando</span><span class="sxs-lookup"><span data-stu-id="18bf8-286">Command</span></span> | <span data-ttu-id="18bf8-287">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-287">Function</span></span>
--- | ---
[<span data-ttu-id="18bf8-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="18bf8-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="18bf8-289">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="18bf8-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="18bf8-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="18bf8-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="18bf8-291">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="18bf8-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="18bf8-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="18bf8-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="18bf8-293">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="18bf8-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="18bf8-294">Comandi degli strumenti globali</span><span class="sxs-lookup"><span data-stu-id="18bf8-294">Global Tools commands</span></span>

<span data-ttu-id="18bf8-295">Gli [strumenti globali .NET Core](global-tools.md) sono disponibili a partire da .NET Core SDK 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="18bf8-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="18bf8-296">Comando</span><span class="sxs-lookup"><span data-stu-id="18bf8-296">Command</span></span> | <span data-ttu-id="18bf8-297">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-297">Function</span></span>
--- | ---
[<span data-ttu-id="18bf8-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="18bf8-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="18bf8-299">Installa uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="18bf8-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="18bf8-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="18bf8-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="18bf8-301">Elenca tutti gli strumenti globali attualmente installati nella directory predefinita nel computer o nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="18bf8-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="18bf8-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="18bf8-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="18bf8-303">Disinstalla uno strumento globale dal computer.</span><span class="sxs-lookup"><span data-stu-id="18bf8-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="18bf8-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="18bf8-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="18bf8-305">Aggiorna uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="18bf8-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="18bf8-306">Strumenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="18bf8-306">Additional tools</span></span>

<span data-ttu-id="18bf8-307">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="18bf8-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="18bf8-308">Tali strumenti sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="18bf8-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="18bf8-309">Strumento</span><span class="sxs-lookup"><span data-stu-id="18bf8-309">Tool</span></span>                                              | <span data-ttu-id="18bf8-310">Funzione</span><span class="sxs-lookup"><span data-stu-id="18bf8-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="18bf8-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="18bf8-311">dev-certs</span></span>                                         | <span data-ttu-id="18bf8-312">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="18bf8-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="18bf8-313">ef</span><span class="sxs-lookup"><span data-stu-id="18bf8-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="18bf8-314">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="18bf8-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="18bf8-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="18bf8-315">sql-cache</span></span>                                         | <span data-ttu-id="18bf8-316">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18bf8-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="18bf8-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="18bf8-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="18bf8-318">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="18bf8-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="18bf8-319">watch</span><span class="sxs-lookup"><span data-stu-id="18bf8-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="18bf8-320">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="18bf8-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="18bf8-321">Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="18bf8-322">Esempi</span><span class="sxs-lookup"><span data-stu-id="18bf8-322">Examples</span></span>

<span data-ttu-id="18bf8-323">Creare una nuova applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="18bf8-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="18bf8-324">Ripristinare le dipendenze per una determinata applicazione:</span><span class="sxs-lookup"><span data-stu-id="18bf8-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="18bf8-325">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="18bf8-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="18bf8-326">Eseguire una DLL dell'applicazione, ad esempio `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="18bf8-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="18bf8-327">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="18bf8-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18bf8-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18bf8-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="18bf8-329">La cartella dei pacchetti globali.</span><span class="sxs-lookup"><span data-stu-id="18bf8-329">The global packages folder.</span></span> <span data-ttu-id="18bf8-330">Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="18bf8-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="18bf8-331">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="18bf8-332">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18bf8-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="18bf8-333">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="18bf8-334">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="18bf8-335">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="18bf8-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="18bf8-336">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="18bf8-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="18bf8-337">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="18bf8-338">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="18bf8-339">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="18bf8-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="18bf8-340">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="18bf8-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="18bf8-341">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="18bf8-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18bf8-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18bf8-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="18bf8-343">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="18bf8-343">The primary package cache.</span></span> <span data-ttu-id="18bf8-344">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="18bf8-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="18bf8-345">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="18bf8-346">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18bf8-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="18bf8-347">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="18bf8-348">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="18bf8-349">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="18bf8-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="18bf8-350">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="18bf8-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="18bf8-351">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="18bf8-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="18bf8-352">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="18bf8-353">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="18bf8-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18bf8-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18bf8-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="18bf8-355">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="18bf8-355">The primary package cache.</span></span> <span data-ttu-id="18bf8-356">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="18bf8-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="18bf8-357">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="18bf8-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="18bf8-358">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18bf8-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="18bf8-359">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="18bf8-360">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="18bf8-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="18bf8-361">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="18bf8-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="18bf8-362">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18bf8-362">See also</span></span>

- <span data-ttu-id="18bf8-363">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)</span><span class="sxs-lookup"><span data-stu-id="18bf8-363">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)</span></span>
