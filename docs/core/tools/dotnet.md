---
title: Comando dotnet - Interfaccia della riga di comando di .NET Core
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805659"
---
# <a name="dotnet-command"></a><span data-ttu-id="c429e-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="c429e-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c429e-104">nome</span><span class="sxs-lookup"><span data-stu-id="c429e-104">Name</span></span>

<span data-ttu-id="c429e-105">`dotnet`: driver generale per l'esecuzione dei comandi della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c429e-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c429e-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c429e-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c429e-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c429e-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c429e-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c429e-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c429e-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="c429e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c429e-110">Description</span></span>

<span data-ttu-id="c429e-111">`dotnet` è un driver generico per la toolchain dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-111">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="c429e-112">Se richiamato come comando autonomo, visualizza brevi istruzioni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c429e-112">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="c429e-113">Ogni funzionalità specifica viene implementata come un comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-113">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="c429e-114">Per usare la funzionalità, il comando viene specificato dopo `dotnet`, ad esempio [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="c429e-114">To use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="c429e-115">Tutti gli argomenti che seguono il comando sono gli argomenti del comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-115">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="c429e-116">`dotnet` viene usato come comando autonomo solo per eseguire [app dipendenti dal framework](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c429e-116">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="c429e-117">Per eseguire l'applicazione, ad esempio `dotnet myapp.dll`, specificare una DLL di applicazione dopo il verbo `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="c429e-117">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="c429e-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c429e-118">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c429e-119">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c429e-119">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="c429e-120">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="c429e-120">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c429e-121">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="c429e-121">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c429e-122">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="c429e-122">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c429e-123">Versione del runtime .NET Core installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-123">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c429e-124">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-124">Prints out a short help for the command.</span></span> <span data-ttu-id="c429e-125">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="c429e-125">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c429e-126">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="c429e-126">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--list-runtimes`

<span data-ttu-id="c429e-127">Visualizza i runtime di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="c429e-127">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="c429e-128">Visualizza i .NET Core SDK installati.</span><span class="sxs-lookup"><span data-stu-id="c429e-128">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c429e-129">Non esegue il roll forward su framework condiviso candidato.</span><span class="sxs-lookup"><span data-stu-id="c429e-129">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c429e-130">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c429e-131">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c429e-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c429e-132">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c429e-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c429e-133">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="c429e-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c429e-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c429e-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="c429e-135">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="c429e-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="c429e-136">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="c429e-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c429e-137">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="c429e-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c429e-138">Versione del runtime .NET Core installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-138">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c429e-139">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-139">Prints out a short help for the command.</span></span> <span data-ttu-id="c429e-140">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="c429e-140">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c429e-141">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="c429e-141">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="c429e-142">Non esegue il roll forward su framework condiviso candidato.</span><span class="sxs-lookup"><span data-stu-id="c429e-142">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c429e-143">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c429e-144">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c429e-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c429e-145">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c429e-145">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c429e-146">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="c429e-146">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c429e-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c429e-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="c429e-148">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="c429e-148">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="c429e-149">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="c429e-149">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="c429e-150">Versione del runtime .NET Core installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-150">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="c429e-151">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-151">Prints out a short help for the command.</span></span> <span data-ttu-id="c429e-152">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="c429e-152">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="c429e-153">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="c429e-153">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c429e-154">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-154">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c429e-155">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c429e-155">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c429e-156">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c429e-156">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="c429e-157">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="c429e-157">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="c429e-158">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="c429e-158">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c429e-159">Generale</span><span class="sxs-lookup"><span data-stu-id="c429e-159">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c429e-160">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c429e-160">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="c429e-161">Comando</span><span class="sxs-lookup"><span data-stu-id="c429e-161">Command</span></span>                                       | <span data-ttu-id="c429e-162">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-162">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c429e-163">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c429e-163">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="c429e-164">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c429e-164">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c429e-165">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="c429e-165">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="c429e-166">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-166">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="c429e-167">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c429e-167">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="c429e-168">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-168">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="c429e-169">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c429e-169">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="c429e-170">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-170">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c429e-171">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c429e-171">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="c429e-172">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="c429e-172">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c429e-173">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c429e-173">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="c429e-174">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c429e-174">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c429e-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c429e-175">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="c429e-176">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="c429e-176">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c429e-177">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c429e-177">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="c429e-178">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="c429e-178">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c429e-179">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c429e-179">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="c429e-180">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="c429e-180">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c429e-181">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c429e-181">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="c429e-182">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-182">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c429e-183">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c429e-183">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="c429e-184">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="c429e-184">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c429e-185">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c429e-185">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="c429e-186">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="c429e-186">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c429e-187">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c429e-187">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="c429e-188">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="c429e-188">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c429e-189">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c429e-189">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="c429e-190">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="c429e-190">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c429e-191">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c429e-191">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="c429e-192">Comando</span><span class="sxs-lookup"><span data-stu-id="c429e-192">Command</span></span>                             | <span data-ttu-id="c429e-193">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-193">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c429e-194">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c429e-194">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c429e-195">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c429e-195">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c429e-196">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c429e-196">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c429e-197">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-197">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c429e-198">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c429e-198">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="c429e-199">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="c429e-199">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c429e-200">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c429e-200">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c429e-201">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="c429e-201">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c429e-202">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c429e-202">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c429e-203">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c429e-203">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c429e-204">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c429e-204">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c429e-205">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="c429e-205">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c429e-206">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c429e-206">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c429e-207">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="c429e-207">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c429e-208">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c429e-208">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c429e-209">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="c429e-209">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c429e-210">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c429e-210">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c429e-211">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-211">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c429e-212">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c429e-212">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c429e-213">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="c429e-213">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c429e-214">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c429e-214">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c429e-215">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="c429e-215">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c429e-216">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c429e-216">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="c429e-217">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="c429e-217">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c429e-218">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c429e-218">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c429e-219">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="c429e-219">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c429e-220">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c429e-220">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="c429e-221">Comando</span><span class="sxs-lookup"><span data-stu-id="c429e-221">Command</span></span>                             | <span data-ttu-id="c429e-222">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-222">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c429e-223">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c429e-223">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="c429e-224">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c429e-224">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c429e-225">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c429e-225">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="c429e-226">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-226">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="c429e-227">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c429e-227">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="c429e-228">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="c429e-228">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c429e-229">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c429e-229">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="c429e-230">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c429e-230">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c429e-231">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c429e-231">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="c429e-232">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="c429e-232">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c429e-233">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c429e-233">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="c429e-234">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="c429e-234">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c429e-235">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c429e-235">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="c429e-236">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="c429e-236">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c429e-237">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c429e-237">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="c429e-238">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="c429e-238">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c429e-239">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c429e-239">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="c429e-240">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="c429e-240">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c429e-241">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c429e-241">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="c429e-242">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="c429e-242">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c429e-243">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c429e-243">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="c429e-244">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="c429e-244">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="c429e-245">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="c429e-245">Project references</span></span>

<span data-ttu-id="c429e-246">Comando</span><span class="sxs-lookup"><span data-stu-id="c429e-246">Command</span></span> | <span data-ttu-id="c429e-247">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-247">Function</span></span>
--- | ---
[<span data-ttu-id="c429e-248">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c429e-248">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c429e-249">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="c429e-249">Adds a project reference.</span></span>
[<span data-ttu-id="c429e-250">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c429e-250">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c429e-251">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="c429e-251">Lists project references.</span></span>
[<span data-ttu-id="c429e-252">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c429e-252">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c429e-253">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="c429e-253">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c429e-254">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="c429e-254">NuGet packages</span></span>

<span data-ttu-id="c429e-255">Comando</span><span class="sxs-lookup"><span data-stu-id="c429e-255">Command</span></span> | <span data-ttu-id="c429e-256">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-256">Function</span></span>
--- | ---
[<span data-ttu-id="c429e-257">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c429e-257">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c429e-258">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="c429e-258">Adds a NuGet package.</span></span>
[<span data-ttu-id="c429e-259">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c429e-259">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c429e-260">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="c429e-260">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c429e-261">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="c429e-261">NuGet commands</span></span>

<span data-ttu-id="c429e-262">Comando</span><span class="sxs-lookup"><span data-stu-id="c429e-262">Command</span></span> | <span data-ttu-id="c429e-263">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-263">Function</span></span>
--- | ---
[<span data-ttu-id="c429e-264">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c429e-264">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c429e-265">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="c429e-265">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c429e-266">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c429e-266">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c429e-267">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="c429e-267">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c429e-268">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c429e-268">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c429e-269">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="c429e-269">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="c429e-270">Comandi degli strumenti globali</span><span class="sxs-lookup"><span data-stu-id="c429e-270">Global Tools commands</span></span>

<span data-ttu-id="c429e-271">Gli [strumenti globali .NET Core](global-tools.md) sono disponibili a partire da .NET Core SDK 2.1.300:</span><span class="sxs-lookup"><span data-stu-id="c429e-271">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="c429e-272">Comando</span><span class="sxs-lookup"><span data-stu-id="c429e-272">Command</span></span> | <span data-ttu-id="c429e-273">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-273">Function</span></span>
--- | ---
[<span data-ttu-id="c429e-274">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="c429e-274">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="c429e-275">Installa uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="c429e-275">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="c429e-276">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="c429e-276">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="c429e-277">Elenca tutti gli strumenti globali attualmente installati nella directory predefinita nel computer o nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="c429e-277">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="c429e-278">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="c429e-278">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="c429e-279">Disinstalla uno strumento globale dal computer.</span><span class="sxs-lookup"><span data-stu-id="c429e-279">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="c429e-280">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="c429e-280">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="c429e-281">Aggiorna uno strumento globale nel computer.</span><span class="sxs-lookup"><span data-stu-id="c429e-281">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="c429e-282">Altri strumenti</span><span class="sxs-lookup"><span data-stu-id="c429e-282">Additional tools</span></span>

<span data-ttu-id="c429e-283">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="c429e-283">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="c429e-284">Questi strumenti comprendono:</span><span class="sxs-lookup"><span data-stu-id="c429e-284">These tools include:</span></span>

| <span data-ttu-id="c429e-285">Strumento</span><span class="sxs-lookup"><span data-stu-id="c429e-285">Tool</span></span>                                              | <span data-ttu-id="c429e-286">Funzione</span><span class="sxs-lookup"><span data-stu-id="c429e-286">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="c429e-287">dev-certs</span><span class="sxs-lookup"><span data-stu-id="c429e-287">dev-certs</span></span>                                         | <span data-ttu-id="c429e-288">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c429e-288">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="c429e-289">ef</span><span class="sxs-lookup"><span data-stu-id="c429e-289">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="c429e-290">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="c429e-290">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="c429e-291">sql-cache</span><span class="sxs-lookup"><span data-stu-id="c429e-291">sql-cache</span></span>                                         | <span data-ttu-id="c429e-292">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c429e-292">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="c429e-293">user-secrets</span><span class="sxs-lookup"><span data-stu-id="c429e-293">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="c429e-294">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c429e-294">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="c429e-295">watch</span><span class="sxs-lookup"><span data-stu-id="c429e-295">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="c429e-296">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="c429e-296">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="c429e-297">Per altre informazioni sui diversi strumenti, eseguire `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="c429e-297">For more information about each tool, execute `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="c429e-298">Esempi</span><span class="sxs-lookup"><span data-stu-id="c429e-298">Examples</span></span>

<span data-ttu-id="c429e-299">Creare una nuova applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="c429e-299">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="c429e-300">Ripristinare le dipendenze per una determinata applicazione:</span><span class="sxs-lookup"><span data-stu-id="c429e-300">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c429e-301">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="c429e-301">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="c429e-302">Eseguire un'app dipendente dal framework denominata `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="c429e-302">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="c429e-303">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="c429e-303">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c429e-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c429e-304">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="c429e-305">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="c429e-305">The primary package cache.</span></span> <span data-ttu-id="c429e-306">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="c429e-306">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c429e-307">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="c429e-307">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c429e-308">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c429e-308">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c429e-309">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="c429e-309">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c429e-310">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="c429e-310">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c429e-311">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="c429e-311">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="c429e-312">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="c429e-312">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c429e-313">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="c429e-313">If not set, it defaults to `true`.</span></span> <span data-ttu-id="c429e-314">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="c429e-314">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="c429e-315">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="c429e-315">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="c429e-316">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="c429e-316">Disables minor version roll forward.</span></span> <span data-ttu-id="c429e-317">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="c429e-317">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c429e-318">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c429e-318">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="c429e-319">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="c429e-319">The primary package cache.</span></span> <span data-ttu-id="c429e-320">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="c429e-320">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c429e-321">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="c429e-321">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c429e-322">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c429e-322">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c429e-323">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="c429e-323">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c429e-324">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="c429e-324">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c429e-325">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="c429e-325">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="c429e-326">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="c429e-326">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c429e-327">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="c429e-327">If not set, it defaults to `true`.</span></span> <span data-ttu-id="c429e-328">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="c429e-328">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="c429e-329">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="c429e-329">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c429e-330">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c429e-330">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="c429e-331">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="c429e-331">The primary package cache.</span></span> <span data-ttu-id="c429e-332">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="c429e-332">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="c429e-333">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="c429e-333">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="c429e-334">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c429e-334">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c429e-335">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="c429e-335">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c429e-336">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="c429e-336">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c429e-337">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="c429e-337">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
