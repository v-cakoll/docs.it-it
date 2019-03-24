---
title: Comando dotnet
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
ms.date: 06/04/2018
ms.openlocfilehash: 107a529952cce62dac840874fa5d6d8986376adf
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185636"
---
# <a name="dotnet-command"></a><span data-ttu-id="afec5-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="afec5-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="afec5-104">nome</span><span class="sxs-lookup"><span data-stu-id="afec5-104">Name</span></span>

<span data-ttu-id="afec5-105">`dotnet`: uno strumento per la gestione dei file binari e del codice sorgente di .NET.</span><span class="sxs-lookup"><span data-stu-id="afec5-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="afec5-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="afec5-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="afec5-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="afec5-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="afec5-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="afec5-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="afec5-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="afec5-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="afec5-110">Description</span><span class="sxs-lookup"><span data-stu-id="afec5-110">Description</span></span>

<span data-ttu-id="afec5-111">`dotnet` è uno strumento per la gestione dei file binari e del codice sorgente di .NET.</span><span class="sxs-lookup"><span data-stu-id="afec5-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="afec5-112">Espone i comandi che eseguono attività specifiche, come ad esempio [`dotnet build`](dotnet-build.md) e [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="afec5-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="afec5-113">Ogni comando definisce i propri argomenti.</span><span class="sxs-lookup"><span data-stu-id="afec5-113">Each command defines its own arguments.</span></span> <span data-ttu-id="afec5-114">Digitare `--help` dopo ogni comando per accedere a una breve documentazione della Guida.</span><span class="sxs-lookup"><span data-stu-id="afec5-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="afec5-115">`dotnet` può essere usato per eseguire le applicazioni specificando una DLL dell'applicazione, come ad esempio `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="afec5-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="afec5-116">Per informazioni sulle opzioni di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="afec5-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="afec5-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="afec5-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="afec5-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="afec5-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="afec5-119">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="afec5-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="afec5-120">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="afec5-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="afec5-121">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="afec5-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="afec5-122">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="afec5-123">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="afec5-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="afec5-124">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="afec5-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="afec5-125">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="afec5-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="afec5-126">Visualizza i runtime di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="afec5-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="afec5-127">Visualizza i .NET Core SDK installati.</span><span class="sxs-lookup"><span data-stu-id="afec5-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="afec5-128">Definisce il comportamento quando il framework condiviso richiesto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afec5-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="afec5-129">`N` può essere:</span><span class="sxs-lookup"><span data-stu-id="afec5-129">`N` can be:</span></span>
* <span data-ttu-id="afec5-130">`0` - Disabilitare anche il roll forward per la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="afec5-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="afec5-131">`1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale.</span><span class="sxs-lookup"><span data-stu-id="afec5-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="afec5-132">Comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="afec5-132">This is the default behavior.</span></span>
* <span data-ttu-id="afec5-133">`2` - Eseguire il roll forward per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="afec5-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="afec5-134">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="afec5-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="afec5-135">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="afec5-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="afec5-136">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="afec5-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="afec5-137">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afec5-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="afec5-138">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="afec5-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="afec5-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="afec5-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="afec5-140">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="afec5-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="afec5-141">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="afec5-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="afec5-142">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="afec5-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="afec5-143">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="afec5-144">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="afec5-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="afec5-145">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="afec5-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="afec5-146">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="afec5-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="afec5-147">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="afec5-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="afec5-148">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="afec5-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="afec5-149">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="afec5-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="afec5-150">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="afec5-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="afec5-151">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afec5-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="afec5-152">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="afec5-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="afec5-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="afec5-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="afec5-154">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="afec5-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="afec5-155">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="afec5-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="afec5-156">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="afec5-157">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="afec5-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="afec5-158">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="afec5-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="afec5-159">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="afec5-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="afec5-160">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="afec5-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="afec5-161">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="afec5-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="afec5-162">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afec5-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="afec5-163">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="afec5-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="afec5-164">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="afec5-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="afec5-165">Generale</span><span class="sxs-lookup"><span data-stu-id="afec5-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="afec5-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="afec5-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="afec5-167">Comando</span><span class="sxs-lookup"><span data-stu-id="afec5-167">Command</span></span>                                       | <span data-ttu-id="afec5-168">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="afec5-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="afec5-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="afec5-170">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="afec5-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="afec5-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="afec5-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="afec5-172">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="afec5-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="afec5-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="afec5-174">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="afec5-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="afec5-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="afec5-176">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="afec5-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="afec5-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="afec5-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="afec5-178">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="afec5-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="afec5-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="afec5-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="afec5-180">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="afec5-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="afec5-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="afec5-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="afec5-182">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="afec5-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="afec5-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="afec5-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="afec5-184">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="afec5-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="afec5-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="afec5-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="afec5-186">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="afec5-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="afec5-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="afec5-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="afec5-188">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="afec5-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="afec5-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="afec5-190">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="afec5-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="afec5-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="afec5-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="afec5-192">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="afec5-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="afec5-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="afec5-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="afec5-194">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="afec5-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="afec5-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="afec5-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="afec5-196">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="afec5-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="afec5-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="afec5-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="afec5-198">Comando</span><span class="sxs-lookup"><span data-stu-id="afec5-198">Command</span></span>                             | <span data-ttu-id="afec5-199">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="afec5-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="afec5-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="afec5-201">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="afec5-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="afec5-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="afec5-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="afec5-203">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="afec5-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="afec5-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="afec5-205">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="afec5-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="afec5-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="afec5-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="afec5-207">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="afec5-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="afec5-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="afec5-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="afec5-209">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="afec5-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="afec5-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="afec5-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="afec5-211">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="afec5-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="afec5-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="afec5-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="afec5-213">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="afec5-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="afec5-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="afec5-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="afec5-215">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="afec5-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="afec5-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="afec5-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="afec5-217">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="afec5-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="afec5-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="afec5-219">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="afec5-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="afec5-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="afec5-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="afec5-221">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="afec5-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="afec5-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="afec5-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="afec5-223">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="afec5-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="afec5-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="afec5-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="afec5-225">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="afec5-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="afec5-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="afec5-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="afec5-227">Comando</span><span class="sxs-lookup"><span data-stu-id="afec5-227">Command</span></span>                             | <span data-ttu-id="afec5-228">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="afec5-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="afec5-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="afec5-230">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="afec5-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="afec5-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="afec5-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="afec5-232">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="afec5-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="afec5-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="afec5-234">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="afec5-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="afec5-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="afec5-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="afec5-236">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="afec5-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="afec5-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="afec5-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="afec5-238">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="afec5-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="afec5-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="afec5-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="afec5-240">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="afec5-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="afec5-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="afec5-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="afec5-242">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="afec5-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="afec5-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="afec5-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="afec5-244">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="afec5-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="afec5-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="afec5-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="afec5-246">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="afec5-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="afec5-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="afec5-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="afec5-248">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="afec5-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="afec5-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="afec5-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="afec5-250">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="afec5-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="afec5-251">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="afec5-251">Project references</span></span>

<span data-ttu-id="afec5-252">Comando</span><span class="sxs-lookup"><span data-stu-id="afec5-252">Command</span></span> | <span data-ttu-id="afec5-253">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-253">Function</span></span>
--- | ---
[<span data-ttu-id="afec5-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="afec5-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="afec5-255">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="afec5-255">Adds a project reference.</span></span>
[<span data-ttu-id="afec5-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="afec5-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="afec5-257">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="afec5-257">Lists project references.</span></span>
[<span data-ttu-id="afec5-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="afec5-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="afec5-259">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="afec5-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="afec5-260">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="afec5-260">NuGet packages</span></span>

<span data-ttu-id="afec5-261">Comando</span><span class="sxs-lookup"><span data-stu-id="afec5-261">Command</span></span> | <span data-ttu-id="afec5-262">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-262">Function</span></span>
--- | ---
[<span data-ttu-id="afec5-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="afec5-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="afec5-264">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="afec5-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="afec5-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="afec5-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="afec5-266">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="afec5-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="afec5-267">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="afec5-267">NuGet commands</span></span>

<span data-ttu-id="afec5-268">Comando</span><span class="sxs-lookup"><span data-stu-id="afec5-268">Command</span></span> | <span data-ttu-id="afec5-269">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-269">Function</span></span>
--- | ---
[<span data-ttu-id="afec5-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="afec5-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="afec5-271">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="afec5-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="afec5-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="afec5-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="afec5-273">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="afec5-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="afec5-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="afec5-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="afec5-275">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="afec5-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="afec5-276">Comandi degli strumenti globali</span><span class="sxs-lookup"><span data-stu-id="afec5-276">Global Tools commands</span></span>

<span data-ttu-id="afec5-277">Gli [strumenti globali .NET Core](global-tools.md) sono disponibili a partire da .NET Core SDK 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="afec5-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="afec5-278">Comando</span><span class="sxs-lookup"><span data-stu-id="afec5-278">Command</span></span> | <span data-ttu-id="afec5-279">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-279">Function</span></span>
--- | ---
[<span data-ttu-id="afec5-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="afec5-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="afec5-281">Installa uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="afec5-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="afec5-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="afec5-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="afec5-283">Elenca tutti gli strumenti globali attualmente installati nella directory predefinita nel computer o nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="afec5-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="afec5-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="afec5-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="afec5-285">Disinstalla uno strumento globale dal computer.</span><span class="sxs-lookup"><span data-stu-id="afec5-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="afec5-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="afec5-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="afec5-287">Aggiorna uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="afec5-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="afec5-288">Strumenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="afec5-288">Additional tools</span></span>

<span data-ttu-id="afec5-289">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="afec5-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="afec5-290">Tali strumenti sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="afec5-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="afec5-291">Strumento</span><span class="sxs-lookup"><span data-stu-id="afec5-291">Tool</span></span>                                              | <span data-ttu-id="afec5-292">Funzione</span><span class="sxs-lookup"><span data-stu-id="afec5-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="afec5-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="afec5-293">dev-certs</span></span>                                         | <span data-ttu-id="afec5-294">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="afec5-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="afec5-295">ef</span><span class="sxs-lookup"><span data-stu-id="afec5-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="afec5-296">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="afec5-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="afec5-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="afec5-297">sql-cache</span></span>                                         | <span data-ttu-id="afec5-298">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="afec5-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="afec5-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="afec5-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="afec5-300">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="afec5-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="afec5-301">watch</span><span class="sxs-lookup"><span data-stu-id="afec5-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="afec5-302">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="afec5-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="afec5-303">Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="afec5-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="afec5-304">Esempi</span><span class="sxs-lookup"><span data-stu-id="afec5-304">Examples</span></span>

<span data-ttu-id="afec5-305">Creare una nuova applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="afec5-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="afec5-306">Ripristinare le dipendenze per una determinata applicazione:</span><span class="sxs-lookup"><span data-stu-id="afec5-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="afec5-307">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="afec5-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="afec5-308">Eseguire una DLL dell'applicazione, ad esempio `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="afec5-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="afec5-309">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="afec5-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="afec5-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="afec5-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="afec5-311">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="afec5-311">The primary package cache.</span></span> <span data-ttu-id="afec5-312">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="afec5-312">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="afec5-313">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="afec5-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="afec5-314">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afec5-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="afec5-315">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="afec5-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="afec5-316">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="afec5-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="afec5-317">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="afec5-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="afec5-318">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="afec5-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="afec5-319">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="afec5-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="afec5-320">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="afec5-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="afec5-321">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="afec5-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="afec5-322">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="afec5-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="afec5-323">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="afec5-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="afec5-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="afec5-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="afec5-325">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="afec5-325">The primary package cache.</span></span> <span data-ttu-id="afec5-326">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="afec5-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="afec5-327">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="afec5-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="afec5-328">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afec5-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="afec5-329">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="afec5-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="afec5-330">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="afec5-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="afec5-331">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="afec5-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="afec5-332">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="afec5-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="afec5-333">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="afec5-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="afec5-334">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="afec5-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="afec5-335">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="afec5-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="afec5-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="afec5-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="afec5-337">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="afec5-337">The primary package cache.</span></span> <span data-ttu-id="afec5-338">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="afec5-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="afec5-339">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="afec5-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="afec5-340">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afec5-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="afec5-341">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="afec5-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="afec5-342">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="afec5-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="afec5-343">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="afec5-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
