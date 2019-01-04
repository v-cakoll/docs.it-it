---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 05/29/2018
ms.openlocfilehash: 2cfe96b24e5f46ae679c970a1df028d38ebf6037
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170848"
---
# <a name="dotnet-test"></a><span data-ttu-id="c9269-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c9269-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c9269-104">nome</span><span class="sxs-lookup"><span data-stu-id="c9269-104">Name</span></span>

<span data-ttu-id="c9269-105">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="c9269-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c9269-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c9269-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c9269-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c9269-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c9269-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c9269-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c9269-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c9269-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="c9269-110">Description</span><span class="sxs-lookup"><span data-stu-id="c9269-110">Description</span></span>

<span data-ttu-id="c9269-111">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="c9269-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="c9269-112">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="c9269-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="c9269-113">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="c9269-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="c9269-114">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="c9269-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="c9269-115">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="c9269-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="c9269-116">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c9269-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="c9269-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c9269-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c9269-118">Percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="c9269-118">Path to the test project.</span></span> <span data-ttu-id="c9269-119">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c9269-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="c9269-120">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c9269-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c9269-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c9269-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="c9269-122">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="c9269-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="c9269-123">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="c9269-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="c9269-124">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="c9269-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="c9269-125">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="c9269-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c9269-126">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c9269-126">Defines the build configuration.</span></span> <span data-ttu-id="c9269-127">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="c9269-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="c9269-128">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="c9269-128">Enables data collector for the test run.</span></span> <span data-ttu-id="c9269-129">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="c9269-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="c9269-130">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="c9269-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c9269-131">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="c9269-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c9269-132">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="c9269-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="c9269-133">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="c9269-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="c9269-134">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c9269-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="c9269-135">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="c9269-136">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="c9269-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="c9269-137">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9269-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="c9269-138">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="c9269-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="c9269-139">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c9269-140">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="c9269-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="c9269-141">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="c9269-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="c9269-142">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="c9269-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="c9269-143">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="c9269-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="c9269-144">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="c9269-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c9269-145">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c9269-146">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c9269-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="c9269-147">Argomenti passati come configurazioni RunSettings per il test.</span><span class="sxs-lookup"><span data-stu-id="c9269-147">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="c9269-148">Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --.</span><span class="sxs-lookup"><span data-stu-id="c9269-148">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="c9269-149">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="c9269-149">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="c9269-150">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="c9269-150">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="c9269-151">Per altre informazioni su RunSettings, vedere [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: passare argomenti RunSettings).</span><span class="sxs-lookup"><span data-stu-id="c9269-151">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c9269-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c9269-152">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="c9269-153">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="c9269-153">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c9269-154">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c9269-154">Defines the build configuration.</span></span> <span data-ttu-id="c9269-155">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="c9269-155">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="c9269-156">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="c9269-156">Enables data collector for the test run.</span></span> <span data-ttu-id="c9269-157">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="c9269-157">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="c9269-158">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="c9269-158">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c9269-159">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="c9269-159">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c9269-160">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="c9269-160">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="c9269-161">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="c9269-161">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="c9269-162">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c9269-162">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="c9269-163">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-163">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="c9269-164">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="c9269-164">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="c9269-165">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9269-165">Doesn't build the test project before running it.</span></span> <span data-ttu-id="c9269-166">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="c9269-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="c9269-167">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-167">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c9269-168">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="c9269-168">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="c9269-169">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="c9269-169">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="c9269-170">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="c9269-170">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="c9269-171">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="c9269-171">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="c9269-172">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="c9269-172">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c9269-173">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-173">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c9269-174">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c9269-174">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c9269-175">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c9269-175">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="c9269-176">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="c9269-176">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="c9269-177">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c9269-177">Defines the build configuration.</span></span> <span data-ttu-id="c9269-178">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="c9269-178">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="c9269-179">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="c9269-179">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="c9269-180">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="c9269-180">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c9269-181">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="c9269-181">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="c9269-182">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="c9269-182">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="c9269-183">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c9269-183">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="c9269-184">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-184">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="c9269-185">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="c9269-185">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="c9269-186">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9269-186">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c9269-187">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="c9269-187">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="c9269-188">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="c9269-188">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="c9269-189">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="c9269-189">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="c9269-190">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="c9269-190">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c9269-191">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c9269-191">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c9269-192">Esempi</span><span class="sxs-lookup"><span data-stu-id="c9269-192">Examples</span></span>

<span data-ttu-id="c9269-193">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="c9269-193">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="c9269-194">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="c9269-194">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="c9269-195">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati di test in formato trx:</span><span class="sxs-lookup"><span data-stu-id="c9269-195">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="c9269-196">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="c9269-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="c9269-197">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="c9269-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="c9269-198">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="c9269-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="c9269-199">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="c9269-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="c9269-200">Framework di test</span><span class="sxs-lookup"><span data-stu-id="c9269-200">Test Framework</span></span> | <span data-ttu-id="c9269-201">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="c9269-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c9269-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="c9269-202">MSTest</span></span>         | <ul><li><span data-ttu-id="c9269-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c9269-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="c9269-204">nome</span><span class="sxs-lookup"><span data-stu-id="c9269-204">Name</span></span></li><li><span data-ttu-id="c9269-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="c9269-205">ClassName</span></span></li><li><span data-ttu-id="c9269-206">Priorità</span><span class="sxs-lookup"><span data-stu-id="c9269-206">Priority</span></span></li><li><span data-ttu-id="c9269-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="c9269-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="c9269-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="c9269-208">xUnit</span></span>          | <ul><li><span data-ttu-id="c9269-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c9269-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="c9269-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c9269-210">DisplayName</span></span></li><li><span data-ttu-id="c9269-211">Tratti</span><span class="sxs-lookup"><span data-stu-id="c9269-211">Traits</span></span></li></ul>                                   |

<span data-ttu-id="c9269-212">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="c9269-212">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="c9269-213">Operatore</span><span class="sxs-lookup"><span data-stu-id="c9269-213">Operator</span></span> | <span data-ttu-id="c9269-214">Funzione</span><span class="sxs-lookup"><span data-stu-id="c9269-214">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="c9269-215">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="c9269-215">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="c9269-216">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="c9269-216">Not exact match</span></span> |
| `~`      | <span data-ttu-id="c9269-217">Contiene</span><span class="sxs-lookup"><span data-stu-id="c9269-217">Contains</span></span>        |

<span data-ttu-id="c9269-218">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="c9269-218">`<value>` is a string.</span></span> <span data-ttu-id="c9269-219">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c9269-219">All the lookups are case insensitive.</span></span>

<span data-ttu-id="c9269-220">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="c9269-220">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="c9269-221">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="c9269-221">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="c9269-222">Operatore</span><span class="sxs-lookup"><span data-stu-id="c9269-222">Operator</span></span>            | <span data-ttu-id="c9269-223">Funzione</span><span class="sxs-lookup"><span data-stu-id="c9269-223">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="c9269-224">OR</span><span class="sxs-lookup"><span data-stu-id="c9269-224">OR</span></span>       |
| `&`                 | <span data-ttu-id="c9269-225">AND</span><span class="sxs-lookup"><span data-stu-id="c9269-225">AND</span></span>      |

<span data-ttu-id="c9269-226">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="c9269-226">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="c9269-227">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c9269-227">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9269-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9269-228">See also</span></span>

* [<span data-ttu-id="c9269-229">Frameworks e destinazioni</span><span class="sxs-lookup"><span data-stu-id="c9269-229">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="c9269-230">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="c9269-230">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
