---
title: Comando dotnet - Interfaccia della riga di comando di .NET Core
description: Informazioni sul comando dotnet (il driver generico per gli strumenti dell'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
keywords: dotnet, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/20/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 256e468e-eaaa-4715-b5fb-8cbddcf80e69
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f377ea55278ae382f56a0dc0cbcf1bb99f49eca
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-command"></a><span data-ttu-id="2d9a6-104">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="2d9a6-104">dotnet command</span></span>

## <a name="name"></a><span data-ttu-id="2d9a6-105">Nome</span><span class="sxs-lookup"><span data-stu-id="2d9a6-105">Name</span></span>

<span data-ttu-id="2d9a6-106">`dotnet`: driver generale per l'esecuzione dei comandi della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-106">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2d9a6-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2d9a6-107">Synopsis</span></span>

`dotnet [command] [arguments] [--version] [--info] [-d|--diagnostics] [-v|--verbose] [--fx-version] [--additionalprobingpath] [-h|--help]`

## <a name="description"></a><span data-ttu-id="2d9a6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d9a6-108">Description</span></span>

<span data-ttu-id="2d9a6-109">`dotnet` è un driver generico per la toolchain dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-109">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="2d9a6-110">Se richiamato come comando autonomo, visualizza brevi istruzioni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-110">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="2d9a6-111">Ogni funzionalità specifica viene implementata come un comando.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-111">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="2d9a6-112">Per usare la funzionalità, il comando viene specificato dopo `dotnet`, ad esempio [`dotnet build`](dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="2d9a6-112">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="2d9a6-113">Tutti gli argomenti che seguono il comando sono gli argomenti del comando.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-113">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="2d9a6-114">`dotnet` viene usato come comando autonomo solo per eseguire [app dipendenti dal framework](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="2d9a6-114">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="2d9a6-115">Per eseguire l'applicazione, ad esempio `dotnet myapp.dll`, specificare una DLL di applicazione dopo il verbo `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-115">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="2d9a6-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2d9a6-116">Options</span></span>

`-v|--verbose`

<span data-ttu-id="2d9a6-117">Abilita l'output dettagliato.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-117">Enables verbose output.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2d9a6-118">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-118">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2d9a6-119">Versione del framework condiviso installato da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-119">Version of the installed Shared Framework to use to run the application.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="2d9a6-120">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-120">Path containing probing policy and assemblies to probe.</span></span>

`--version`

<span data-ttu-id="2d9a6-121">Stampa la versione degli strumenti dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-121">Prints out the version of the CLI tooling.</span></span>

`--info`

<span data-ttu-id="2d9a6-122">Stampa informazioni dettagliate sull'ambiente e sugli strumenti dell'interfaccia della riga di comando, ad esempio il sistema operativo corrente, l'Agente integrità sistema di commit per la versione e altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-122">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-h|--help`

<span data-ttu-id="2d9a6-123">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-123">Prints out a short help for the command.</span></span> <span data-ttu-id="2d9a6-124">Se usato con `dotnet`, stampa anche un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="2d9a6-125">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="2d9a6-125">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="2d9a6-126">Generale</span><span class="sxs-lookup"><span data-stu-id="2d9a6-126">General</span></span>

<span data-ttu-id="2d9a6-127">Comando</span><span class="sxs-lookup"><span data-stu-id="2d9a6-127">Command</span></span> | <span data-ttu-id="2d9a6-128">Funzione</span><span class="sxs-lookup"><span data-stu-id="2d9a6-128">Function</span></span>
--- | ---
[<span data-ttu-id="2d9a6-129">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="2d9a6-129">dotnet-build</span></span>](dotnet-build.md) | <span data-ttu-id="2d9a6-130">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-130">Builds a .NET Core application.</span></span>
[<span data-ttu-id="2d9a6-131">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="2d9a6-131">dotnet-clean</span></span>](dotnet-clean.md) | <span data-ttu-id="2d9a6-132">Consente di pulire gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-132">Clean build output(s).</span></span>
[<span data-ttu-id="2d9a6-133">dotnet-migrate</span><span class="sxs-lookup"><span data-stu-id="2d9a6-133">dotnet-migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="2d9a6-134">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-134">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>
[<span data-ttu-id="2d9a6-135">dotnet-msbuild</span><span class="sxs-lookup"><span data-stu-id="2d9a6-135">dotnet-msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="2d9a6-136">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-136">Provides access to the MSBuild command line.</span></span>
[<span data-ttu-id="2d9a6-137">dotnet-new</span><span class="sxs-lookup"><span data-stu-id="2d9a6-137">dotnet-new</span></span>](dotnet-new.md) | <span data-ttu-id="2d9a6-138">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-138">Initializes a C# or F# project for a given template.</span></span>
[<span data-ttu-id="2d9a6-139">dotnet-pack</span><span class="sxs-lookup"><span data-stu-id="2d9a6-139">dotnet-pack</span></span>](dotnet-pack.md) | <span data-ttu-id="2d9a6-140">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-140">Creates a NuGet package of your code.</span></span>
[<span data-ttu-id="2d9a6-141">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="2d9a6-141">dotnet-publish</span></span>](dotnet-publish.md) | <span data-ttu-id="2d9a6-142">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-142">Publishes a .NET framework-dependent or self-contained application.</span></span>
[<span data-ttu-id="2d9a6-143">dotnet-restore</span><span class="sxs-lookup"><span data-stu-id="2d9a6-143">dotnet-restore</span></span>](dotnet-restore.md) | <span data-ttu-id="2d9a6-144">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-144">Restores the dependencies for a given application.</span></span>
[<span data-ttu-id="2d9a6-145">dotnet-run</span><span class="sxs-lookup"><span data-stu-id="2d9a6-145">dotnet-run</span></span>](dotnet-run.md) | <span data-ttu-id="2d9a6-146">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-146">Runs the application from source.</span></span>
[<span data-ttu-id="2d9a6-147">dotnet-sln</span><span class="sxs-lookup"><span data-stu-id="2d9a6-147">dotnet-sln</span></span>](dotnet-sln.md) | <span data-ttu-id="2d9a6-148">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-148">Options to add, remove, and list projects in a solution file.</span></span>
[<span data-ttu-id="2d9a6-149">dotnet-test</span><span class="sxs-lookup"><span data-stu-id="2d9a6-149">dotnet-test</span></span>](dotnet-test.md) | <span data-ttu-id="2d9a6-150">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-150">Runs tests using a test runner.</span></span>

### <a name="project-references"></a><span data-ttu-id="2d9a6-151">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="2d9a6-151">Project references</span></span>

<span data-ttu-id="2d9a6-152">Comando</span><span class="sxs-lookup"><span data-stu-id="2d9a6-152">Command</span></span> | <span data-ttu-id="2d9a6-153">Funzione</span><span class="sxs-lookup"><span data-stu-id="2d9a6-153">Function</span></span>
--- | ---
[<span data-ttu-id="2d9a6-154">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="2d9a6-154">dotnet-add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="2d9a6-155">Aggiungere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-155">Add a project reference.</span></span>
[<span data-ttu-id="2d9a6-156">dotnet-list reference</span><span class="sxs-lookup"><span data-stu-id="2d9a6-156">dotnet-list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="2d9a6-157">Elencare i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-157">List project references.</span></span>
[<span data-ttu-id="2d9a6-158">dotnet-remove reference</span><span class="sxs-lookup"><span data-stu-id="2d9a6-158">dotnet-remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="2d9a6-159">Rimuovere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-159">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="2d9a6-160">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="2d9a6-160">NuGet packages</span></span>

<span data-ttu-id="2d9a6-161">Comando</span><span class="sxs-lookup"><span data-stu-id="2d9a6-161">Command</span></span> | <span data-ttu-id="2d9a6-162">Funzione</span><span class="sxs-lookup"><span data-stu-id="2d9a6-162">Function</span></span>
--- | ---
[<span data-ttu-id="2d9a6-163">dotnet-add package</span><span class="sxs-lookup"><span data-stu-id="2d9a6-163">dotnet-add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="2d9a6-164">Aggiungere un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-164">Add a NuGet package.</span></span>
[<span data-ttu-id="2d9a6-165">dotnet-remove package</span><span class="sxs-lookup"><span data-stu-id="2d9a6-165">dotnet-remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="2d9a6-166">Rimuovere un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-166">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="2d9a6-167">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="2d9a6-167">NuGet commands</span></span>

<span data-ttu-id="2d9a6-168">Comando</span><span class="sxs-lookup"><span data-stu-id="2d9a6-168">Command</span></span> | <span data-ttu-id="2d9a6-169">Funzione</span><span class="sxs-lookup"><span data-stu-id="2d9a6-169">Function</span></span>
--- | ---
[<span data-ttu-id="2d9a6-170">dotnet-nuget delete</span><span class="sxs-lookup"><span data-stu-id="2d9a6-170">dotnet-nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="2d9a6-171">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-171">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="2d9a6-172">dotnet-nuget locals</span><span class="sxs-lookup"><span data-stu-id="2d9a6-172">dotnet-nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="2d9a6-173">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-173">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="2d9a6-174">dotnet-nuget push</span><span class="sxs-lookup"><span data-stu-id="2d9a6-174">dotnet-nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="2d9a6-175">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-175">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="2d9a6-176">Esempi</span><span class="sxs-lookup"><span data-stu-id="2d9a6-176">Examples</span></span>

<span data-ttu-id="2d9a6-177">Inizializzare un'applicazione console .NET Core di esempio che può essere compilata ed eseguita:</span><span class="sxs-lookup"><span data-stu-id="2d9a6-177">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="2d9a6-178">Ripristinare le dipendenze per una determinata applicazione:</span><span class="sxs-lookup"><span data-stu-id="2d9a6-178">Restore dependencies for a given application:</span></span>

`dotnet restore`

<span data-ttu-id="2d9a6-179">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="2d9a6-179">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="2d9a6-180">Eseguire un'app dipendente dal framework denominata `myapp.dll`:</span><span class="sxs-lookup"><span data-stu-id="2d9a6-180">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="2d9a6-181">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="2d9a6-181">Environment variables</span></span>

`DOTNET_PACKAGES`

<span data-ttu-id="2d9a6-182">Cache dei pacchetti principali.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-182">The primary package cache.</span></span> <span data-ttu-id="2d9a6-183">Se non è impostata, il percorso predefinito è `$HOME/.nuget/packages` in Unix o `%HOME%\NuGet\Packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-183">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2d9a6-184">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-184">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2d9a6-185">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-185">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2d9a6-186">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`). In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="2d9a6-186">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2d9a6-187">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="2d9a6-187">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

