---
title: Comando dotnet - Interfaccia della riga di comando di .NET Core
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 2eea7d13994bfddc89d8f3513308a6620c53c88c
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="bb255-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="bb255-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="bb255-104">nome</span><span class="sxs-lookup"><span data-stu-id="bb255-104">Name</span></span>

<span data-ttu-id="bb255-105">`dotnet`: driver generale per l'esecuzione dei comandi della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="bb255-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bb255-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="bb255-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bb255-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bb255-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bb255-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bb255-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a><span data-ttu-id="bb255-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb255-109">Description</span></span>

<span data-ttu-id="bb255-110">`dotnet` è un driver generico per la toolchain dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="bb255-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="bb255-111">Se richiamato come comando autonomo, visualizza brevi istruzioni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="bb255-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="bb255-112">Ogni funzionalità specifica viene implementata come un comando.</span><span class="sxs-lookup"><span data-stu-id="bb255-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="bb255-113">Per usare la funzionalità, il comando viene specificato dopo `dotnet`, ad esempio [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="bb255-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="bb255-114">Tutti gli argomenti che seguono il comando sono gli argomenti del comando.</span><span class="sxs-lookup"><span data-stu-id="bb255-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="bb255-115">`dotnet` viene usato come comando autonomo solo per eseguire [app dipendenti dal framework](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="bb255-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="bb255-116">Per eseguire l'applicazione, ad esempio `dotnet myapp.dll`, specificare una DLL di applicazione dopo il verbo `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="bb255-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="bb255-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bb255-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bb255-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bb255-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="bb255-119">Percorso del file *deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="bb255-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="bb255-120">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="bb255-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="bb255-121">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="bb255-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="bb255-122">Versione del runtime .NET Core installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb255-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="bb255-123">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="bb255-123">Prints out a short help for the command.</span></span> <span data-ttu-id="bb255-124">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="bb255-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="bb255-125">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="bb255-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="bb255-126">Non esegue il roll forward su framework condiviso candidato.</span><span class="sxs-lookup"><span data-stu-id="bb255-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbose`

<span data-ttu-id="bb255-127">Abilita l'output dettagliato.</span><span class="sxs-lookup"><span data-stu-id="bb255-127">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="bb255-128">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="bb255-128">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bb255-129">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bb255-129">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="bb255-130">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="bb255-130">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="bb255-131">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="bb255-131">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="bb255-132">Versione del runtime .NET Core installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb255-132">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="bb255-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="bb255-133">Prints out a short help for the command.</span></span> <span data-ttu-id="bb255-134">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="bb255-134">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="bb255-135">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="bb255-135">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbose`

<span data-ttu-id="bb255-136">Abilita l'output dettagliato.</span><span class="sxs-lookup"><span data-stu-id="bb255-136">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="bb255-137">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="bb255-137">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="bb255-138">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="bb255-138">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="bb255-139">Generale</span><span class="sxs-lookup"><span data-stu-id="bb255-139">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bb255-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bb255-140">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="bb255-141">Comando</span><span class="sxs-lookup"><span data-stu-id="bb255-141">Command</span></span>                             | <span data-ttu-id="bb255-142">Funzione</span><span class="sxs-lookup"><span data-stu-id="bb255-142">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="bb255-143">dotnet build</span><span class="sxs-lookup"><span data-stu-id="bb255-143">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="bb255-144">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bb255-144">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="bb255-145">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="bb255-145">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="bb255-146">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bb255-146">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="bb255-147">dotnet help</span><span class="sxs-lookup"><span data-stu-id="bb255-147">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="bb255-148">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="bb255-148">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="bb255-149">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="bb255-149">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="bb255-150">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="bb255-150">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="bb255-151">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="bb255-151">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="bb255-152">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="bb255-152">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="bb255-153">dotnet new</span><span class="sxs-lookup"><span data-stu-id="bb255-153">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="bb255-154">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="bb255-154">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="bb255-155">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="bb255-155">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="bb255-156">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="bb255-156">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="bb255-157">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="bb255-157">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="bb255-158">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="bb255-158">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="bb255-159">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="bb255-159">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="bb255-160">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb255-160">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="bb255-161">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bb255-161">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="bb255-162">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="bb255-162">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="bb255-163">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="bb255-163">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="bb255-164">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="bb255-164">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="bb255-165">dotnet store</span><span class="sxs-lookup"><span data-stu-id="bb255-165">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="bb255-166">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="bb255-166">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="bb255-167">dotnet test</span><span class="sxs-lookup"><span data-stu-id="bb255-167">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="bb255-168">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="bb255-168">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bb255-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bb255-169">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="bb255-170">Comando</span><span class="sxs-lookup"><span data-stu-id="bb255-170">Command</span></span>                             | <span data-ttu-id="bb255-171">Funzione</span><span class="sxs-lookup"><span data-stu-id="bb255-171">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="bb255-172">dotnet build</span><span class="sxs-lookup"><span data-stu-id="bb255-172">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="bb255-173">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bb255-173">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="bb255-174">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="bb255-174">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="bb255-175">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bb255-175">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="bb255-176">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="bb255-176">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="bb255-177">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="bb255-177">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="bb255-178">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="bb255-178">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="bb255-179">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="bb255-179">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="bb255-180">dotnet new</span><span class="sxs-lookup"><span data-stu-id="bb255-180">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="bb255-181">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="bb255-181">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="bb255-182">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="bb255-182">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="bb255-183">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="bb255-183">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="bb255-184">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="bb255-184">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="bb255-185">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="bb255-185">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="bb255-186">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="bb255-186">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="bb255-187">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb255-187">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="bb255-188">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bb255-188">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="bb255-189">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="bb255-189">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="bb255-190">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="bb255-190">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="bb255-191">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="bb255-191">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="bb255-192">dotnet test</span><span class="sxs-lookup"><span data-stu-id="bb255-192">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="bb255-193">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="bb255-193">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="bb255-194">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="bb255-194">Project references</span></span>

<span data-ttu-id="bb255-195">Comando</span><span class="sxs-lookup"><span data-stu-id="bb255-195">Command</span></span> | <span data-ttu-id="bb255-196">Funzione</span><span class="sxs-lookup"><span data-stu-id="bb255-196">Function</span></span>
--- | ---
[<span data-ttu-id="bb255-197">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="bb255-197">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="bb255-198">Aggiungere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="bb255-198">Add a project reference.</span></span>
[<span data-ttu-id="bb255-199">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="bb255-199">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="bb255-200">Elencare i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="bb255-200">List project references.</span></span>
[<span data-ttu-id="bb255-201">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="bb255-201">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="bb255-202">Rimuovere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="bb255-202">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="bb255-203">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="bb255-203">NuGet packages</span></span>

<span data-ttu-id="bb255-204">Comando</span><span class="sxs-lookup"><span data-stu-id="bb255-204">Command</span></span> | <span data-ttu-id="bb255-205">Funzione</span><span class="sxs-lookup"><span data-stu-id="bb255-205">Function</span></span>
--- | ---
[<span data-ttu-id="bb255-206">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="bb255-206">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="bb255-207">Aggiungere un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="bb255-207">Add a NuGet package.</span></span>
[<span data-ttu-id="bb255-208">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="bb255-208">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="bb255-209">Rimuovere un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="bb255-209">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="bb255-210">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="bb255-210">NuGet commands</span></span>

<span data-ttu-id="bb255-211">Comando</span><span class="sxs-lookup"><span data-stu-id="bb255-211">Command</span></span> | <span data-ttu-id="bb255-212">Funzione</span><span class="sxs-lookup"><span data-stu-id="bb255-212">Function</span></span>
--- | ---
[<span data-ttu-id="bb255-213">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="bb255-213">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="bb255-214">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="bb255-214">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="bb255-215">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="bb255-215">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="bb255-216">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="bb255-216">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="bb255-217">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="bb255-217">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="bb255-218">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="bb255-218">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="bb255-219">Esempi</span><span class="sxs-lookup"><span data-stu-id="bb255-219">Examples</span></span>

<span data-ttu-id="bb255-220">Inizializzare un'applicazione console .NET Core di esempio che può essere compilata ed eseguita:</span><span class="sxs-lookup"><span data-stu-id="bb255-220">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="bb255-221">Ripristinare le dipendenze per una determinata applicazione:</span><span class="sxs-lookup"><span data-stu-id="bb255-221">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="bb255-222">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="bb255-222">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="bb255-223">Eseguire un'app dipendente dal framework denominata `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="bb255-223">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="bb255-224">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="bb255-224">Environment variables</span></span>

`DOTNET_PACKAGES`

<span data-ttu-id="bb255-225">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="bb255-225">The primary package cache.</span></span> <span data-ttu-id="bb255-226">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="bb255-226">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="bb255-227">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="bb255-227">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="bb255-228">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb255-228">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="bb255-229">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="bb255-229">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="bb255-230">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="bb255-230">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>
