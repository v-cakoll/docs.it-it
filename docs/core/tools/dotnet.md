---
title: Comando dotnet
description: Informazioni sul comando DotNet (il driver generico per la interfaccia della riga di comando di .NET Core) e il relativo utilizzo.
ms.date: 02/13/2020
ms.openlocfilehash: da37c5cc3b019851e245fa3f65ae9dfb8a3fef54
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240870"
---
# <a name="dotnet-command"></a><span data-ttu-id="fe4f8-103">Comando dotnet</span><span class="sxs-lookup"><span data-stu-id="fe4f8-103">dotnet command</span></span>

<span data-ttu-id="fe4f8-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="fe4f8-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fe4f8-105">Nome</span><span class="sxs-lookup"><span data-stu-id="fe4f8-105">Name</span></span>

<span data-ttu-id="fe4f8-106">`dotnet`: il driver generico per l'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fe4f8-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fe4f8-107">Synopsis</span></span>

<span data-ttu-id="fe4f8-108">Per ottenere informazioni sui comandi disponibili e sull'ambiente:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

<span data-ttu-id="fe4f8-109">Per eseguire un comando (richiede l'installazione dell'SDK):</span><span class="sxs-lookup"><span data-stu-id="fe4f8-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

<span data-ttu-id="fe4f8-110">Per eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="fe4f8-111">`--roll-forward` è disponibile a partire da .NET Core 3. x.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="fe4f8-112">Usare `--roll-forward-on-no-candidate-fx` per .NET Core 2. x.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="fe4f8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe4f8-113">Description</span></span>

<span data-ttu-id="fe4f8-114">Il comando `dotnet` dispone di due funzioni:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="fe4f8-115">Fornisce i comandi per l'uso dei progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="fe4f8-116">Ad esempio, [`dotnet build`](dotnet-build.md) compila un progetto.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="fe4f8-117">Ogni comando definisce le proprie opzioni e gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="fe4f8-118">Tutti i comandi supportano l'opzione `--help` per stampare brevemente la documentazione sull'uso del comando.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="fe4f8-119">Esegue le applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="fe4f8-120">Per eseguire l'applicazione, è necessario specificare il percorso di un'applicazione `.dll` file.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-120">You specify the path to an application `.dll` file to run the application.</span></span> <span data-ttu-id="fe4f8-121">Ad esempio, `dotnet myapp.dll` esegue l'applicazione `myapp`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-121">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="fe4f8-122">Per informazioni sulle opzioni di distribuzione, vedere [distribuzione di applicazioni .NET Core](../deploying/index.md) .</span><span class="sxs-lookup"><span data-stu-id="fe4f8-122">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="fe4f8-123">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fe4f8-123">Options</span></span>

<span data-ttu-id="fe4f8-124">Sono disponibili diverse opzioni per `dotnet` da solo, per l'esecuzione di un comando e per l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-124">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="fe4f8-125">Opzioni per DotNet autonomamente</span><span class="sxs-lookup"><span data-stu-id="fe4f8-125">Options for dotnet by itself</span></span>

<span data-ttu-id="fe4f8-126">Di seguito sono riportate le opzioni per `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-126">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="fe4f8-127">Ad esempio: `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-127">For example, `dotnet --info`.</span></span> <span data-ttu-id="fe4f8-128">Stampano le informazioni sull'ambiente.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-128">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="fe4f8-129">Consente di visualizzare informazioni dettagliate sull'installazione di .NET Core e sull'ambiente del computer, come ad esempio il sistema operativo corrente e l'Agente integrità sistema di commit della versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-129">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="fe4f8-130">Stampa la versione di .NET Core SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-130">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="fe4f8-131">Stampa un elenco di runtime di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-131">Prints out a list of the installed .NET Core runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="fe4f8-132">Stampa un elenco degli SDK di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-132">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="fe4f8-133">Stampa un elenco di comandi disponibili.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-133">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="fe4f8-134">Opzioni SDK per l'esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="fe4f8-134">SDK options for running a command</span></span>

<span data-ttu-id="fe4f8-135">Di seguito sono riportate le opzioni per `dotnet` con un comando.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-135">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="fe4f8-136">Ad esempio: `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-136">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="fe4f8-137">Abilita l'output di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-137">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="fe4f8-138">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fe4f8-139">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fe4f8-140">Non supportato in ogni comando.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-140">Not supported in every command.</span></span> <span data-ttu-id="fe4f8-141">Vedere la pagina di comando specifica per determinare se questa opzione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-141">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="fe4f8-142">Visualizza la documentazione per un determinato comando, come ad esempio `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-142">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="fe4f8-143">Ogni comando definisce opzioni specifiche del comando.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-143">Each command defines options specific to that command.</span></span> <span data-ttu-id="fe4f8-144">Per un elenco delle opzioni disponibili, vedere la pagina di comando specifica.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-144">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="fe4f8-145">Opzioni di runtime</span><span class="sxs-lookup"><span data-stu-id="fe4f8-145">Runtime options</span></span>

<span data-ttu-id="fe4f8-146">Quando `dotnet` esegue un'applicazione, sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-146">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="fe4f8-147">Ad esempio: `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-147">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="fe4f8-148">Percorso contenente i criteri di probe e gli assembly di cui eseguire il probe.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-148">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="fe4f8-149">Percorso di un file *.deps.json* aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-149">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="fe4f8-150">Un file *Deps. JSON* contiene un elenco di dipendenze, dipendenze di compilazione e informazioni sulla versione utilizzate per risolvere i conflitti di assembly.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-150">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="fe4f8-151">Per altre informazioni, vedere [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-151">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="fe4f8-152">Versione del runtime di .NET Core da usare per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-152">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="fe4f8-153">Percorso di un file *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-153">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="fe4f8-154">Un file *runtimeconfig. JSON* è un file di configurazione che contiene le impostazioni della fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-154">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="fe4f8-155">Per altre informazioni, vedere Impostazioni di configurazione della fase di [esecuzione di .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-155">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="fe4f8-156">**`--roll-forward-on-no-candidate-fx <N>`** **disponibile in .NET Core 2. x SDK.**</span><span class="sxs-lookup"><span data-stu-id="fe4f8-156">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="fe4f8-157">Definisce il comportamento quando il framework condiviso richiesto non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-157">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="fe4f8-158">`N` può essere:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-158">`N` can be:</span></span>

  - <span data-ttu-id="fe4f8-159">`0` - Disabilitare anche il roll forward per la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-159">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="fe4f8-160">`1` - Eseguire il roll forward per la versione secondaria, ma non la versione principale.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-160">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="fe4f8-161">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-161">This is the default behavior.</span></span>
  - <span data-ttu-id="fe4f8-162">`2` - Eseguire il roll forward per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-162">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="fe4f8-163">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-163">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="fe4f8-164">**`--roll-forward <SETTING>`** **disponibile a partire da .NET Core SDK 3,0.**</span><span class="sxs-lookup"><span data-stu-id="fe4f8-164">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="fe4f8-165">Controlla il modo in cui viene applicato il rollforward all'app.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-165">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="fe4f8-166">Il `SETTING` può essere uno dei valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-166">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="fe4f8-167">Se non è specificato, il valore predefinito è `Minor`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-167">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="fe4f8-168">`LatestPatch`: eseguire il rollforward alla versione più recente della patch.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-168">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="fe4f8-169">Disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-169">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="fe4f8-170">`Minor` eseguire il rollforward alla versione secondaria più bassa, se manca la versione secondaria richiesta.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-170">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="fe4f8-171">Se è presente la versione secondaria richiesta, viene usato il criterio LatestPatch.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-171">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="fe4f8-172">`Major`: eseguire il rollforward alla versione principale più bassa e la versione secondaria più bassa, se la versione principale richiesta è mancante.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-172">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="fe4f8-173">Se è presente la versione principale richiesta, viene usato il criterio secondario.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-173">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="fe4f8-174">`LatestMinor` il rollforward alla versione secondaria più elevata, anche se è presente una versione secondaria richiesta.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-174">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="fe4f8-175">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-175">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="fe4f8-176">`LatestMajor`: eseguire il rollforward alla versione principale e più alta più elevata, anche se è presente la versione principale richiesta.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-176">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="fe4f8-177">È destinata a scenari di hosting dei componenti.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="fe4f8-178">`Disable` non eseguire il rollforward.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-178">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="fe4f8-179">Esegue solo un'associazione alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-179">Only bind to specified version.</span></span> <span data-ttu-id="fe4f8-180">Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-180">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="fe4f8-181">Questo valore è consigliato solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-181">This value is only recommended for testing.</span></span>

<span data-ttu-id="fe4f8-182">Ad eccezione di `Disable`, tutte le impostazioni utilizzeranno la versione patch più recente disponibile.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-182">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="fe4f8-183">Il comportamento di rollforward può essere configurato anche in una proprietà file di progetto, in una proprietà del file di configurazione in fase di esecuzione e in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-183">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="fe4f8-184">Per ulteriori informazioni, vedere il [rollforward del runtime della versione principale](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-184">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="fe4f8-185">Comandi dotnet</span><span class="sxs-lookup"><span data-stu-id="fe4f8-185">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="fe4f8-186">Generale</span><span class="sxs-lookup"><span data-stu-id="fe4f8-186">General</span></span>

| <span data-ttu-id="fe4f8-187">Comando</span><span class="sxs-lookup"><span data-stu-id="fe4f8-187">Command</span></span>                                       | <span data-ttu-id="fe4f8-188">Funzione</span><span class="sxs-lookup"><span data-stu-id="fe4f8-188">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="fe4f8-189">dotnet build</span><span class="sxs-lookup"><span data-stu-id="fe4f8-189">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="fe4f8-190">Compila un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-190">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="fe4f8-191">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="fe4f8-191">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="fe4f8-192">Interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-192">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="fe4f8-193">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="fe4f8-193">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="fe4f8-194">Pulisce gli output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-194">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="fe4f8-195">dotnet help</span><span class="sxs-lookup"><span data-stu-id="fe4f8-195">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="fe4f8-196">Visualizza documentazione online dettagliata per il comando.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-196">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="fe4f8-197">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="fe4f8-197">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="fe4f8-198">Esegue la migrazione di un progetto Preview 2 in un progetto .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-198">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="fe4f8-199">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="fe4f8-199">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="fe4f8-200">Consente di accedere alla riga di comando di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-200">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="fe4f8-201">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fe4f8-201">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="fe4f8-202">Inizializza un progetto C# o F# per un modello specificato.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-202">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="fe4f8-203">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fe4f8-203">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="fe4f8-204">Crea un pacchetto NuGet del codice.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-204">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="fe4f8-205">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="fe4f8-205">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="fe4f8-206">Pubblica un'applicazione .NET dipendente dal framework o autonoma.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-206">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="fe4f8-207">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fe4f8-207">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="fe4f8-208">Ripristina le dipendenze per una determinata applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-208">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="fe4f8-209">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fe4f8-209">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="fe4f8-210">Esegue l'applicazione dall'origine.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-210">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="fe4f8-211">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="fe4f8-211">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="fe4f8-212">Opzioni per aggiungere, rimuovere ed elencare i progetti in un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-212">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="fe4f8-213">dotnet store</span><span class="sxs-lookup"><span data-stu-id="fe4f8-213">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="fe4f8-214">Archivia gli assembly nell'archivio pacchetti di runtime.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-214">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="fe4f8-215">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fe4f8-215">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="fe4f8-216">Esegue test usando un Test Runner.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-216">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="fe4f8-217">Riferimenti al progetto</span><span class="sxs-lookup"><span data-stu-id="fe4f8-217">Project references</span></span>

<span data-ttu-id="fe4f8-218">Comando</span><span class="sxs-lookup"><span data-stu-id="fe4f8-218">Command</span></span> | <span data-ttu-id="fe4f8-219">Funzione</span><span class="sxs-lookup"><span data-stu-id="fe4f8-219">Function</span></span>
--- | ---
[<span data-ttu-id="fe4f8-220">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="fe4f8-220">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="fe4f8-221">Aggiunge un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-221">Adds a project reference.</span></span>
[<span data-ttu-id="fe4f8-222">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="fe4f8-222">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="fe4f8-223">Elenca i riferimenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-223">Lists project references.</span></span>
[<span data-ttu-id="fe4f8-224">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="fe4f8-224">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="fe4f8-225">Rimuove un riferimento dal progetto.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-225">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="fe4f8-226">Pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="fe4f8-226">NuGet packages</span></span>

<span data-ttu-id="fe4f8-227">Comando</span><span class="sxs-lookup"><span data-stu-id="fe4f8-227">Command</span></span> | <span data-ttu-id="fe4f8-228">Funzione</span><span class="sxs-lookup"><span data-stu-id="fe4f8-228">Function</span></span>
--- | ---
[<span data-ttu-id="fe4f8-229">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="fe4f8-229">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="fe4f8-230">Aggiunge un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-230">Adds a NuGet package.</span></span>
[<span data-ttu-id="fe4f8-231">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="fe4f8-231">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="fe4f8-232">Rimuove un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-232">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="fe4f8-233">Comandi NuGet</span><span class="sxs-lookup"><span data-stu-id="fe4f8-233">NuGet commands</span></span>

<span data-ttu-id="fe4f8-234">Comando</span><span class="sxs-lookup"><span data-stu-id="fe4f8-234">Command</span></span> | <span data-ttu-id="fe4f8-235">Funzione</span><span class="sxs-lookup"><span data-stu-id="fe4f8-235">Function</span></span>
--- | ---
[<span data-ttu-id="fe4f8-236">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="fe4f8-236">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="fe4f8-237">Rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-237">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="fe4f8-238">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="fe4f8-238">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="fe4f8-239">Cancella o elenca risorse NuGet locali come cache delle richieste HTTP, cache temporanea o cartella globale dei pacchetti a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-239">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="fe4f8-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="fe4f8-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="fe4f8-241">Effettua il push di un pacchetto nel server e lo pubblica.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-241">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="fe4f8-242">Comandi Global, Tool-Path e local Tools</span><span class="sxs-lookup"><span data-stu-id="fe4f8-242">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="fe4f8-243">Gli strumenti sono applicazioni console installate da pacchetti NuGet e vengono richiamate dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-243">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="fe4f8-244">È possibile scrivere strumenti manualmente oppure installare gli strumenti scritti da terze parti.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-244">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="fe4f8-245">Gli strumenti sono noti anche come strumenti globali, strumenti per percorsi di strumenti e strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-245">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="fe4f8-246">Per altre informazioni, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-246">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="fe4f8-247">Gli strumenti per percorsi globali e strumenti sono disponibili a partire da .NET Core SDK 2,1.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-247">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="fe4f8-248">Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-248">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="fe4f8-249">Comando</span><span class="sxs-lookup"><span data-stu-id="fe4f8-249">Command</span></span> | <span data-ttu-id="fe4f8-250">Funzione</span><span class="sxs-lookup"><span data-stu-id="fe4f8-250">Function</span></span>
--- | ---
[<span data-ttu-id="fe4f8-251">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="fe4f8-251">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="fe4f8-252">Installa uno strumento nel computer.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-252">Installs a tool on your machine.</span></span>
[<span data-ttu-id="fe4f8-253">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="fe4f8-253">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="fe4f8-254">Elenca tutti gli strumenti globali, di percorso degli strumenti o locali attualmente installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-254">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="fe4f8-255">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="fe4f8-255">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="fe4f8-256">Disinstalla uno strumento dal computer.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-256">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="fe4f8-257">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="fe4f8-257">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="fe4f8-258">Aggiorna uno strumento installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-258">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="fe4f8-259">Strumenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="fe4f8-259">Additional tools</span></span>

<span data-ttu-id="fe4f8-260">A partire da .NET Core SDK 2.1.300, numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-260">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="fe4f8-261">Tali strumenti sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-261">These tools are listed in the following table:</span></span>

| <span data-ttu-id="fe4f8-262">Strumento</span><span class="sxs-lookup"><span data-stu-id="fe4f8-262">Tool</span></span>                                              | <span data-ttu-id="fe4f8-263">Funzione</span><span class="sxs-lookup"><span data-stu-id="fe4f8-263">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="fe4f8-264">dev-certs</span><span class="sxs-lookup"><span data-stu-id="fe4f8-264">dev-certs</span></span>                                         | <span data-ttu-id="fe4f8-265">Crea e gestisce i certificati di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-265">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="fe4f8-266">ef</span><span class="sxs-lookup"><span data-stu-id="fe4f8-266">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="fe4f8-267">Strumenti da riga di comando di Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-267">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="fe4f8-268">sql-cache</span><span class="sxs-lookup"><span data-stu-id="fe4f8-268">sql-cache</span></span>                                         | <span data-ttu-id="fe4f8-269">Strumenti da riga di comando della cache di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-269">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="fe4f8-270">user-secrets</span><span class="sxs-lookup"><span data-stu-id="fe4f8-270">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="fe4f8-271">Gestisce i segreti dell'utente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-271">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="fe4f8-272">watch</span><span class="sxs-lookup"><span data-stu-id="fe4f8-272">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="fe4f8-273">Avvia un watcher per file che esegue un comando quando si modificano i file.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-273">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="fe4f8-274">Per altre informazioni su ogni strumento, digitare `dotnet <tool-name> --help`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-274">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="fe4f8-275">Esempi</span><span class="sxs-lookup"><span data-stu-id="fe4f8-275">Examples</span></span>

<span data-ttu-id="fe4f8-276">Creare una nuova applicazione console .NET Core:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-276">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="fe4f8-277">Compilare un progetto e le relative dipendenze in una determinata directory:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-277">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="fe4f8-278">Eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="fe4f8-278">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="fe4f8-279">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="fe4f8-279">Environment variables</span></span>

- <span data-ttu-id="fe4f8-280">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="fe4f8-280">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="fe4f8-281">Specifica il percorso dei runtime di .NET Core, se non sono installati nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-281">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="fe4f8-282">Il percorso predefinito in Windows è `C:\Program Files\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-282">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="fe4f8-283">Il percorso predefinito in Linux e macOS è `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-283">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="fe4f8-284">Questa variabile di ambiente viene utilizzata solo quando si eseguono app tramite file eseguibili generati (apphosts).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-284">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="fe4f8-285">`DOTNET_ROOT(x86)` viene invece utilizzato quando si esegue un eseguibile a 32 bit in un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-285">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="fe4f8-286">La cartella dei pacchetti globali.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-286">The global packages folder.</span></span> <span data-ttu-id="fe4f8-287">Se non è impostata, il percorso predefinito è `~/.nuget/packages` in Unix o `%userprofile%\.nuget\packages` in Windows.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-287">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="fe4f8-288">Specifica il percorso dell'indice di manutenzione che l'host condiviso deve usare durante il caricamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-288">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="fe4f8-289">Specifica se i dati relativi all'utilizzo degli strumenti .NET Core vengono raccolti e inviati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-289">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="fe4f8-290">Impostare su `true` per rifiutare esplicitamente la funzionalità di telemetria (i valori accettati sono `true`, `1` o `yes`).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-290">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="fe4f8-291">In caso contrario, impostare su `false` per acconsentire esplicitamente alle funzionalità di telemetria (i valori accettati sono `false`, `0` o `no`).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-291">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="fe4f8-292">Se non è impostata, il valore predefinito è `false` e quindi la funzionalità di telemetria è attiva.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-292">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="fe4f8-293">Specifica se il runtime .NET Core, il framework condiviso o l'SDK vengono risolti dal percorso globale.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-293">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="fe4f8-294">Se non impostato, il valore predefinito è 1 (`true`logico).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-294">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="fe4f8-295">Impostare su 0 (`false`logico) per non risolvere il percorso globale e avere installazioni .NET Core isolate.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-295">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="fe4f8-296">Per altre informazioni sulla ricerca multilivello, vedere [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Ricerca SharedFX multilivello).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-296">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="fe4f8-297">`DOTNET_ROLL_FORWARD` **disponibile a partire da .NET Core 3. x SDK.**</span><span class="sxs-lookup"><span data-stu-id="fe4f8-297">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="fe4f8-298">Determina il comportamento di rollforward.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-298">Determines roll forward behavior.</span></span> <span data-ttu-id="fe4f8-299">Per ulteriori informazioni, vedere l'opzione `--roll-forward` più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-299">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="fe4f8-300">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **disponibile in .NET Core 2. x SDK.**</span><span class="sxs-lookup"><span data-stu-id="fe4f8-300">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="fe4f8-301">Se impostato su `0`, disabilita il roll forward della versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-301">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="fe4f8-302">Per altre informazioni, vedere [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-302">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="fe4f8-303">Imposta la lingua dell'interfaccia utente CLI usando un valore delle impostazioni locali, ad esempio `en-us`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-303">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="fe4f8-304">I valori supportati sono identici a quelli di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-304">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="fe4f8-305">Per ulteriori informazioni, vedere la sezione relativa alla modifica della lingua del programma di installazione nella [documentazione sull'installazione di Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="fe4f8-305">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="fe4f8-306">Si applicano le regole di .NET Resource Manager, pertanto non è necessario scegliere una corrispondenza esatta&mdash;è anche possibile selezionare i discendenti nell'albero di `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-306">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="fe4f8-307">Se ad esempio lo si imposta su `fr-CA`, l'interfaccia della riga di comando troverà e utilizzerà le traduzioni di `fr`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-307">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="fe4f8-308">Se lo si imposta su una lingua non supportata, l'interfaccia della riga di comando esegue il fallback all'inglese.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-308">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="fe4f8-309">Per gli eseguibili generati da GUI, Disabilita il popup della finestra di dialogo che in genere viene visualizzato per determinate classi di errori.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-309">For GUI-enabled generated executables - disables dialog popup which normally shows for certain classes of errors.</span></span> <span data-ttu-id="fe4f8-310">Scrive solo in `stderr` e si chiude in questi casi.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-310">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="fe4f8-311">Equivalente all'opzione CLI `--additional-deps`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-311">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="fe4f8-312">Esegue l'override del RID rilevato.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-312">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="fe4f8-313">Percorso dell'archivio condiviso in cui viene eseguito il fallback della risoluzione degli assembly in alcuni casi.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-313">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="fe4f8-314">Elenco di assembly da cui caricare ed eseguire hook di avvio.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-314">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="fe4f8-315">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="fe4f8-315">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="fe4f8-316">Controlla la traccia di diagnostica dai componenti host, ad esempio `dotnet.exe`, `hostfxr`e `hostpolicy`.</span><span class="sxs-lookup"><span data-stu-id="fe4f8-316">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe4f8-317">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe4f8-317">See also</span></span>

- <span data-ttu-id="fe4f8-318">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) (File di configurazione di runtime)</span><span class="sxs-lookup"><span data-stu-id="fe4f8-318">[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)</span></span>
- [<span data-ttu-id="fe4f8-319">Impostazioni di configurazione della fase di esecuzione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="fe4f8-319">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
