---
title: Comando dotnet - Interfaccia della riga di comando di .NET Core
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
author: mairaw
ms.author: mairaw
ms.date: 03/20/2018
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 2d22124cb613152df402046541650f3262e7e202
ms.sourcegitcommit: 6f967c86dde55472440f0c8669b0e910ee3c53ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="33e27-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="33e27-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="33e27-104">nome</span><span class="sxs-lookup"><span data-stu-id="33e27-104">Name</span></span>

<span data-ttu-id="33e27-105">`dotnet`: driver generale per l'esecuzione dei comandi della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="33e27-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="33e27-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="33e27-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="33e27-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="33e27-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="33e27-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="33e27-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33e27-109">Description</span></span>

<span data-ttu-id="33e27-110">`dotnet` è un driver generico per la toolchain dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="33e27-111">Se richiamato come comando autonomo, visualizza brevi istruzioni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="33e27-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="33e27-112">Ogni funzionalità specifica viene implementata come un comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="33e27-113">Per usare la funzionalità, il comando viene specificato dopo `dotnet`, ad esempio [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="33e27-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="33e27-114">Tutti gli argomenti che seguono il comando sono gli argomenti del comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="33e27-115">`dotnet` viene usato come comando autonomo solo per eseguire [app dipendenti dal framework](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="33e27-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="33e27-116">Per eseguire l'applicazione, ad esempio `dotnet myapp.dll`, specificare una DLL di applicazione dopo il verbo `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="33e27-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="33e27-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="33e27-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="33e27-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="33e27-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="33e27-119">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="33e27-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="33e27-120">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="33e27-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="33e27-121">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="33e27-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="33e27-122">Versione del runtime .NET Core installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="33e27-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="33e27-123">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-123">Prints out a short help for the command.</span></span> <span data-ttu-id="33e27-124">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="33e27-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="33e27-125">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="33e27-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="33e27-126">Non esegue il roll forward su framework condiviso candidato.</span><span class="sxs-lookup"><span data-stu-id="33e27-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="33e27-127">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="33e27-128">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="33e27-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="33e27-129">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="33e27-129">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="33e27-130">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="33e27-130">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="33e27-131">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="33e27-131">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="33e27-132">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="33e27-132">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="33e27-133">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="33e27-133">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="33e27-134">Versione del runtime .NET Core installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="33e27-134">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="33e27-135">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-135">Prints out a short help for the command.</span></span> <span data-ttu-id="33e27-136">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="33e27-136">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="33e27-137">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="33e27-137">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="33e27-138">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="33e27-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="33e27-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="33e27-140">Non supportato in tutti i comandi; vedere la pagina specifica del comando per determinare se l'opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="33e27-140">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="33e27-141">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="33e27-141">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="33e27-142">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="33e27-142">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="33e27-143">Generale</span><span class="sxs-lookup"><span data-stu-id="33e27-143">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="33e27-144">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="33e27-144">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="33e27-145">Comando</span><span class="sxs-lookup"><span data-stu-id="33e27-145">Command</span></span>                             | <span data-ttu-id="33e27-146">Funzione</span><span class="sxs-lookup"><span data-stu-id="33e27-146">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="33e27-147">dotnet build</span><span class="sxs-lookup"><span data-stu-id="33e27-147">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="33e27-148">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33e27-148">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="33e27-149">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="33e27-149">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="33e27-150">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="33e27-150">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="33e27-151">dotnet help</span><span class="sxs-lookup"><span data-stu-id="33e27-151">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="33e27-152">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="33e27-152">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="33e27-153">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="33e27-153">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="33e27-154">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="33e27-154">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="33e27-155">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="33e27-155">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="33e27-156">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="33e27-156">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="33e27-157">dotnet new</span><span class="sxs-lookup"><span data-stu-id="33e27-157">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="33e27-158">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="33e27-158">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="33e27-159">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="33e27-159">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="33e27-160">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="33e27-160">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="33e27-161">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="33e27-161">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="33e27-162">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="33e27-162">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="33e27-163">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="33e27-163">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="33e27-164">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="33e27-164">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="33e27-165">dotnet run</span><span class="sxs-lookup"><span data-stu-id="33e27-165">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="33e27-166">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="33e27-166">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="33e27-167">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="33e27-167">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="33e27-168">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="33e27-168">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="33e27-169">dotnet store</span><span class="sxs-lookup"><span data-stu-id="33e27-169">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="33e27-170">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="33e27-170">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="33e27-171">dotnet test</span><span class="sxs-lookup"><span data-stu-id="33e27-171">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="33e27-172">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="33e27-172">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="33e27-173">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="33e27-173">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="33e27-174">Comando</span><span class="sxs-lookup"><span data-stu-id="33e27-174">Command</span></span>                             | <span data-ttu-id="33e27-175">Funzione</span><span class="sxs-lookup"><span data-stu-id="33e27-175">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="33e27-176">dotnet build</span><span class="sxs-lookup"><span data-stu-id="33e27-176">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="33e27-177">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="33e27-177">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="33e27-178">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="33e27-178">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="33e27-179">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="33e27-179">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="33e27-180">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="33e27-180">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="33e27-181">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="33e27-181">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="33e27-182">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="33e27-182">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="33e27-183">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="33e27-183">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="33e27-184">dotnet new</span><span class="sxs-lookup"><span data-stu-id="33e27-184">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="33e27-185">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="33e27-185">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="33e27-186">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="33e27-186">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="33e27-187">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="33e27-187">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="33e27-188">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="33e27-188">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="33e27-189">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="33e27-189">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="33e27-190">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="33e27-190">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="33e27-191">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="33e27-191">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="33e27-192">dotnet run</span><span class="sxs-lookup"><span data-stu-id="33e27-192">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="33e27-193">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="33e27-193">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="33e27-194">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="33e27-194">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="33e27-195">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="33e27-195">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="33e27-196">dotnet test</span><span class="sxs-lookup"><span data-stu-id="33e27-196">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="33e27-197">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="33e27-197">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="33e27-198">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="33e27-198">Project references</span></span>

<span data-ttu-id="33e27-199">Comando</span><span class="sxs-lookup"><span data-stu-id="33e27-199">Command</span></span> | <span data-ttu-id="33e27-200">Funzione</span><span class="sxs-lookup"><span data-stu-id="33e27-200">Function</span></span>
--- | ---
[<span data-ttu-id="33e27-201">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="33e27-201">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="33e27-202">Aggiungere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="33e27-202">Add a project reference.</span></span>
[<span data-ttu-id="33e27-203">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="33e27-203">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="33e27-204">Elencare i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="33e27-204">List project references.</span></span>
[<span data-ttu-id="33e27-205">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="33e27-205">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="33e27-206">Rimuovere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="33e27-206">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="33e27-207">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="33e27-207">NuGet packages</span></span>

<span data-ttu-id="33e27-208">Comando</span><span class="sxs-lookup"><span data-stu-id="33e27-208">Command</span></span> | <span data-ttu-id="33e27-209">Funzione</span><span class="sxs-lookup"><span data-stu-id="33e27-209">Function</span></span>
--- | ---
[<span data-ttu-id="33e27-210">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="33e27-210">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="33e27-211">Aggiungere un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="33e27-211">Add a NuGet package.</span></span>
[<span data-ttu-id="33e27-212">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="33e27-212">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="33e27-213">Rimuovere un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="33e27-213">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="33e27-214">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="33e27-214">NuGet commands</span></span>

<span data-ttu-id="33e27-215">Comando</span><span class="sxs-lookup"><span data-stu-id="33e27-215">Command</span></span> | <span data-ttu-id="33e27-216">Funzione</span><span class="sxs-lookup"><span data-stu-id="33e27-216">Function</span></span>
--- | ---
[<span data-ttu-id="33e27-217">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="33e27-217">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="33e27-218">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="33e27-218">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="33e27-219">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="33e27-219">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="33e27-220">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="33e27-220">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="33e27-221">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="33e27-221">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="33e27-222">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="33e27-222">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="33e27-223">Esempi</span><span class="sxs-lookup"><span data-stu-id="33e27-223">Examples</span></span>

<span data-ttu-id="33e27-224">Inizializzare un'applicazione console .NET Core di esempio che può essere compilata ed eseguita:</span><span class="sxs-lookup"><span data-stu-id="33e27-224">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="33e27-225">Ripristinare le dipendenze per una determinata applicazione:</span><span class="sxs-lookup"><span data-stu-id="33e27-225">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="33e27-226">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="33e27-226">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="33e27-227">Eseguire un'app dipendente dal framework denominata `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="33e27-227">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="33e27-228">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="33e27-228">Environment variables</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="33e27-229">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="33e27-229">.NET Core 2.x</span></span>](#tab/netcore2x)

`DOTNET_PACKAGES`

<span data-ttu-id="33e27-230">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="33e27-230">The primary package cache.</span></span> <span data-ttu-id="33e27-231">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="33e27-231">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="33e27-232">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="33e27-232">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="33e27-233">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33e27-233">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="33e27-234">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="33e27-234">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="33e27-235">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="33e27-235">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="33e27-236">Specifica se il runtime .NET Core, il framework condiviso o SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="33e27-236">Specifies whether .NET Core runtime, shared framework or SDK are resolved from the global location.</span></span> <span data-ttu-id="33e27-237">Se non sono impostati, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="33e27-237">If not set, it defaults to `true`.</span></span> <span data-ttu-id="33e27-238">Impostare su `false` per non risolvere dal percorso globale e disporre di installazioni di .NET Core isolate (sono accettati i valori `0` o `false`).</span><span class="sxs-lookup"><span data-stu-id="33e27-238">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="33e27-239">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="33e27-239">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="33e27-240">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="33e27-240">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="33e27-241">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="33e27-241">The primary package cache.</span></span> <span data-ttu-id="33e27-242">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="33e27-242">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="33e27-243">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="33e27-243">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="33e27-244">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33e27-244">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="33e27-245">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="33e27-245">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="33e27-246">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="33e27-246">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

---
