---
title: Comando dotnet
description: Informazioni sul comando dotnet (il driver generico per l'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
ms.date: 02/13/2020
ms.openlocfilehash: da37c5cc3b019851e245fa3f65ae9dfb8a3fef54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398895"
---
# <a name="dotnet-command"></a><span data-ttu-id="4b747-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="4b747-103">dotnet command</span></span>

<span data-ttu-id="4b747-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="4b747-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4b747-105">Nome</span><span class="sxs-lookup"><span data-stu-id="4b747-105">Name</span></span>

<span data-ttu-id="4b747-106">`dotnet`- Il driver generico per l'interfaccia della riga di comando di .NET Core.- The generic driver for the .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="4b747-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4b747-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4b747-107">Synopsis</span></span>

<span data-ttu-id="4b747-108">Per ottenere informazioni sui comandi disponibili e sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="4b747-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

<span data-ttu-id="4b747-109">Per eseguire un comando (richiede l'installazione SDK):</span><span class="sxs-lookup"><span data-stu-id="4b747-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

<span data-ttu-id="4b747-110">Per eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="4b747-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="4b747-111">`--roll-forward`è disponibile a partire da .NET Core 3.x.</span><span class="sxs-lookup"><span data-stu-id="4b747-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="4b747-112">Utilizzare `--roll-forward-on-no-candidate-fx` per .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="4b747-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="4b747-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b747-113">Description</span></span>

<span data-ttu-id="4b747-114">Il `dotnet` comando ha due funzioni:</span><span class="sxs-lookup"><span data-stu-id="4b747-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="4b747-115">Fornisce comandi per l'utilizzo di progetti .NET Core.It provides commands for working with .NET Core projects.</span><span class="sxs-lookup"><span data-stu-id="4b747-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="4b747-116">Ad esempio, [`dotnet build`](dotnet-build.md) compila un progetto.</span><span class="sxs-lookup"><span data-stu-id="4b747-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="4b747-117">Ogni comando definisce le proprie opzioni e argomenti.</span><span class="sxs-lookup"><span data-stu-id="4b747-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="4b747-118">Tutti i `--help` comandi supportano l'opzione per stampare una breve documentazione su come utilizzare il comando.</span><span class="sxs-lookup"><span data-stu-id="4b747-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="4b747-119">Esegue applicazioni .NET Core.It runs .NET Core applications.</span><span class="sxs-lookup"><span data-stu-id="4b747-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="4b747-120">Specificare il percorso `.dll` di un file dell'applicazione per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b747-120">You specify the path to an application `.dll` file to run the application.</span></span> <span data-ttu-id="4b747-121">Ad esempio, `dotnet myapp.dll` `myapp` esegue l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b747-121">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="4b747-122">Per informazioni sulle opzioni di distribuzione, [vedere Distribuzione di applicazioni .NET Core.See .NET Core application deployment](../deploying/index.md) to learn about deployment options.</span><span class="sxs-lookup"><span data-stu-id="4b747-122">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="4b747-123">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4b747-123">Options</span></span>

<span data-ttu-id="4b747-124">Sono disponibili diverse `dotnet` opzioni per se stesso, per l'esecuzione di un comando e per l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b747-124">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="4b747-125">Opzioni per dotnet da solo</span><span class="sxs-lookup"><span data-stu-id="4b747-125">Options for dotnet by itself</span></span>

<span data-ttu-id="4b747-126">Le seguenti opzioni `dotnet` sono per sé.</span><span class="sxs-lookup"><span data-stu-id="4b747-126">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="4b747-127">Ad esempio: `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="4b747-127">For example, `dotnet --info`.</span></span> <span data-ttu-id="4b747-128">Stampano informazioni sull'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b747-128">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="4b747-129">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b747-129">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="4b747-130">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="4b747-130">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="4b747-131">Stampa un elenco dei runtime .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="4b747-131">Prints out a list of the installed .NET Core runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="4b747-132">Stampa un elenco degli SDK di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="4b747-132">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4b747-133">Stampa un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="4b747-133">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="4b747-134">Opzioni SDK per l'esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="4b747-134">SDK options for running a command</span></span>

<span data-ttu-id="4b747-135">Le seguenti opzioni `dotnet` sono per con un comando.</span><span class="sxs-lookup"><span data-stu-id="4b747-135">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="4b747-136">Ad esempio: `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4b747-136">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="4b747-137">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="4b747-137">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="4b747-138">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="4b747-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4b747-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="4b747-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="4b747-140">Non supportato in ogni comando.</span><span class="sxs-lookup"><span data-stu-id="4b747-140">Not supported in every command.</span></span> <span data-ttu-id="4b747-141">Vedere la pagina dei comandi specifica per determinare se questa opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4b747-141">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4b747-142">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="4b747-142">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="4b747-143">Ogni comando definisce le opzioni specifiche di tale comando.</span><span class="sxs-lookup"><span data-stu-id="4b747-143">Each command defines options specific to that command.</span></span> <span data-ttu-id="4b747-144">Vedere la pagina dei comandi specifici per un elenco delle opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="4b747-144">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="4b747-145">Opzioni di runtime</span><span class="sxs-lookup"><span data-stu-id="4b747-145">Runtime options</span></span>

<span data-ttu-id="4b747-146">Quando `dotnet` si esegue un'applicazione, sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4b747-146">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="4b747-147">Ad esempio: `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="4b747-147">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="4b747-148">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="4b747-148">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="4b747-149">Percorso di un file *.deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="4b747-149">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="4b747-150">Un file *deps.json* contiene un elenco di dipendenze, dipendenze di compilazione e informazioni sulla versione utilizzate per risolvere i conflitti tra assembly.</span><span class="sxs-lookup"><span data-stu-id="4b747-150">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="4b747-151">Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="4b747-151">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="4b747-152">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b747-152">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="4b747-153">Percorso di un file *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="4b747-153">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="4b747-154">Un file *runtimeconfig.json* è un file di configurazione che contiene le impostazioni di runtime.</span><span class="sxs-lookup"><span data-stu-id="4b747-154">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="4b747-155">Per ulteriori informazioni, vedere Impostazioni di configurazione di [runtime di .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="4b747-155">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="4b747-156">**`--roll-forward-on-no-candidate-fx <N>`\*\*\*\*Disponibile in .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="4b747-156">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="4b747-157">Definisce il comportamento quando il framework condiviso richiesto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4b747-157">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="4b747-158">`N` può essere:</span><span class="sxs-lookup"><span data-stu-id="4b747-158">`N` can be:</span></span>

  - <span data-ttu-id="4b747-159">`0` - Disabilitare anche il roll forward per la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="4b747-159">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="4b747-160">`1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale.</span><span class="sxs-lookup"><span data-stu-id="4b747-160">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="4b747-161">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="4b747-161">This is the default behavior.</span></span>
  - <span data-ttu-id="4b747-162">`2` - Eseguire il roll forward per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="4b747-162">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="4b747-163">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4b747-163">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="4b747-164">**`--roll-forward <SETTING>`\*\*\*\*Disponibile a partire da .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="4b747-164">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="4b747-165">Controlla il modo in cui il rollforward viene applicato all'app.</span><span class="sxs-lookup"><span data-stu-id="4b747-165">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="4b747-166">Può `SETTING` essere uno dei seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="4b747-166">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="4b747-167">Se non `Minor` specificato, è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4b747-167">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="4b747-168">`LatestPatch`- Roll forward alla versione patch più alta.</span><span class="sxs-lookup"><span data-stu-id="4b747-168">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="4b747-169">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="4b747-169">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="4b747-170">`Minor`- Roll forward alla versione secondaria più bassa superiore, se richiesta versione secondaria è mancante.</span><span class="sxs-lookup"><span data-stu-id="4b747-170">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="4b747-171">Se la versione secondaria richiesta è presente, viene usato il criterio LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="4b747-171">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="4b747-172">`Major`- Roll forward alla versione principale superiore più bassa e versione secondaria più bassa, se manca la versione principale richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b747-172">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="4b747-173">Se la versione principale richiesta è presente, viene usato il criterio Minor.</span><span class="sxs-lookup"><span data-stu-id="4b747-173">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="4b747-174">`LatestMinor`- Passa alla versione secondaria più alta, anche se è presente la versione secondaria richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b747-174">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="4b747-175">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="4b747-175">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="4b747-176">`LatestMajor`- Passa alla versione principale e secondaria più alta, anche se è presente la versione principale richiesta.</span><span class="sxs-lookup"><span data-stu-id="4b747-176">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="4b747-177">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="4b747-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="4b747-178">`Disable`- Non andare avanti.</span><span class="sxs-lookup"><span data-stu-id="4b747-178">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="4b747-179">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="4b747-179">Only bind to specified version.</span></span> <span data-ttu-id="4b747-180">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="4b747-180">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="4b747-181">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="4b747-181">This value is only recommended for testing.</span></span>

<span data-ttu-id="4b747-182">Ad eccezione `Disable`di , tutte le impostazioni utilizzeranno la versione di patch più alta disponibile.</span><span class="sxs-lookup"><span data-stu-id="4b747-182">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="4b747-183">Il comportamento di rollforward può essere configurato anche in una proprietà del file di progetto, in una proprietà del file di configurazione di runtime e in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b747-183">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="4b747-184">Per ulteriori informazioni, vedere [Rollforward di runtime di versione principale](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4b747-184">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="4b747-185">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="4b747-185">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="4b747-186">Generale</span><span class="sxs-lookup"><span data-stu-id="4b747-186">General</span></span>

| <span data-ttu-id="4b747-187">Comando</span><span class="sxs-lookup"><span data-stu-id="4b747-187">Command</span></span>                                       | <span data-ttu-id="4b747-188">Funzione</span><span class="sxs-lookup"><span data-stu-id="4b747-188">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="4b747-189">dotnet build</span><span class="sxs-lookup"><span data-stu-id="4b747-189">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="4b747-190">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b747-190">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="4b747-191">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="4b747-191">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="4b747-192">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="4b747-192">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="4b747-193">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="4b747-193">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="4b747-194">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4b747-194">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="4b747-195">dotnet help</span><span class="sxs-lookup"><span data-stu-id="4b747-195">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="4b747-196">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="4b747-196">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="4b747-197">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="4b747-197">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="4b747-198">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="4b747-198">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="4b747-199">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4b747-199">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="4b747-200">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4b747-200">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="4b747-201">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4b747-201">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="4b747-202">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="4b747-202">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="4b747-203">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="4b747-203">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="4b747-204">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="4b747-204">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="4b747-205">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4b747-205">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="4b747-206">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="4b747-206">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="4b747-207">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="4b747-207">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="4b747-208">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b747-208">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="4b747-209">dotnet run</span><span class="sxs-lookup"><span data-stu-id="4b747-209">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="4b747-210">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="4b747-210">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="4b747-211">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="4b747-211">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="4b747-212">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4b747-212">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="4b747-213">dotnet store</span><span class="sxs-lookup"><span data-stu-id="4b747-213">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="4b747-214">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="4b747-214">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="4b747-215">test dotnet</span><span class="sxs-lookup"><span data-stu-id="4b747-215">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="4b747-216">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="4b747-216">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="4b747-217">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="4b747-217">Project references</span></span>

<span data-ttu-id="4b747-218">Comando</span><span class="sxs-lookup"><span data-stu-id="4b747-218">Command</span></span> | <span data-ttu-id="4b747-219">Funzione</span><span class="sxs-lookup"><span data-stu-id="4b747-219">Function</span></span>
--- | ---
[<span data-ttu-id="4b747-220">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="4b747-220">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="4b747-221">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="4b747-221">Adds a project reference.</span></span>
[<span data-ttu-id="4b747-222">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="4b747-222">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="4b747-223">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="4b747-223">Lists project references.</span></span>
[<span data-ttu-id="4b747-224">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="4b747-224">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="4b747-225">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="4b747-225">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="4b747-226">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="4b747-226">NuGet packages</span></span>

<span data-ttu-id="4b747-227">Comando</span><span class="sxs-lookup"><span data-stu-id="4b747-227">Command</span></span> | <span data-ttu-id="4b747-228">Funzione</span><span class="sxs-lookup"><span data-stu-id="4b747-228">Function</span></span>
--- | ---
[<span data-ttu-id="4b747-229">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="4b747-229">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="4b747-230">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="4b747-230">Adds a NuGet package.</span></span>
[<span data-ttu-id="4b747-231">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="4b747-231">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="4b747-232">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="4b747-232">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="4b747-233">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="4b747-233">NuGet commands</span></span>

<span data-ttu-id="4b747-234">Comando</span><span class="sxs-lookup"><span data-stu-id="4b747-234">Command</span></span> | <span data-ttu-id="4b747-235">Funzione</span><span class="sxs-lookup"><span data-stu-id="4b747-235">Function</span></span>
--- | ---
[<span data-ttu-id="4b747-236">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="4b747-236">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="4b747-237">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="4b747-237">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="4b747-238">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="4b747-238">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="4b747-239">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="4b747-239">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="4b747-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="4b747-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="4b747-241">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="4b747-241">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="4b747-242">Comandi globali, del percorso degli strumenti e degli strumenti locali</span><span class="sxs-lookup"><span data-stu-id="4b747-242">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="4b747-243">Gli strumenti sono applicazioni console installate da pacchetti NuGet e richiamate dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4b747-243">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="4b747-244">È possibile scrivere strumenti da soli o installare strumenti scritti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="4b747-244">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="4b747-245">Gli strumenti sono noti anche come strumenti globali, strumenti per il percorso degli strumenti e strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="4b747-245">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="4b747-246">Per ulteriori informazioni, vedere [Panoramica degli strumenti .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4b747-246">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="4b747-247">Gli strumenti globali e per corsi degli strumenti sono disponibili a partire da .NET Core SDK 2.1.</span><span class="sxs-lookup"><span data-stu-id="4b747-247">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="4b747-248">Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.</span><span class="sxs-lookup"><span data-stu-id="4b747-248">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="4b747-249">Comando</span><span class="sxs-lookup"><span data-stu-id="4b747-249">Command</span></span> | <span data-ttu-id="4b747-250">Funzione</span><span class="sxs-lookup"><span data-stu-id="4b747-250">Function</span></span>
--- | ---
[<span data-ttu-id="4b747-251">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="4b747-251">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="4b747-252">Installa uno strumento sul computer.</span><span class="sxs-lookup"><span data-stu-id="4b747-252">Installs a tool on your machine.</span></span>
[<span data-ttu-id="4b747-253">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="4b747-253">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="4b747-254">Elenca tutti gli strumenti globali, del percorso degli strumenti o locali attualmente installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4b747-254">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="4b747-255">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="4b747-255">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="4b747-256">Disinstalla uno strumento dal computer.</span><span class="sxs-lookup"><span data-stu-id="4b747-256">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="4b747-257">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="4b747-257">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="4b747-258">Aggiorna uno strumento installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="4b747-258">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="4b747-259">Strumenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="4b747-259">Additional tools</span></span>

<span data-ttu-id="4b747-260">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="4b747-260">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="4b747-261">Tali strumenti sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4b747-261">These tools are listed in the following table:</span></span>

| <span data-ttu-id="4b747-262">Strumento</span><span class="sxs-lookup"><span data-stu-id="4b747-262">Tool</span></span>                                              | <span data-ttu-id="4b747-263">Funzione</span><span class="sxs-lookup"><span data-stu-id="4b747-263">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="4b747-264">dev-certs</span><span class="sxs-lookup"><span data-stu-id="4b747-264">dev-certs</span></span>                                         | <span data-ttu-id="4b747-265">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4b747-265">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="4b747-266">Ef</span><span class="sxs-lookup"><span data-stu-id="4b747-266">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="4b747-267">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="4b747-267">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="4b747-268">sql-cache</span><span class="sxs-lookup"><span data-stu-id="4b747-268">sql-cache</span></span>                                         | <span data-ttu-id="4b747-269">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4b747-269">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="4b747-270">user-secrets</span><span class="sxs-lookup"><span data-stu-id="4b747-270">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="4b747-271">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4b747-271">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="4b747-272">orologio</span><span class="sxs-lookup"><span data-stu-id="4b747-272">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="4b747-273">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="4b747-273">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="4b747-274">Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="4b747-274">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="4b747-275">Esempi</span><span class="sxs-lookup"><span data-stu-id="4b747-275">Examples</span></span>

<span data-ttu-id="4b747-276">Creare una nuova applicazione console .NET Core:Create a new .NET Core console application:</span><span class="sxs-lookup"><span data-stu-id="4b747-276">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="4b747-277">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="4b747-277">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="4b747-278">Eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="4b747-278">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="4b747-279">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="4b747-279">Environment variables</span></span>

- <span data-ttu-id="4b747-280">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="4b747-280">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="4b747-281">Specifica il percorso dei runtime .NET Core, se non sono installati nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="4b747-281">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="4b747-282">Il percorso predefinito `C:\Program Files\dotnet`in Windows è .</span><span class="sxs-lookup"><span data-stu-id="4b747-282">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="4b747-283">Il percorso predefinito su Linux `/usr/share/dotnet`e macOS è .</span><span class="sxs-lookup"><span data-stu-id="4b747-283">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="4b747-284">Questa variabile di ambiente viene usata solo quando si eseguono app tramite file eseguibili generati (apphosts).</span><span class="sxs-lookup"><span data-stu-id="4b747-284">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="4b747-285">`DOTNET_ROOT(x86)`viene utilizzato invece quando si esegue un eseguibile a 32 bit su un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="4b747-285">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="4b747-286">La cartella dei pacchetti globali.</span><span class="sxs-lookup"><span data-stu-id="4b747-286">The global packages folder.</span></span> <span data-ttu-id="4b747-287">Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="4b747-287">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="4b747-288">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="4b747-288">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="4b747-289">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b747-289">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="4b747-290">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="4b747-290">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="4b747-291">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="4b747-291">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="4b747-292">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="4b747-292">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="4b747-293">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="4b747-293">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="4b747-294">Se non è impostato, il `true`valore predefinito è 1 (logico ).</span><span class="sxs-lookup"><span data-stu-id="4b747-294">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="4b747-295">Impostare su `false`0 (logico ) per non risolvere dal percorso globale e sono state isolate installazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b747-295">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="4b747-296">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="4b747-296">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="4b747-297">`DOTNET_ROLL_FORWARD`**Disponibile a partire da .NET Core 3.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="4b747-297">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="4b747-298">Determina il comportamento di rollforward.</span><span class="sxs-lookup"><span data-stu-id="4b747-298">Determines roll forward behavior.</span></span> <span data-ttu-id="4b747-299">Per altre informazioni, `--roll-forward` vedere l'opzione più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4b747-299">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="4b747-300">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`**Disponibile in .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="4b747-300">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="4b747-301">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="4b747-301">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="4b747-302">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="4b747-302">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="4b747-303">Imposta la lingua dell'interfaccia utente dell'interfaccia della riga di comando utilizzando un valore delle impostazioni locali, `en-us`ad esempio .</span><span class="sxs-lookup"><span data-stu-id="4b747-303">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="4b747-304">The supported values are the same as for Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b747-304">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="4b747-305">Per ulteriori informazioni, vedere la sezione sulla modifica della lingua del programma di installazione nella [documentazione relativa all'installazione](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4b747-305">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="4b747-306">Si applicano le regole di gestione delle risorse .NET, pertanto non è necessario selezionare una corrispondenza&mdash;esatta, è anche possibile selezionare i discendenti nell'albero. `CultureInfo`</span><span class="sxs-lookup"><span data-stu-id="4b747-306">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="4b747-307">Ad esempio, se si `fr-CA`imposta su , l'interfaccia della riga di comando troverà e utilizzerà le `fr` traduzioni.</span><span class="sxs-lookup"><span data-stu-id="4b747-307">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="4b747-308">Se si imposta su una lingua non supportata, l'interfaccia della riga di comando esegue il fallback all'inglese.</span><span class="sxs-lookup"><span data-stu-id="4b747-308">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="4b747-309">Per gli eseguibili generati abilitati per GUI - disabilita la finestra popup della finestra di dialogo che normalmente mostra per alcune classi di errori.</span><span class="sxs-lookup"><span data-stu-id="4b747-309">For GUI-enabled generated executables - disables dialog popup which normally shows for certain classes of errors.</span></span> <span data-ttu-id="4b747-310">Scrive `stderr` e esce solo in questi casi.</span><span class="sxs-lookup"><span data-stu-id="4b747-310">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="4b747-311">Equivalente all'opzione `--additional-deps`CLI .</span><span class="sxs-lookup"><span data-stu-id="4b747-311">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="4b747-312">Esegue l'override del RID rilevato.</span><span class="sxs-lookup"><span data-stu-id="4b747-312">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="4b747-313">Posizione dell'"archivio condiviso" in cui viene eseguito il fallback della risoluzione dell'assembly in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="4b747-313">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="4b747-314">Elenco di assembly da cui caricare ed eseguire gli hook di avvio.</span><span class="sxs-lookup"><span data-stu-id="4b747-314">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="4b747-315">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="4b747-315">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="4b747-316">Controlla la traccia diagnostica dai `dotnet.exe`componenti `hostfxr`di `hostpolicy`hosting, ad esempio , e .</span><span class="sxs-lookup"><span data-stu-id="4b747-316">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b747-317">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b747-317">See also</span></span>

- <span data-ttu-id="4b747-318">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)</span><span class="sxs-lookup"><span data-stu-id="4b747-318">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)</span></span>
- [<span data-ttu-id="4b747-319">Impostazioni di configurazione di runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="4b747-319">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
