---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 05/29/2018
ms.openlocfilehash: 6b67273f549edd7712237756a5aba13d5cb59a61
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410363"
---
# <a name="dotnet-test"></a><span data-ttu-id="73e40-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="73e40-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="73e40-104">nome</span><span class="sxs-lookup"><span data-stu-id="73e40-104">Name</span></span>

<span data-ttu-id="73e40-105">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="73e40-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="73e40-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="73e40-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="73e40-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="73e40-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="73e40-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="73e40-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="73e40-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="73e40-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="73e40-110">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="73e40-110">Description</span></span>

<span data-ttu-id="73e40-111">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="73e40-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="73e40-112">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="73e40-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="73e40-113">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="73e40-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="73e40-114">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="73e40-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="73e40-115">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="73e40-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="73e40-116">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="73e40-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="73e40-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="73e40-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="73e40-118">Percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="73e40-118">Path to the test project.</span></span> <span data-ttu-id="73e40-119">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="73e40-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="73e40-120">Opzioni</span><span class="sxs-lookup"><span data-stu-id="73e40-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="73e40-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="73e40-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="73e40-122">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="73e40-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="73e40-123">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="73e40-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="73e40-124">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="73e40-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="73e40-125">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="73e40-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="73e40-126">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="73e40-126">Defines the build configuration.</span></span> <span data-ttu-id="73e40-127">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="73e40-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="73e40-128">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="73e40-128">Enables data collector for the test run.</span></span> <span data-ttu-id="73e40-129">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="73e40-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="73e40-130">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="73e40-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="73e40-131">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="73e40-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="73e40-132">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="73e40-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="73e40-133">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="73e40-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="73e40-134">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="73e40-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="73e40-135">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="73e40-136">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="73e40-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="73e40-137">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73e40-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="73e40-138">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="73e40-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="73e40-139">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="73e40-140">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="73e40-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="73e40-141">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="73e40-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="73e40-142">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="73e40-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="73e40-143">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="73e40-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="73e40-144">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="73e40-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="73e40-145">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="73e40-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="73e40-146">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="73e40-147">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="73e40-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="73e40-148">Argomenti passati come configurazioni RunSettings per il test.</span><span class="sxs-lookup"><span data-stu-id="73e40-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="73e40-149">Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --.</span><span class="sxs-lookup"><span data-stu-id="73e40-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="73e40-150">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="73e40-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="73e40-151">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="73e40-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="73e40-152">Per altre informazioni su RunSettings, vedere [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: passare argomenti RunSettings).</span><span class="sxs-lookup"><span data-stu-id="73e40-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="73e40-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="73e40-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="73e40-154">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="73e40-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="73e40-155">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="73e40-155">Defines the build configuration.</span></span> <span data-ttu-id="73e40-156">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="73e40-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="73e40-157">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="73e40-157">Enables data collector for the test run.</span></span> <span data-ttu-id="73e40-158">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="73e40-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="73e40-159">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="73e40-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="73e40-160">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="73e40-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="73e40-161">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="73e40-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="73e40-162">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="73e40-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="73e40-163">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="73e40-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="73e40-164">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="73e40-165">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="73e40-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="73e40-166">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73e40-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="73e40-167">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="73e40-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="73e40-168">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="73e40-169">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="73e40-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="73e40-170">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="73e40-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="73e40-171">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="73e40-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="73e40-172">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="73e40-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="73e40-173">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="73e40-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="73e40-174">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="73e40-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="73e40-175">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="73e40-176">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="73e40-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="73e40-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="73e40-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="73e40-178">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="73e40-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="73e40-179">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="73e40-179">Defines the build configuration.</span></span> <span data-ttu-id="73e40-180">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="73e40-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="73e40-181">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="73e40-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="73e40-182">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="73e40-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="73e40-183">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="73e40-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="73e40-184">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="73e40-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="73e40-185">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="73e40-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="73e40-186">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="73e40-187">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="73e40-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="73e40-188">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73e40-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="73e40-189">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="73e40-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="73e40-190">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="73e40-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="73e40-191">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="73e40-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="73e40-192">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="73e40-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="73e40-193">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="73e40-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="73e40-194">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="73e40-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="73e40-195">Esempi</span><span class="sxs-lookup"><span data-stu-id="73e40-195">Examples</span></span>

<span data-ttu-id="73e40-196">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="73e40-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="73e40-197">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="73e40-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="73e40-198">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati di test in formato trx:</span><span class="sxs-lookup"><span data-stu-id="73e40-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="73e40-199">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="73e40-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="73e40-200">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="73e40-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="73e40-201">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="73e40-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="73e40-202">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="73e40-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="73e40-203">Framework di test</span><span class="sxs-lookup"><span data-stu-id="73e40-203">Test Framework</span></span> | <span data-ttu-id="73e40-204">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="73e40-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="73e40-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="73e40-205">MSTest</span></span>         | <ul><li><span data-ttu-id="73e40-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="73e40-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="73e40-207">nome</span><span class="sxs-lookup"><span data-stu-id="73e40-207">Name</span></span></li><li><span data-ttu-id="73e40-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="73e40-208">ClassName</span></span></li><li><span data-ttu-id="73e40-209">Priorità</span><span class="sxs-lookup"><span data-stu-id="73e40-209">Priority</span></span></li><li><span data-ttu-id="73e40-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="73e40-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="73e40-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="73e40-211">xUnit</span></span>          | <ul><li><span data-ttu-id="73e40-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="73e40-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="73e40-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="73e40-213">DisplayName</span></span></li><li><span data-ttu-id="73e40-214">Tratti</span><span class="sxs-lookup"><span data-stu-id="73e40-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="73e40-215">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="73e40-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="73e40-216">Operatore</span><span class="sxs-lookup"><span data-stu-id="73e40-216">Operator</span></span> | <span data-ttu-id="73e40-217">Funzione</span><span class="sxs-lookup"><span data-stu-id="73e40-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="73e40-218">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="73e40-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="73e40-219">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="73e40-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="73e40-220">Contiene</span><span class="sxs-lookup"><span data-stu-id="73e40-220">Contains</span></span>        |

<span data-ttu-id="73e40-221">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="73e40-221">`<value>` is a string.</span></span> <span data-ttu-id="73e40-222">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="73e40-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="73e40-223">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="73e40-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="73e40-224">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="73e40-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="73e40-225">Operatore</span><span class="sxs-lookup"><span data-stu-id="73e40-225">Operator</span></span>            | <span data-ttu-id="73e40-226">Funzione</span><span class="sxs-lookup"><span data-stu-id="73e40-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="73e40-227">OR</span><span class="sxs-lookup"><span data-stu-id="73e40-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="73e40-228">AND</span><span class="sxs-lookup"><span data-stu-id="73e40-228">AND</span></span>      |

<span data-ttu-id="73e40-229">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="73e40-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="73e40-230">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="73e40-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="73e40-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73e40-231">See also</span></span>

- [<span data-ttu-id="73e40-232">Frameworks e destinazioni</span><span class="sxs-lookup"><span data-stu-id="73e40-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="73e40-233">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="73e40-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
