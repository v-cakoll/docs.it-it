---
title: Comando dotnet
description: Informazioni sul comando DotNet (il driver generico per la interfaccia della riga di comando di .NET Core) e il relativo utilizzo.
ms.date: 02/13/2020
ms.openlocfilehash: 88e92b3ff5e8f68b980015a817434dd2d67df93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378834"
---
# <a name="dotnet-command"></a><span data-ttu-id="b4e2b-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="b4e2b-103">dotnet command</span></span>

<span data-ttu-id="b4e2b-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="b4e2b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b4e2b-105">Nome</span><span class="sxs-lookup"><span data-stu-id="b4e2b-105">Name</span></span>

<span data-ttu-id="b4e2b-106">`dotnet`-Il driver generico per la interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b4e2b-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b4e2b-107">Synopsis</span></span>

<span data-ttu-id="b4e2b-108">Per ottenere informazioni sui comandi disponibili e sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="b4e2b-109">Per eseguire un comando (richiede l'installazione dell'SDK):</span><span class="sxs-lookup"><span data-stu-id="b4e2b-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="b4e2b-110">Per eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="b4e2b-111">`--roll-forward`è disponibile a partire da .NET Core 3. x.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="b4e2b-112">Usare `--roll-forward-on-no-candidate-fx` per .NET Core 2. x.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="b4e2b-113">Description</span><span class="sxs-lookup"><span data-stu-id="b4e2b-113">Description</span></span>

<span data-ttu-id="b4e2b-114">Il `dotnet` comando ha due funzioni:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="b4e2b-115">Fornisce i comandi per l'uso dei progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="b4e2b-116">Ad esempio, [`dotnet build`](dotnet-build.md) Compila un progetto.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="b4e2b-117">Ogni comando definisce le proprie opzioni e gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="b4e2b-118">Tutti i comandi supportano l' `--help` opzione per stampare brevemente la documentazione su come usare il comando.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="b4e2b-119">Esegue le applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="b4e2b-120">Specificare il percorso di un `.dll` file di applicazione per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="b4e2b-121">Per eseguire l'applicazione significa trovare ed eseguire il punto di ingresso, che nel caso delle app console è il `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="b4e2b-122">Ad esempio, `dotnet myapp.dll` esegue l' `myapp` applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="b4e2b-123">Per informazioni sulle opzioni di distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md) .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="b4e2b-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b4e2b-124">Options</span></span>

<span data-ttu-id="b4e2b-125">Diverse opzioni sono disponibili per `dotnet` sé, per l'esecuzione di un comando e per l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="b4e2b-126">Opzioni per DotNet autonomamente</span><span class="sxs-lookup"><span data-stu-id="b4e2b-126">Options for dotnet by itself</span></span>

<span data-ttu-id="b4e2b-127">Le opzioni seguenti sono destinate a `dotnet` se stesso.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="b4e2b-128">Ad esempio, `dotnet --info`</span><span class="sxs-lookup"><span data-stu-id="b4e2b-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="b4e2b-129">Stampano le informazioni sull'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="b4e2b-130">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="b4e2b-131">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="b4e2b-132">Stampa un elenco di runtime di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="b4e2b-133">Una versione x86 dell'SDK elenca solo i Runtime x86 e una versione x64 dell'SDK elenca solo i runtime x64.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="b4e2b-134">Stampa un elenco degli SDK di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b4e2b-135">Stampa un elenco di comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="b4e2b-136">Opzioni SDK per l'esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="b4e2b-136">SDK options for running a command</span></span>

<span data-ttu-id="b4e2b-137">Le opzioni seguenti sono per `dotnet` con un comando.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="b4e2b-138">Ad esempio, `dotnet build --help`</span><span class="sxs-lookup"><span data-stu-id="b4e2b-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="b4e2b-139">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="b4e2b-140">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b4e2b-141">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b4e2b-142">Non supportato in ogni comando.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-142">Not supported in every command.</span></span> <span data-ttu-id="b4e2b-143">Vedere la pagina di comando specifica per determinare se questa opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b4e2b-144">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="b4e2b-145">Ogni comando definisce opzioni specifiche del comando.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="b4e2b-146">Per un elenco delle opzioni disponibili, vedere la pagina di comando specifica.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="b4e2b-147">Opzioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b4e2b-147">Runtime options</span></span>

<span data-ttu-id="b4e2b-148">Quando `dotnet` viene eseguita un'applicazione, sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="b4e2b-149">Ad esempio, `dotnet myapp.dll --roll-forward Major`</span><span class="sxs-lookup"><span data-stu-id="b4e2b-149">For example, `dotnet myapp.dll --roll-forward Major`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="b4e2b-150">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="b4e2b-151">Percorso di un file *.deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="b4e2b-152">Un file *Deps. JSON* contiene un elenco di dipendenze, dipendenze di compilazione e informazioni sulla versione utilizzate per risolvere i conflitti di assembly.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="b4e2b-153">Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--depsfile <PATH_TO_DEPSFILE>`**

  <span data-ttu-id="b4e2b-154">Percorso del file *Deps. JSON* .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-154">Path to the *deps.json* file.</span></span> <span data-ttu-id="b4e2b-155">Un file *Deps. JSON* è un file di configurazione che contiene informazioni sulle dipendenze necessarie per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-155">A *deps.json* file is a configuration file that contains information about dependencies necessary to run the application.</span></span> <span data-ttu-id="b4e2b-156">Questo file viene generato dal .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-156">This file is generated by the .NET Core SDK.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="b4e2b-157">Percorso di un file *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-157">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="b4e2b-158">Un file *runtimeconfig. JSON* è un file di configurazione che contiene le impostazioni della fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-158">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="b4e2b-159">Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-159">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="b4e2b-160">**`--roll-forward <SETTING>`\*\*\*\*Disponibile a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-160">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="b4e2b-161">Controlla il modo in cui viene applicato il rollforward all'app.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-161">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="b4e2b-162">`SETTING`Può essere uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-162">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="b4e2b-163">Se non è specificato, `Minor` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-163">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="b4e2b-164">`LatestPatch`-Eseguire il rollforward alla versione più recente della patch.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-164">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="b4e2b-165">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-165">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="b4e2b-166">`Minor`-Eseguire il rollforward alla versione secondaria più bassa, se manca la versione secondaria richiesta.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-166">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="b4e2b-167">Se la versione secondaria richiesta è presente, viene usato il criterio LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-167">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="b4e2b-168">`Major`: Eseguire il rollforward alla versione principale più bassa e la versione secondaria più bassa, se la versione principale richiesta è mancante.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-168">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="b4e2b-169">Se la versione principale richiesta è presente, viene usato il criterio Minor.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-169">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="b4e2b-170">`LatestMinor`-Rollforward alla versione secondaria più elevata, anche se è presente una versione secondaria richiesta.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-170">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="b4e2b-171">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-171">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="b4e2b-172">`LatestMajor`-Eseguire il rollforward alla versione principale più elevata e alla versione secondaria più elevata, anche se è presente la versione principale richiesta.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-172">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="b4e2b-173">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-173">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="b4e2b-174">`Disable`-Non eseguire il rollforward.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-174">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="b4e2b-175">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-175">Only bind to specified version.</span></span> <span data-ttu-id="b4e2b-176">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-176">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="b4e2b-177">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-177">This value is only recommended for testing.</span></span>

  <span data-ttu-id="b4e2b-178">Ad eccezione di `Disable` , tutte le impostazioni utilizzeranno la versione patch più recente disponibile.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-178">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

  <span data-ttu-id="b4e2b-179">Il comportamento di rollforward può essere configurato anche in una proprietà file di progetto, in una proprietà del file di configurazione in fase di esecuzione e in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-179">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="b4e2b-180">Per ulteriori informazioni, vedere il [rollforward del runtime della versione principale](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-180">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="b4e2b-181">**`--roll-forward-on-no-candidate-fx <N>`\*\*\*\*Disponibile in .NET Core 2. x SDK.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-181">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="b4e2b-182">Definisce il comportamento quando il framework condiviso richiesto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-182">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="b4e2b-183">`N` può essere:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-183">`N` can be:</span></span>

  - <span data-ttu-id="b4e2b-184">`0` - Disabilitare anche il roll forward per la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-184">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="b4e2b-185">`1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-185">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="b4e2b-186">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-186">This is the default behavior.</span></span>
  - <span data-ttu-id="b4e2b-187">`2` - Eseguire il roll forward per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-187">`2` - Roll forward on minor and major versions.</span></span>

  <span data-ttu-id="b4e2b-188">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-188">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="b4e2b-189">A partire da .NET Core 3,0, questa opzione è sostituita da `--roll-forward` ed è invece necessario usare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-189">Starting with .NET Core 3.0, this option is superseded by `--roll-forward`, and that option should be used instead.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="b4e2b-190">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-190">Version of the .NET Core runtime to use to run the application.</span></span>

  <span data-ttu-id="b4e2b-191">Questa opzione esegue l'override della versione del primo riferimento al Framework nel file dell'applicazione `.runtimeconfig.json` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-191">This option overrides the version of the first framework reference in the application's `.runtimeconfig.json` file.</span></span> <span data-ttu-id="b4e2b-192">Ciò significa che funziona solo come previsto se è presente solo un riferimento al Framework.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-192">This means it only works as expected if there's just one framework reference.</span></span> <span data-ttu-id="b4e2b-193">Se l'applicazione dispone di più di un riferimento a Framework, l'utilizzo di questa opzione può causare errori.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-193">If the application has more than one framework reference, using this option may cause errors.</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="b4e2b-194">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="b4e2b-194">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="b4e2b-195">Generale</span><span class="sxs-lookup"><span data-stu-id="b4e2b-195">General</span></span>

| <span data-ttu-id="b4e2b-196">Comando</span><span class="sxs-lookup"><span data-stu-id="b4e2b-196">Command</span></span>                                       | <span data-ttu-id="b4e2b-197">Funzione</span><span class="sxs-lookup"><span data-stu-id="b4e2b-197">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="b4e2b-198">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b4e2b-198">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="b4e2b-199">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-199">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="b4e2b-200">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="b4e2b-200">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="b4e2b-201">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-201">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="b4e2b-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b4e2b-202">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="b4e2b-203">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-203">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="b4e2b-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="b4e2b-204">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="b4e2b-205">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="b4e2b-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="b4e2b-206">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="b4e2b-207">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="b4e2b-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b4e2b-208">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="b4e2b-209">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="b4e2b-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b4e2b-210">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="b4e2b-211">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="b4e2b-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b4e2b-212">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="b4e2b-213">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="b4e2b-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b4e2b-214">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="b4e2b-215">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="b4e2b-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b4e2b-216">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="b4e2b-217">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="b4e2b-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b4e2b-218">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="b4e2b-219">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="b4e2b-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b4e2b-220">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="b4e2b-221">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="b4e2b-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="b4e2b-222">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="b4e2b-223">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="b4e2b-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b4e2b-224">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="b4e2b-225">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-225">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="b4e2b-226">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="b4e2b-226">Project references</span></span>

<span data-ttu-id="b4e2b-227">Comando</span><span class="sxs-lookup"><span data-stu-id="b4e2b-227">Command</span></span> | <span data-ttu-id="b4e2b-228">Funzione</span><span class="sxs-lookup"><span data-stu-id="b4e2b-228">Function</span></span>
--- | ---
[<span data-ttu-id="b4e2b-229">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="b4e2b-229">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="b4e2b-230">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-230">Adds a project reference.</span></span>
[<span data-ttu-id="b4e2b-231">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="b4e2b-231">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="b4e2b-232">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-232">Lists project references.</span></span>
[<span data-ttu-id="b4e2b-233">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="b4e2b-233">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="b4e2b-234">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-234">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="b4e2b-235">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="b4e2b-235">NuGet packages</span></span>

<span data-ttu-id="b4e2b-236">Comando</span><span class="sxs-lookup"><span data-stu-id="b4e2b-236">Command</span></span> | <span data-ttu-id="b4e2b-237">Funzione</span><span class="sxs-lookup"><span data-stu-id="b4e2b-237">Function</span></span>
--- | ---
[<span data-ttu-id="b4e2b-238">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="b4e2b-238">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="b4e2b-239">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-239">Adds a NuGet package.</span></span>
[<span data-ttu-id="b4e2b-240">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="b4e2b-240">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="b4e2b-241">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-241">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="b4e2b-242">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="b4e2b-242">NuGet commands</span></span>

<span data-ttu-id="b4e2b-243">Comando</span><span class="sxs-lookup"><span data-stu-id="b4e2b-243">Command</span></span> | <span data-ttu-id="b4e2b-244">Funzione</span><span class="sxs-lookup"><span data-stu-id="b4e2b-244">Function</span></span>
--- | ---
[<span data-ttu-id="b4e2b-245">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="b4e2b-245">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="b4e2b-246">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-246">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="b4e2b-247">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="b4e2b-247">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="b4e2b-248">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-248">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="b4e2b-249">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="b4e2b-249">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="b4e2b-250">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-250">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="b4e2b-251">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="b4e2b-251">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="b4e2b-252">Aggiunge un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-252">Adds a NuGet source.</span></span>
[<span data-ttu-id="b4e2b-253">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="b4e2b-253">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="b4e2b-254">Disabilita un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-254">Disables a NuGet source.</span></span>
[<span data-ttu-id="b4e2b-255">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="b4e2b-255">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="b4e2b-256">Abilita un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-256">Enables a NuGet source.</span></span>
[<span data-ttu-id="b4e2b-257">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="b4e2b-257">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="b4e2b-258">Elenca tutte le origini NuGet configurate.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-258">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="b4e2b-259">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="b4e2b-259">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="b4e2b-260">Rimuove un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-260">Removes a NuGet source.</span></span>
[<span data-ttu-id="b4e2b-261">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="b4e2b-261">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="b4e2b-262">Aggiorna un'origine NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-262">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="b4e2b-263">Comandi Global, Tool-Path e local Tools</span><span class="sxs-lookup"><span data-stu-id="b4e2b-263">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="b4e2b-264">Gli strumenti sono applicazioni console installate da pacchetti NuGet e vengono richiamate dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-264">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="b4e2b-265">È possibile scrivere strumenti manualmente oppure installare gli strumenti scritti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-265">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="b4e2b-266">Gli strumenti sono noti anche come strumenti globali, strumenti per percorsi di strumenti e strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-266">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="b4e2b-267">Per altre informazioni, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-267">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="b4e2b-268">Gli strumenti per percorsi globali e strumenti sono disponibili a partire da .NET Core SDK 2,1.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-268">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="b4e2b-269">Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-269">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="b4e2b-270">Comando</span><span class="sxs-lookup"><span data-stu-id="b4e2b-270">Command</span></span> | <span data-ttu-id="b4e2b-271">Funzione</span><span class="sxs-lookup"><span data-stu-id="b4e2b-271">Function</span></span>
--- | ---
[<span data-ttu-id="b4e2b-272">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="b4e2b-272">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="b4e2b-273">Installa uno strumento nel computer.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-273">Installs a tool on your machine.</span></span>
[<span data-ttu-id="b4e2b-274">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="b4e2b-274">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="b4e2b-275">Elenca tutti gli strumenti globali, di percorso degli strumenti o locali attualmente installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-275">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="b4e2b-276">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="b4e2b-276">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="b4e2b-277">Disinstalla uno strumento dal computer.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-277">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="b4e2b-278">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="b4e2b-278">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="b4e2b-279">Aggiorna uno strumento installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-279">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="b4e2b-280">Strumenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="b4e2b-280">Additional tools</span></span>

<span data-ttu-id="b4e2b-281">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-281">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="b4e2b-282">Tali strumenti sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-282">These tools are listed in the following table:</span></span>

| <span data-ttu-id="b4e2b-283">Strumento</span><span class="sxs-lookup"><span data-stu-id="b4e2b-283">Tool</span></span>                                              | <span data-ttu-id="b4e2b-284">Funzione</span><span class="sxs-lookup"><span data-stu-id="b4e2b-284">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="b4e2b-285">dev-certs</span><span class="sxs-lookup"><span data-stu-id="b4e2b-285">dev-certs</span></span>                                         | <span data-ttu-id="b4e2b-286">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-286">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="b4e2b-287">EF</span><span class="sxs-lookup"><span data-stu-id="b4e2b-287">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="b4e2b-288">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-288">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="b4e2b-289">sql-cache</span><span class="sxs-lookup"><span data-stu-id="b4e2b-289">sql-cache</span></span>                                         | <span data-ttu-id="b4e2b-290">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-290">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="b4e2b-291">user-secrets</span><span class="sxs-lookup"><span data-stu-id="b4e2b-291">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="b4e2b-292">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-292">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="b4e2b-293">guardare</span><span class="sxs-lookup"><span data-stu-id="b4e2b-293">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="b4e2b-294">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-294">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="b4e2b-295">Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-295">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="b4e2b-296">Esempi</span><span class="sxs-lookup"><span data-stu-id="b4e2b-296">Examples</span></span>

<span data-ttu-id="b4e2b-297">Creare una nuova applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-297">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="b4e2b-298">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-298">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="b4e2b-299">Eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="b4e2b-299">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="b4e2b-300">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="b4e2b-300">Environment variables</span></span>

- <span data-ttu-id="b4e2b-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="b4e2b-301">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="b4e2b-302">Specifica il percorso dei runtime di .NET Core, se non sono installati nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-302">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="b4e2b-303">Il percorso predefinito in Windows è `C:\Program Files\dotnet` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-303">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="b4e2b-304">Il percorso predefinito in Linux e macOS è `/usr/share/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-304">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="b4e2b-305">Questa variabile di ambiente viene utilizzata solo quando si eseguono app tramite file eseguibili generati (apphosts).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-305">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="b4e2b-306">`DOTNET_ROOT(x86)`viene invece usato quando si esegue un eseguibile a 32 bit in un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-306">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="b4e2b-307">La cartella dei pacchetti globali.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-307">The global packages folder.</span></span> <span data-ttu-id="b4e2b-308">Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-308">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="b4e2b-309">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-309">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="b4e2b-310">Specifica se i messaggi di benvenuto e di telemetria di .NET Core vengono visualizzati alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-310">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="b4e2b-311">Impostare su `true` per disattivare questi messaggi (valori `true` , `1` o `yes` accettati) o impostare su `false` Consenti (valori `false` , `0` o `no` accettati).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-311">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="b4e2b-312">Se non è impostato, il valore predefinito è `false` e i messaggi verranno visualizzati alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-312">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="b4e2b-313">Questo flag non ha alcun effetto sui dati di telemetria (vedere per rifiutare esplicitamente `DOTNET_CLI_TELEMETRY_OPTOUT` l'invio di dati di telemetria).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-313">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="b4e2b-314">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="b4e2b-315">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="b4e2b-316">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="b4e2b-317">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="b4e2b-318">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="b4e2b-319">Se non impostato, il valore predefinito è 1 (logico `true` ).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-319">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="b4e2b-320">Impostare su 0 (Logical `false` ) per non risolversi dal percorso globale e avere installazioni .NET Core isolate.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-320">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="b4e2b-321">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="b4e2b-322">`DOTNET_ROLL_FORWARD`**Disponibile a partire da .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-322">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="b4e2b-323">Determina il comportamento di rollforward.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-323">Determines roll forward behavior.</span></span> <span data-ttu-id="b4e2b-324">Per ulteriori informazioni, vedere l' `--roll-forward` opzione riportata in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-324">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="b4e2b-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE`**Disponibile a partire da .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-325">`DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="b4e2b-326">Se impostato su `1` (abilitato), consente di eseguire il rollforward di una versione non definitiva da una versione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-326">If set to `1` (enabled), enables rolling forward to a pre-release version from a release version.</span></span> <span data-ttu-id="b4e2b-327">Per impostazione predefinita ( `0` -disabilitato), quando viene richiesta una versione di rilascio del runtime di .NET Core, il rollforward prende in considerazione solo le versioni di rilascio installate.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-327">By default (`0` - disabled), when a release version of .NET Core runtime is requested, roll-forward will only consider installed release versions.</span></span>

  <span data-ttu-id="b4e2b-328">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-328">For more information, see [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

- <span data-ttu-id="b4e2b-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`**Disponibile in .NET Core 2. x.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-329">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x.**</span></span>

  <span data-ttu-id="b4e2b-330">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-330">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="b4e2b-331">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-331">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

  <span data-ttu-id="b4e2b-332">Questa impostazione viene sostituita in .NET Core 3,0 da `DOTNET_ROLL_FORWARD` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-332">This setting is superseded in .NET Core 3.0 by `DOTNET_ROLL_FORWARD`.</span></span> <span data-ttu-id="b4e2b-333">In alternativa, è consigliabile usare le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-333">The new settings should be used instead.</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="b4e2b-334">Imposta la lingua dell'interfaccia utente CLI usando un valore delle impostazioni locali, ad esempio `en-us` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-334">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="b4e2b-335">I valori supportati sono identici a quelli di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-335">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="b4e2b-336">Per ulteriori informazioni, vedere la sezione relativa alla modifica della lingua del programma di installazione nella [documentazione sull'installazione di Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-336">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="b4e2b-337">Si applicano le regole di .NET Resource Manager, pertanto non è necessario scegliere una corrispondenza esatta &mdash; . è anche possibile selezionare i discendenti nell' `CultureInfo` albero.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-337">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="b4e2b-338">Se, ad esempio, si imposta su `fr-CA` , l'interfaccia della riga di comando troverà e utilizzerà le `fr` traduzioni.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-338">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="b4e2b-339">Se lo si imposta su una lingua non supportata, l'interfaccia della riga di comando esegue il fallback all'inglese.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-339">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="b4e2b-340">Per gli eseguibili generati da GUI, Disabilita il popup della finestra di dialogo, che in genere viene visualizzato per determinate classi di errori.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-340">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="b4e2b-341">In questi casi, scrive solo in `stderr` e chiude.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-341">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="b4e2b-342">Equivale all'opzione CLI `--additional-deps` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-342">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="b4e2b-343">Esegue l'override del RID rilevato.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-343">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="b4e2b-344">Percorso dell'archivio condiviso in cui viene eseguito il fallback della risoluzione degli assembly in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-344">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="b4e2b-345">Elenco di assembly da cui caricare ed eseguire hook di avvio.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-345">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="b4e2b-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR`**Disponibile a partire da .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-346">`DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Available starting with .NET Core 3.x.**</span></span>

  <span data-ttu-id="b4e2b-347">Specifica una directory in cui viene estratta un'applicazione a file singolo prima che venga eseguita.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-347">Specifies a directory to which a single-file application is extracted before it is executed.</span></span>

  <span data-ttu-id="b4e2b-348">Per ulteriori informazioni, vedere [file eseguibili con singolo file](../whats-new/dotnet-core-3-0.md#single-file-executables).</span><span class="sxs-lookup"><span data-stu-id="b4e2b-348">For more information, see [Single-file executables](../whats-new/dotnet-core-3-0.md#single-file-executables).</span></span>

- <span data-ttu-id="b4e2b-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="b4e2b-349">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="b4e2b-350">Controlla la traccia di diagnostica dai componenti di hosting, ad esempio `dotnet.exe` , `hostfxr` e `hostpolicy` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-350">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

  * <span data-ttu-id="b4e2b-351">`COREHOST_TRACE=[0/1]`-la traccia predefinita è `0` disabilitata.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-351">`COREHOST_TRACE=[0/1]` - default is `0` - tracing disabled.</span></span> <span data-ttu-id="b4e2b-352">Se impostato su `1` , la traccia di diagnostica è abilitata.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-352">If set to `1`, diagnostics tracing is enabled.</span></span>
  * <span data-ttu-id="b4e2b-353">`COREHOST_TRACEFILE=<file path>`-ha effetto solo se la traccia è abilitata tramite `COREHOST_TRACE=1` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-353">`COREHOST_TRACEFILE=<file path>` - only has effect if tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="b4e2b-354">Se impostato, le informazioni di traccia vengono scritte nel file specificato, in caso contrario le informazioni di traccia vengono scritte in `stderr` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-354">When set, the tracing information is written to the specified file, otherwise the tracing information is written to `stderr`.</span></span> <span data-ttu-id="b4e2b-355">**Disponibile a partire da .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-355">**Available starting with .NET Core 3.x.**</span></span>
  * <span data-ttu-id="b4e2b-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]`-il valore predefinito è `4` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-356">`COREHOST_TRACE_VERBOSITY=[1/2/3/4]` - default is `4`.</span></span> <span data-ttu-id="b4e2b-357">L'impostazione viene utilizzata solo quando la traccia è abilitata tramite `COREHOST_TRACE=1` .</span><span class="sxs-lookup"><span data-stu-id="b4e2b-357">The setting is used only when tracing is enabled via `COREHOST_TRACE=1`.</span></span> <span data-ttu-id="b4e2b-358">**Disponibile a partire da .NET Core 3. x.**</span><span class="sxs-lookup"><span data-stu-id="b4e2b-358">**Available starting with .NET Core 3.x.**</span></span>
    * <span data-ttu-id="b4e2b-359">`4`-tutte le informazioni di traccia vengono scritte</span><span class="sxs-lookup"><span data-stu-id="b4e2b-359">`4` - all tracing information is written</span></span>
    * <span data-ttu-id="b4e2b-360">`3`-vengono scritti solo messaggi informativi, di avviso e di errore</span><span class="sxs-lookup"><span data-stu-id="b4e2b-360">`3` - only informational, warning and error messages are written</span></span>
    * <span data-ttu-id="b4e2b-361">`2`-vengono scritti solo i messaggi di avviso e di errore</span><span class="sxs-lookup"><span data-stu-id="b4e2b-361">`2` - only warning and error messages are written</span></span>
    * <span data-ttu-id="b4e2b-362">`1`-vengono scritti solo i messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="b4e2b-362">`1` - only error messages are written</span></span>

  <span data-ttu-id="b4e2b-363">Il modo più comune per ottenere informazioni dettagliate sulla traccia dell'avvio dell'applicazione consiste nell'impostare `COREHOST_TRACE=1` e `COREHOST_TRACEFILE=host_trace.txt` quindi eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-363">The typical way to get detailed trace information about application startup is to set `COREHOST_TRACE=1` and `COREHOST_TRACEFILE=host_trace.txt` and then run the application.</span></span> <span data-ttu-id="b4e2b-364">Verrà creato un nuovo file `host_trace.txt` nella directory corrente con le informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="b4e2b-364">A new file `host_trace.txt` will be created in the current directory with the detailed information.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4e2b-365">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4e2b-365">See also</span></span>

- <span data-ttu-id="b4e2b-366">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)</span><span class="sxs-lookup"><span data-stu-id="b4e2b-366">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)</span></span>
- [<span data-ttu-id="b4e2b-367">Impostazioni di configurazione della fase di esecuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="b4e2b-367">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
