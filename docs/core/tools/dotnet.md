---
title: Comando dotnet - Interfaccia della riga di comando di .NET Core
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 53e8f8bab1cbaabaa7926aa68197c18843b0b637
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44079816"
---
# <a name="dotnet-command"></a><span data-ttu-id="ca8d8-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="ca8d8-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ca8d8-104">nome</span><span class="sxs-lookup"><span data-stu-id="ca8d8-104">Name</span></span>

<span data-ttu-id="ca8d8-105">`dotnet`: uno strumento per la gestione dei file binari e del codice sorgente di .NET.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ca8d8-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ca8d8-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca8d8-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca8d8-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca8d8-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca8d8-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca8d8-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca8d8-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="ca8d8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-110">Description</span></span>

<span data-ttu-id="ca8d8-111">`dotnet` è uno strumento per la gestione dei file binari e del codice sorgente di .NET.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="ca8d8-112">Espone i comandi che eseguono attività specifiche, come ad esempio [`dotnet build`](dotnet-build.md) e [`dotnet run`](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="ca8d8-113">Ogni comando definisce i propri argomenti.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-113">Each command defines its own arguments.</span></span> <span data-ttu-id="ca8d8-114">Digitare `--help` dopo ogni comando per accedere a una breve documentazione della Guida.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="ca8d8-115">`dotnet` può essere usato per eseguire le applicazioni specificando una DLL dell'applicazione, come ad esempio `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="ca8d8-116">Per informazioni sulle opzioni di distribuzione, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="ca8d8-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ca8d8-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca8d8-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca8d8-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="ca8d8-119">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ca8d8-120">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ca8d8-121">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ca8d8-122">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ca8d8-123">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ca8d8-124">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ca8d8-125">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="ca8d8-126">Visualizza i runtime di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="ca8d8-127">Visualizza i .NET Core SDK installati.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="ca8d8-128">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-128">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ca8d8-129">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-129">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca8d8-130">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca8d8-131">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ca8d8-132">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ca8d8-133">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca8d8-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca8d8-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="ca8d8-135">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="ca8d8-136">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ca8d8-137">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ca8d8-138">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-138">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ca8d8-139">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-139">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ca8d8-140">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-140">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ca8d8-141">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-141">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="ca8d8-142">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-142">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ca8d8-143">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-143">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca8d8-144">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca8d8-145">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ca8d8-146">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-146">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ca8d8-147">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-147">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca8d8-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca8d8-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="ca8d8-149">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-149">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="ca8d8-150">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-150">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="ca8d8-151">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-151">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="ca8d8-152">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-152">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="ca8d8-153">`dotnet --help` consente di visualizzare un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-153">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="ca8d8-154">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-154">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca8d8-155">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca8d8-156">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ca8d8-157">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-157">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="ca8d8-158">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-158">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="ca8d8-159">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="ca8d8-159">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="ca8d8-160">Generale</span><span class="sxs-lookup"><span data-stu-id="ca8d8-160">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca8d8-161">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca8d8-161">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="ca8d8-162">Comando</span><span class="sxs-lookup"><span data-stu-id="ca8d8-162">Command</span></span>                                       | <span data-ttu-id="ca8d8-163">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-163">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ca8d8-164">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ca8d8-164">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="ca8d8-165">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-165">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ca8d8-166">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="ca8d8-166">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="ca8d8-167">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-167">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="ca8d8-168">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ca8d8-168">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="ca8d8-169">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-169">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="ca8d8-170">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ca8d8-170">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="ca8d8-171">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-171">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ca8d8-172">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ca8d8-172">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="ca8d8-173">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-173">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ca8d8-174">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ca8d8-174">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="ca8d8-175">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-175">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ca8d8-176">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca8d8-176">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="ca8d8-177">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-177">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ca8d8-178">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ca8d8-178">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="ca8d8-179">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-179">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ca8d8-180">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ca8d8-180">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="ca8d8-181">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-181">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ca8d8-182">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ca8d8-182">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="ca8d8-183">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-183">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ca8d8-184">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ca8d8-184">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="ca8d8-185">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-185">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ca8d8-186">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ca8d8-186">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="ca8d8-187">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-187">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ca8d8-188">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ca8d8-188">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="ca8d8-189">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-189">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ca8d8-190">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ca8d8-190">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="ca8d8-191">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-191">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca8d8-192">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca8d8-192">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="ca8d8-193">Comando</span><span class="sxs-lookup"><span data-stu-id="ca8d8-193">Command</span></span>                             | <span data-ttu-id="ca8d8-194">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-194">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ca8d8-195">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ca8d8-195">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ca8d8-196">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-196">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ca8d8-197">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ca8d8-197">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ca8d8-198">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-198">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ca8d8-199">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ca8d8-199">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="ca8d8-200">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-200">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ca8d8-201">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ca8d8-201">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ca8d8-202">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-202">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ca8d8-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ca8d8-203">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ca8d8-204">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-204">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ca8d8-205">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca8d8-205">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ca8d8-206">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-206">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ca8d8-207">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ca8d8-207">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ca8d8-208">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-208">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ca8d8-209">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ca8d8-209">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ca8d8-210">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-210">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ca8d8-211">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ca8d8-211">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ca8d8-212">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-212">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ca8d8-213">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ca8d8-213">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ca8d8-214">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-214">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ca8d8-215">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ca8d8-215">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ca8d8-216">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-216">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ca8d8-217">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ca8d8-217">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="ca8d8-218">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-218">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ca8d8-219">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ca8d8-219">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ca8d8-220">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-220">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca8d8-221">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca8d8-221">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="ca8d8-222">Comando</span><span class="sxs-lookup"><span data-stu-id="ca8d8-222">Command</span></span>                             | <span data-ttu-id="ca8d8-223">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-223">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ca8d8-224">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ca8d8-224">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="ca8d8-225">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-225">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ca8d8-226">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ca8d8-226">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="ca8d8-227">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-227">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="ca8d8-228">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ca8d8-228">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="ca8d8-229">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-229">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ca8d8-230">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ca8d8-230">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="ca8d8-231">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-231">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ca8d8-232">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca8d8-232">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="ca8d8-233">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-233">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ca8d8-234">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ca8d8-234">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="ca8d8-235">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-235">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ca8d8-236">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ca8d8-236">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="ca8d8-237">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-237">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ca8d8-238">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ca8d8-238">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="ca8d8-239">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-239">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ca8d8-240">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ca8d8-240">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="ca8d8-241">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-241">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ca8d8-242">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ca8d8-242">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="ca8d8-243">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-243">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ca8d8-244">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ca8d8-244">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="ca8d8-245">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-245">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="ca8d8-246">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="ca8d8-246">Project references</span></span>

<span data-ttu-id="ca8d8-247">Comando</span><span class="sxs-lookup"><span data-stu-id="ca8d8-247">Command</span></span> | <span data-ttu-id="ca8d8-248">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-248">Function</span></span>
--- | ---
[<span data-ttu-id="ca8d8-249">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="ca8d8-249">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="ca8d8-250">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-250">Adds a project reference.</span></span>
[<span data-ttu-id="ca8d8-251">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="ca8d8-251">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="ca8d8-252">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-252">Lists project references.</span></span>
[<span data-ttu-id="ca8d8-253">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="ca8d8-253">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="ca8d8-254">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-254">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="ca8d8-255">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="ca8d8-255">NuGet packages</span></span>

<span data-ttu-id="ca8d8-256">Comando</span><span class="sxs-lookup"><span data-stu-id="ca8d8-256">Command</span></span> | <span data-ttu-id="ca8d8-257">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-257">Function</span></span>
--- | ---
[<span data-ttu-id="ca8d8-258">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="ca8d8-258">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="ca8d8-259">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-259">Adds a NuGet package.</span></span>
[<span data-ttu-id="ca8d8-260">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="ca8d8-260">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="ca8d8-261">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-261">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="ca8d8-262">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="ca8d8-262">NuGet commands</span></span>

<span data-ttu-id="ca8d8-263">Comando</span><span class="sxs-lookup"><span data-stu-id="ca8d8-263">Command</span></span> | <span data-ttu-id="ca8d8-264">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-264">Function</span></span>
--- | ---
[<span data-ttu-id="ca8d8-265">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="ca8d8-265">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="ca8d8-266">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-266">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="ca8d8-267">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="ca8d8-267">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="ca8d8-268">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-268">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="ca8d8-269">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="ca8d8-269">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="ca8d8-270">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-270">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="ca8d8-271">Comandi degli strumenti globali</span><span class="sxs-lookup"><span data-stu-id="ca8d8-271">Global Tools commands</span></span>

<span data-ttu-id="ca8d8-272">Gli [strumenti globali .NET Core](global-tools.md) sono disponibili a partire da .NET Core SDK 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="ca8d8-272">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="ca8d8-273">Comando</span><span class="sxs-lookup"><span data-stu-id="ca8d8-273">Command</span></span> | <span data-ttu-id="ca8d8-274">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-274">Function</span></span>
--- | ---
[<span data-ttu-id="ca8d8-275">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="ca8d8-275">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="ca8d8-276">Installa uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-276">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="ca8d8-277">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="ca8d8-277">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="ca8d8-278">Elenca tutti gli strumenti globali attualmente installati nella directory predefinita nel computer o nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-278">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="ca8d8-279">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="ca8d8-279">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="ca8d8-280">Disinstalla uno strumento globale dal computer.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-280">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="ca8d8-281">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="ca8d8-281">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="ca8d8-282">Aggiorna uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-282">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="ca8d8-283">Altri strumenti</span><span class="sxs-lookup"><span data-stu-id="ca8d8-283">Additional tools</span></span>

<span data-ttu-id="ca8d8-284">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-284">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="ca8d8-285">Tali strumenti sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ca8d8-285">These tools are listed in the following table:</span></span>

| <span data-ttu-id="ca8d8-286">Strumento</span><span class="sxs-lookup"><span data-stu-id="ca8d8-286">Tool</span></span>                                              | <span data-ttu-id="ca8d8-287">Funzione</span><span class="sxs-lookup"><span data-stu-id="ca8d8-287">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="ca8d8-288">dev-certs</span><span class="sxs-lookup"><span data-stu-id="ca8d8-288">dev-certs</span></span>                                         | <span data-ttu-id="ca8d8-289">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-289">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="ca8d8-290">ef</span><span class="sxs-lookup"><span data-stu-id="ca8d8-290">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="ca8d8-291">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-291">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="ca8d8-292">sql-cache</span><span class="sxs-lookup"><span data-stu-id="ca8d8-292">sql-cache</span></span>                                         | <span data-ttu-id="ca8d8-293">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-293">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="ca8d8-294">user-secrets</span><span class="sxs-lookup"><span data-stu-id="ca8d8-294">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="ca8d8-295">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-295">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="ca8d8-296">watch</span><span class="sxs-lookup"><span data-stu-id="ca8d8-296">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="ca8d8-297">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-297">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="ca8d8-298">Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-298">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="ca8d8-299">Esempi</span><span class="sxs-lookup"><span data-stu-id="ca8d8-299">Examples</span></span>

<span data-ttu-id="ca8d8-300">Creare una nuova applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="ca8d8-300">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="ca8d8-301">Ripristinare le dipendenze per una determinata applicazione:</span><span class="sxs-lookup"><span data-stu-id="ca8d8-301">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="ca8d8-302">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="ca8d8-302">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="ca8d8-303">Eseguire una DLL dell'applicazione, ad esempio `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="ca8d8-303">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="ca8d8-304">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="ca8d8-304">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca8d8-305">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca8d8-305">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="ca8d8-306">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-306">The primary package cache.</span></span> <span data-ttu-id="ca8d8-307">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-307">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ca8d8-308">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-308">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ca8d8-309">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-309">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ca8d8-310">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-310">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ca8d8-311">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-311">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ca8d8-312">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-312">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ca8d8-313">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-313">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ca8d8-314">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-314">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ca8d8-315">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-315">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ca8d8-316">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-316">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="ca8d8-317">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ca8d8-318">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca8d8-319">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca8d8-319">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="ca8d8-320">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-320">The primary package cache.</span></span> <span data-ttu-id="ca8d8-321">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-321">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ca8d8-322">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-322">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ca8d8-323">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-323">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ca8d8-324">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-324">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ca8d8-325">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-325">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ca8d8-326">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-326">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="ca8d8-327">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-327">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ca8d8-328">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-328">If not set, it defaults to `true`.</span></span> <span data-ttu-id="ca8d8-329">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-329">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="ca8d8-330">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-330">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca8d8-331">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca8d8-331">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="ca8d8-332">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-332">The primary package cache.</span></span> <span data-ttu-id="ca8d8-333">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-333">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="ca8d8-334">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-334">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="ca8d8-335">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-335">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ca8d8-336">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-336">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ca8d8-337">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="ca8d8-337">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ca8d8-338">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="ca8d8-338">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
