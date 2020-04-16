---
title: Comando dotnet
description: Informazioni sul comando dotnet (il driver generico per l'interfaccia della riga di comando di .NET Core) e sul relativo utilizzo.
ms.date: 02/13/2020
ms.openlocfilehash: d700f35f3c977524ff3857da99519882eb0136e9
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463278"
---
# <a name="dotnet-command"></a><span data-ttu-id="887b3-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="887b3-103">dotnet command</span></span>

<span data-ttu-id="887b3-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="887b3-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="887b3-105">Nome</span><span class="sxs-lookup"><span data-stu-id="887b3-105">Name</span></span>

<span data-ttu-id="887b3-106">`dotnet`- Il driver generico per l'interfaccia della riga di comando di .NET Core.- The generic driver for the .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="887b3-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="887b3-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="887b3-107">Synopsis</span></span>

<span data-ttu-id="887b3-108">Per ottenere informazioni sui comandi disponibili e sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="887b3-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="887b3-109">Per eseguire un comando (richiede l'installazione SDK):</span><span class="sxs-lookup"><span data-stu-id="887b3-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="887b3-110">Per eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="887b3-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="887b3-111">`--roll-forward`è disponibile a partire da .NET Core 3.x.</span><span class="sxs-lookup"><span data-stu-id="887b3-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="887b3-112">Utilizzare `--roll-forward-on-no-candidate-fx` per .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="887b3-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="887b3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="887b3-113">Description</span></span>

<span data-ttu-id="887b3-114">Il `dotnet` comando ha due funzioni:</span><span class="sxs-lookup"><span data-stu-id="887b3-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="887b3-115">Fornisce comandi per l'utilizzo di progetti .NET Core.It provides commands for working with .NET Core projects.</span><span class="sxs-lookup"><span data-stu-id="887b3-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="887b3-116">Ad esempio, [`dotnet build`](dotnet-build.md) compila un progetto.</span><span class="sxs-lookup"><span data-stu-id="887b3-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="887b3-117">Ogni comando definisce le proprie opzioni e argomenti.</span><span class="sxs-lookup"><span data-stu-id="887b3-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="887b3-118">Tutti i `--help` comandi supportano l'opzione per stampare una breve documentazione su come utilizzare il comando.</span><span class="sxs-lookup"><span data-stu-id="887b3-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="887b3-119">Esegue applicazioni .NET Core.It runs .NET Core applications.</span><span class="sxs-lookup"><span data-stu-id="887b3-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="887b3-120">Specificare il percorso `.dll` di un file dell'applicazione per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="887b3-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="887b3-121">Eseguire l'applicazione significa trovare ed eseguire il punto di ingresso, `Main` che nel caso delle applicazioni console è il metodo.</span><span class="sxs-lookup"><span data-stu-id="887b3-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="887b3-122">Ad esempio, `dotnet myapp.dll` `myapp` esegue l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="887b3-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="887b3-123">Per informazioni sulle opzioni di distribuzione, [vedere Distribuzione di applicazioni .NET Core.See .NET Core application deployment](../deploying/index.md) to learn about deployment options.</span><span class="sxs-lookup"><span data-stu-id="887b3-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="887b3-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="887b3-124">Options</span></span>

<span data-ttu-id="887b3-125">Sono disponibili diverse `dotnet` opzioni per se stesso, per l'esecuzione di un comando e per l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="887b3-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="887b3-126">Opzioni per dotnet da solo</span><span class="sxs-lookup"><span data-stu-id="887b3-126">Options for dotnet by itself</span></span>

<span data-ttu-id="887b3-127">Le seguenti opzioni `dotnet` sono per sé.</span><span class="sxs-lookup"><span data-stu-id="887b3-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="887b3-128">Ad esempio: `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="887b3-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="887b3-129">Stampano informazioni sull'ambiente.</span><span class="sxs-lookup"><span data-stu-id="887b3-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="887b3-130">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="887b3-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="887b3-131">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="887b3-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="887b3-132">Stampa un elenco dei runtime .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="887b3-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="887b3-133">Una versione x86 dell'SDK elenca solo i runtime x86 e una versione x64 del SDK elenca solo i runtime x64.</span><span class="sxs-lookup"><span data-stu-id="887b3-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="887b3-134">Stampa un elenco degli SDK di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="887b3-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="887b3-135">Stampa un elenco dei comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="887b3-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="887b3-136">Opzioni SDK per l'esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="887b3-136">SDK options for running a command</span></span>

<span data-ttu-id="887b3-137">Le seguenti opzioni `dotnet` sono per con un comando.</span><span class="sxs-lookup"><span data-stu-id="887b3-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="887b3-138">Ad esempio: `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="887b3-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="887b3-139">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="887b3-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="887b3-140">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="887b3-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="887b3-141">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="887b3-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="887b3-142">Non supportato in ogni comando.</span><span class="sxs-lookup"><span data-stu-id="887b3-142">Not supported in every command.</span></span> <span data-ttu-id="887b3-143">Vedere la pagina dei comandi specifica per determinare se questa opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="887b3-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="887b3-144">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="887b3-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="887b3-145">Ogni comando definisce le opzioni specifiche di tale comando.</span><span class="sxs-lookup"><span data-stu-id="887b3-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="887b3-146">Vedere la pagina dei comandi specifici per un elenco delle opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="887b3-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="887b3-147">Opzioni di runtime</span><span class="sxs-lookup"><span data-stu-id="887b3-147">Runtime options</span></span>

<span data-ttu-id="887b3-148">Quando `dotnet` si esegue un'applicazione, sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="887b3-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="887b3-149">Ad esempio: `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="887b3-149">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="887b3-150">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="887b3-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="887b3-151">Percorso di un file *.deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="887b3-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="887b3-152">Un file *deps.json* contiene un elenco di dipendenze, dipendenze di compilazione e informazioni sulla versione utilizzate per risolvere i conflitti tra assembly.</span><span class="sxs-lookup"><span data-stu-id="887b3-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="887b3-153">Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="887b3-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="887b3-154">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="887b3-154">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="887b3-155">Percorso di un file *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="887b3-155">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="887b3-156">Un file *runtimeconfig.json* è un file di configurazione che contiene le impostazioni di runtime.</span><span class="sxs-lookup"><span data-stu-id="887b3-156">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="887b3-157">Per ulteriori informazioni, vedere Impostazioni di configurazione di [runtime di .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="887b3-157">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="887b3-158">**`--roll-forward-on-no-candidate-fx <N>`\*\*\*\*Disponibile in .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="887b3-158">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="887b3-159">Definisce il comportamento quando il framework condiviso richiesto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="887b3-159">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="887b3-160">`N` può essere:</span><span class="sxs-lookup"><span data-stu-id="887b3-160">`N` can be:</span></span>

  - <span data-ttu-id="887b3-161">`0` - Disabilitare anche il roll forward per la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="887b3-161">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="887b3-162">`1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale.</span><span class="sxs-lookup"><span data-stu-id="887b3-162">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="887b3-163">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="887b3-163">This is the default behavior.</span></span>
  - <span data-ttu-id="887b3-164">`2` - Eseguire il roll forward per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="887b3-164">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="887b3-165">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="887b3-165">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="887b3-166">**`--roll-forward <SETTING>`\*\*\*\*Disponibile a partire da .NET Core SDK 3.0.**</span><span class="sxs-lookup"><span data-stu-id="887b3-166">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="887b3-167">Controlla il modo in cui il rollforward viene applicato all'app.</span><span class="sxs-lookup"><span data-stu-id="887b3-167">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="887b3-168">Può `SETTING` essere uno dei seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="887b3-168">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="887b3-169">Se non `Minor` specificato, è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="887b3-169">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="887b3-170">`LatestPatch`- Roll forward alla versione patch più alta.</span><span class="sxs-lookup"><span data-stu-id="887b3-170">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="887b3-171">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="887b3-171">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="887b3-172">`Minor`- Roll forward alla versione secondaria più bassa superiore, se richiesta versione secondaria è mancante.</span><span class="sxs-lookup"><span data-stu-id="887b3-172">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="887b3-173">Se la versione secondaria richiesta è presente, viene usato il criterio LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="887b3-173">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="887b3-174">`Major`- Roll forward alla versione principale superiore più bassa e versione secondaria più bassa, se manca la versione principale richiesta.</span><span class="sxs-lookup"><span data-stu-id="887b3-174">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="887b3-175">Se la versione principale richiesta è presente, viene usato il criterio Minor.</span><span class="sxs-lookup"><span data-stu-id="887b3-175">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="887b3-176">`LatestMinor`- Passa alla versione secondaria più alta, anche se è presente la versione secondaria richiesta.</span><span class="sxs-lookup"><span data-stu-id="887b3-176">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="887b3-177">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="887b3-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="887b3-178">`LatestMajor`- Passa alla versione principale e secondaria più alta, anche se è presente la versione principale richiesta.</span><span class="sxs-lookup"><span data-stu-id="887b3-178">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="887b3-179">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="887b3-179">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="887b3-180">`Disable`- Non andare avanti.</span><span class="sxs-lookup"><span data-stu-id="887b3-180">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="887b3-181">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="887b3-181">Only bind to specified version.</span></span> <span data-ttu-id="887b3-182">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="887b3-182">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="887b3-183">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="887b3-183">This value is only recommended for testing.</span></span>

<span data-ttu-id="887b3-184">Ad eccezione `Disable`di , tutte le impostazioni utilizzeranno la versione di patch più alta disponibile.</span><span class="sxs-lookup"><span data-stu-id="887b3-184">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="887b3-185">Il comportamento di rollforward può essere configurato anche in una proprietà del file di progetto, in una proprietà del file di configurazione di runtime e in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="887b3-185">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="887b3-186">Per ulteriori informazioni, vedere [Rollforward di runtime di versione principale](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="887b3-186">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="887b3-187">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="887b3-187">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="887b3-188">Generale</span><span class="sxs-lookup"><span data-stu-id="887b3-188">General</span></span>

| <span data-ttu-id="887b3-189">Comando</span><span class="sxs-lookup"><span data-stu-id="887b3-189">Command</span></span>                                       | <span data-ttu-id="887b3-190">Funzione</span><span class="sxs-lookup"><span data-stu-id="887b3-190">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="887b3-191">dotnet build</span><span class="sxs-lookup"><span data-stu-id="887b3-191">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="887b3-192">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="887b3-192">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="887b3-193">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="887b3-193">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="887b3-194">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="887b3-194">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="887b3-195">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="887b3-195">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="887b3-196">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="887b3-196">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="887b3-197">dotnet help</span><span class="sxs-lookup"><span data-stu-id="887b3-197">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="887b3-198">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="887b3-198">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="887b3-199">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="887b3-199">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="887b3-200">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="887b3-200">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="887b3-201">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="887b3-201">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="887b3-202">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="887b3-202">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="887b3-203">dotnet new</span><span class="sxs-lookup"><span data-stu-id="887b3-203">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="887b3-204">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="887b3-204">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="887b3-205">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="887b3-205">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="887b3-206">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="887b3-206">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="887b3-207">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="887b3-207">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="887b3-208">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="887b3-208">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="887b3-209">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="887b3-209">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="887b3-210">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="887b3-210">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="887b3-211">dotnet run</span><span class="sxs-lookup"><span data-stu-id="887b3-211">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="887b3-212">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="887b3-212">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="887b3-213">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="887b3-213">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="887b3-214">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="887b3-214">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="887b3-215">dotnet store</span><span class="sxs-lookup"><span data-stu-id="887b3-215">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="887b3-216">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="887b3-216">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="887b3-217">dotnet test</span><span class="sxs-lookup"><span data-stu-id="887b3-217">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="887b3-218">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="887b3-218">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="887b3-219">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="887b3-219">Project references</span></span>

<span data-ttu-id="887b3-220">Comando</span><span class="sxs-lookup"><span data-stu-id="887b3-220">Command</span></span> | <span data-ttu-id="887b3-221">Funzione</span><span class="sxs-lookup"><span data-stu-id="887b3-221">Function</span></span>
--- | ---
[<span data-ttu-id="887b3-222">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="887b3-222">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="887b3-223">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="887b3-223">Adds a project reference.</span></span>
[<span data-ttu-id="887b3-224">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="887b3-224">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="887b3-225">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="887b3-225">Lists project references.</span></span>
[<span data-ttu-id="887b3-226">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="887b3-226">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="887b3-227">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="887b3-227">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="887b3-228">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="887b3-228">NuGet packages</span></span>

<span data-ttu-id="887b3-229">Comando</span><span class="sxs-lookup"><span data-stu-id="887b3-229">Command</span></span> | <span data-ttu-id="887b3-230">Funzione</span><span class="sxs-lookup"><span data-stu-id="887b3-230">Function</span></span>
--- | ---
[<span data-ttu-id="887b3-231">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="887b3-231">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="887b3-232">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="887b3-232">Adds a NuGet package.</span></span>
[<span data-ttu-id="887b3-233">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="887b3-233">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="887b3-234">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="887b3-234">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="887b3-235">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="887b3-235">NuGet commands</span></span>

<span data-ttu-id="887b3-236">Comando</span><span class="sxs-lookup"><span data-stu-id="887b3-236">Command</span></span> | <span data-ttu-id="887b3-237">Funzione</span><span class="sxs-lookup"><span data-stu-id="887b3-237">Function</span></span>
--- | ---
[<span data-ttu-id="887b3-238">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="887b3-238">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="887b3-239">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="887b3-239">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="887b3-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="887b3-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="887b3-241">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="887b3-241">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="887b3-242">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="887b3-242">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="887b3-243">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="887b3-243">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="887b3-244">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="887b3-244">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="887b3-245">Aggiunge un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="887b3-245">Adds a NuGet source.</span></span>
[<span data-ttu-id="887b3-246">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="887b3-246">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="887b3-247">Disabilita un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="887b3-247">Disables a NuGet source.</span></span>
[<span data-ttu-id="887b3-248">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="887b3-248">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="887b3-249">Abilita un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="887b3-249">Enables a NuGet source.</span></span>
[<span data-ttu-id="887b3-250">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="887b3-250">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="887b3-251">Elenca tutte le origini NuGet configurate.</span><span class="sxs-lookup"><span data-stu-id="887b3-251">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="887b3-252">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="887b3-252">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="887b3-253">Rimuove un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="887b3-253">Removes a NuGet source.</span></span>
[<span data-ttu-id="887b3-254">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="887b3-254">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="887b3-255">Aggiorna un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="887b3-255">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="887b3-256">Comandi globali, del percorso degli strumenti e degli strumenti locali</span><span class="sxs-lookup"><span data-stu-id="887b3-256">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="887b3-257">Gli strumenti sono applicazioni console installate da pacchetti NuGet e richiamate dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="887b3-257">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="887b3-258">È possibile scrivere strumenti da soli o installare strumenti scritti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="887b3-258">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="887b3-259">Gli strumenti sono noti anche come strumenti globali, strumenti per il percorso degli strumenti e strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="887b3-259">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="887b3-260">Per ulteriori informazioni, vedere [Panoramica degli strumenti .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="887b3-260">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="887b3-261">Gli strumenti globali e per corsi degli strumenti sono disponibili a partire da .NET Core SDK 2.1.</span><span class="sxs-lookup"><span data-stu-id="887b3-261">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="887b3-262">Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.</span><span class="sxs-lookup"><span data-stu-id="887b3-262">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="887b3-263">Comando</span><span class="sxs-lookup"><span data-stu-id="887b3-263">Command</span></span> | <span data-ttu-id="887b3-264">Funzione</span><span class="sxs-lookup"><span data-stu-id="887b3-264">Function</span></span>
--- | ---
[<span data-ttu-id="887b3-265">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="887b3-265">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="887b3-266">Installa uno strumento sul computer.</span><span class="sxs-lookup"><span data-stu-id="887b3-266">Installs a tool on your machine.</span></span>
[<span data-ttu-id="887b3-267">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="887b3-267">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="887b3-268">Elenca tutti gli strumenti globali, del percorso degli strumenti o locali attualmente installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="887b3-268">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="887b3-269">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="887b3-269">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="887b3-270">Disinstalla uno strumento dal computer.</span><span class="sxs-lookup"><span data-stu-id="887b3-270">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="887b3-271">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="887b3-271">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="887b3-272">Aggiorna uno strumento installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="887b3-272">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="887b3-273">Strumenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="887b3-273">Additional tools</span></span>

<span data-ttu-id="887b3-274">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="887b3-274">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="887b3-275">Tali strumenti sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="887b3-275">These tools are listed in the following table:</span></span>

| <span data-ttu-id="887b3-276">Strumento</span><span class="sxs-lookup"><span data-stu-id="887b3-276">Tool</span></span>                                              | <span data-ttu-id="887b3-277">Funzione</span><span class="sxs-lookup"><span data-stu-id="887b3-277">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="887b3-278">dev-certs</span><span class="sxs-lookup"><span data-stu-id="887b3-278">dev-certs</span></span>                                         | <span data-ttu-id="887b3-279">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="887b3-279">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="887b3-280">Ef</span><span class="sxs-lookup"><span data-stu-id="887b3-280">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="887b3-281">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="887b3-281">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="887b3-282">sql-cache</span><span class="sxs-lookup"><span data-stu-id="887b3-282">sql-cache</span></span>                                         | <span data-ttu-id="887b3-283">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="887b3-283">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="887b3-284">user-secrets</span><span class="sxs-lookup"><span data-stu-id="887b3-284">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="887b3-285">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="887b3-285">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="887b3-286">orologio</span><span class="sxs-lookup"><span data-stu-id="887b3-286">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="887b3-287">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="887b3-287">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="887b3-288">Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="887b3-288">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="887b3-289">Esempi</span><span class="sxs-lookup"><span data-stu-id="887b3-289">Examples</span></span>

<span data-ttu-id="887b3-290">Creare una nuova applicazione console .NET Core:Create a new .NET Core console application:</span><span class="sxs-lookup"><span data-stu-id="887b3-290">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="887b3-291">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="887b3-291">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="887b3-292">Eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="887b3-292">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="887b3-293">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="887b3-293">Environment variables</span></span>

- <span data-ttu-id="887b3-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="887b3-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="887b3-295">Specifica il percorso dei runtime .NET Core, se non sono installati nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="887b3-295">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="887b3-296">Il percorso predefinito `C:\Program Files\dotnet`in Windows è .</span><span class="sxs-lookup"><span data-stu-id="887b3-296">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="887b3-297">Il percorso predefinito su Linux `/usr/share/dotnet`e macOS è .</span><span class="sxs-lookup"><span data-stu-id="887b3-297">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="887b3-298">Questa variabile di ambiente viene usata solo quando si eseguono app tramite file eseguibili generati (apphosts).</span><span class="sxs-lookup"><span data-stu-id="887b3-298">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="887b3-299">`DOTNET_ROOT(x86)`viene utilizzato invece quando si esegue un eseguibile a 32 bit su un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="887b3-299">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="887b3-300">La cartella dei pacchetti globali.</span><span class="sxs-lookup"><span data-stu-id="887b3-300">The global packages folder.</span></span> <span data-ttu-id="887b3-301">Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="887b3-301">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="887b3-302">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="887b3-302">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="887b3-303">Specifica se i messaggi di benvenuto e di telemetria di .NET Core vengono visualizzati alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="887b3-303">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="887b3-304">Impostare `true` su per disattivare `true` `1`l'audio di questi messaggi (valori `yes` o accettati) o su `false` consentito (valori `false`, `0`o `no` accettati ).</span><span class="sxs-lookup"><span data-stu-id="887b3-304">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="887b3-305">Se non è impostato, il valore predefinito è `false` e i messaggi verranno visualizzati alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="887b3-305">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="887b3-306">Si noti che questo flag `DOTNET_CLI_TELEMETRY_OPTOUT` non ha alcun effetto sui dati di telemetria (vedere per la disattivazione dell'invio di dati di telemetria).</span><span class="sxs-lookup"><span data-stu-id="887b3-306">Note that this flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="887b3-307">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="887b3-307">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="887b3-308">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="887b3-308">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="887b3-309">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="887b3-309">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="887b3-310">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="887b3-310">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="887b3-311">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="887b3-311">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="887b3-312">Se non è impostato, il `true`valore predefinito è 1 (logico ).</span><span class="sxs-lookup"><span data-stu-id="887b3-312">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="887b3-313">Impostare su `false`0 (logico ) per non risolvere dal percorso globale e sono state isolate installazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="887b3-313">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="887b3-314">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="887b3-314">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="887b3-315">`DOTNET_ROLL_FORWARD`**Disponibile a partire da .NET Core 3.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="887b3-315">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="887b3-316">Determina il comportamento di rollforward.</span><span class="sxs-lookup"><span data-stu-id="887b3-316">Determines roll forward behavior.</span></span> <span data-ttu-id="887b3-317">Per altre informazioni, `--roll-forward` vedere l'opzione più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="887b3-317">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="887b3-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`**Disponibile in .NET Core 2.x SDK.**</span><span class="sxs-lookup"><span data-stu-id="887b3-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="887b3-319">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="887b3-319">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="887b3-320">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="887b3-320">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="887b3-321">Imposta la lingua dell'interfaccia utente dell'interfaccia della riga di comando utilizzando un valore delle impostazioni locali, `en-us`ad esempio .</span><span class="sxs-lookup"><span data-stu-id="887b3-321">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="887b3-322">The supported values are the same as for Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="887b3-322">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="887b3-323">Per ulteriori informazioni, vedere la sezione sulla modifica della lingua del programma di installazione nella [documentazione relativa all'installazione](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="887b3-323">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="887b3-324">Si applicano le regole di gestione delle risorse .NET, pertanto non è necessario selezionare una corrispondenza&mdash;esatta, è anche possibile selezionare i discendenti nell'albero. `CultureInfo`</span><span class="sxs-lookup"><span data-stu-id="887b3-324">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="887b3-325">Ad esempio, se si `fr-CA`imposta su , l'interfaccia della riga di comando troverà e utilizzerà le `fr` traduzioni.</span><span class="sxs-lookup"><span data-stu-id="887b3-325">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="887b3-326">Se si imposta su una lingua non supportata, l'interfaccia della riga di comando esegue il fallback all'inglese.</span><span class="sxs-lookup"><span data-stu-id="887b3-326">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="887b3-327">Per gli eseguibili generati abilitati per GUI - disabilita la finestra popup della finestra di dialogo, che normalmente mostra per alcune classi di errori.</span><span class="sxs-lookup"><span data-stu-id="887b3-327">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="887b3-328">Scrive `stderr` e esce solo in questi casi.</span><span class="sxs-lookup"><span data-stu-id="887b3-328">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="887b3-329">Equivalente all'opzione `--additional-deps`CLI .</span><span class="sxs-lookup"><span data-stu-id="887b3-329">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="887b3-330">Esegue l'override del RID rilevato.</span><span class="sxs-lookup"><span data-stu-id="887b3-330">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="887b3-331">Posizione dell'"archivio condiviso" in cui viene eseguito il fallback della risoluzione dell'assembly in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="887b3-331">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="887b3-332">Elenco di assembly da cui caricare ed eseguire gli hook di avvio.</span><span class="sxs-lookup"><span data-stu-id="887b3-332">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="887b3-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="887b3-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="887b3-334">Controlla la traccia diagnostica dai `dotnet.exe`componenti `hostfxr`di `hostpolicy`hosting, ad esempio , e .</span><span class="sxs-lookup"><span data-stu-id="887b3-334">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="887b3-335">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="887b3-335">See also</span></span>

- <span data-ttu-id="887b3-336">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)</span><span class="sxs-lookup"><span data-stu-id="887b3-336">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)</span></span>
- [<span data-ttu-id="887b3-337">Impostazioni di configurazione di runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="887b3-337">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
