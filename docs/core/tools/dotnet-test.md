---
title: Comando dotnet test - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 73b1d832b855798dd053187bbb24e8fb989fedf1
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "46696456"
---
# <a name="dotnet-test"></a><span data-ttu-id="a5c07-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="a5c07-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a5c07-104">nome</span><span class="sxs-lookup"><span data-stu-id="a5c07-104">Name</span></span>

<span data-ttu-id="a5c07-105">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a5c07-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a5c07-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a5c07-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a5c07-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a5c07-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a5c07-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a5c07-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a5c07-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="a5c07-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5c07-110">Description</span></span>

<span data-ttu-id="a5c07-111">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="a5c07-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="a5c07-112">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="a5c07-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="a5c07-113">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="a5c07-114">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="a5c07-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="a5c07-115">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a5c07-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="a5c07-116">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a5c07-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="a5c07-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a5c07-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="a5c07-118">Percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-118">Path to the test project.</span></span> <span data-ttu-id="a5c07-119">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a5c07-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="a5c07-120">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a5c07-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a5c07-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a5c07-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="a5c07-122">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="a5c07-123">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="a5c07-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="a5c07-124">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="a5c07-125">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="a5c07-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a5c07-126">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5c07-126">Defines the build configuration.</span></span> <span data-ttu-id="a5c07-127">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="a5c07-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="a5c07-128">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-128">Enables data collector for the test run.</span></span> <span data-ttu-id="a5c07-129">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="a5c07-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="a5c07-130">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="a5c07-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a5c07-131">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="a5c07-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="a5c07-132">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="a5c07-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="a5c07-133">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="a5c07-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="a5c07-134">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="a5c07-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="a5c07-135">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="a5c07-136">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="a5c07-137">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a5c07-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="a5c07-138">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="a5c07-139">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a5c07-140">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="a5c07-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="a5c07-141">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="a5c07-142">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="a5c07-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="a5c07-143">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="a5c07-144">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="a5c07-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a5c07-145">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a5c07-146">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="a5c07-147">Argomenti passati come configurazioni RunSettings per il test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-147">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="a5c07-148">Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --.</span><span class="sxs-lookup"><span data-stu-id="a5c07-148">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="a5c07-149">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="a5c07-149">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="a5c07-150">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="a5c07-150">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="a5c07-151">Per altre informazioni su RunSettings, vedere [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: passaggio di argomenti RunSettings).</span><span class="sxs-lookup"><span data-stu-id="a5c07-151">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a5c07-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a5c07-152">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="a5c07-153">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-153">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a5c07-154">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5c07-154">Defines the build configuration.</span></span> <span data-ttu-id="a5c07-155">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="a5c07-155">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="a5c07-156">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-156">Enables data collector for the test run.</span></span> <span data-ttu-id="a5c07-157">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="a5c07-157">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="a5c07-158">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="a5c07-158">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a5c07-159">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="a5c07-159">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="a5c07-160">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="a5c07-160">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="a5c07-161">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="a5c07-161">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="a5c07-162">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="a5c07-162">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="a5c07-163">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-163">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="a5c07-164">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-164">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="a5c07-165">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a5c07-165">Doesn't build the test project before running it.</span></span> <span data-ttu-id="a5c07-166">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="a5c07-167">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-167">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a5c07-168">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="a5c07-168">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="a5c07-169">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-169">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="a5c07-170">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="a5c07-170">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="a5c07-171">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-171">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="a5c07-172">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="a5c07-172">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a5c07-173">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-173">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a5c07-174">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-174">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a5c07-175">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a5c07-175">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="a5c07-176">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-176">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="a5c07-177">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5c07-177">Defines the build configuration.</span></span> <span data-ttu-id="a5c07-178">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="a5c07-178">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="a5c07-179">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="a5c07-179">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="a5c07-180">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="a5c07-180">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="a5c07-181">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="a5c07-181">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="a5c07-182">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="a5c07-182">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="a5c07-183">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="a5c07-183">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="a5c07-184">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-184">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="a5c07-185">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-185">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="a5c07-186">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a5c07-186">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a5c07-187">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="a5c07-187">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="a5c07-188">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="a5c07-188">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="a5c07-189">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="a5c07-189">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="a5c07-190">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="a5c07-190">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a5c07-191">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-191">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="a5c07-192">Esempi</span><span class="sxs-lookup"><span data-stu-id="a5c07-192">Examples</span></span>

<span data-ttu-id="a5c07-193">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a5c07-193">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="a5c07-194">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="a5c07-194">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="a5c07-195">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati di test in formato trx:</span><span class="sxs-lookup"><span data-stu-id="a5c07-195">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="a5c07-196">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="a5c07-196">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="a5c07-197">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-197">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="a5c07-198">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-198">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="a5c07-199">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="a5c07-199">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="a5c07-200">Framework di test</span><span class="sxs-lookup"><span data-stu-id="a5c07-200">Test Framework</span></span> | <span data-ttu-id="a5c07-201">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="a5c07-201">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a5c07-202">MSTest</span><span class="sxs-lookup"><span data-stu-id="a5c07-202">MSTest</span></span>         | <ul><li><span data-ttu-id="a5c07-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="a5c07-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="a5c07-204">nome</span><span class="sxs-lookup"><span data-stu-id="a5c07-204">Name</span></span></li><li><span data-ttu-id="a5c07-205">ClassName</span><span class="sxs-lookup"><span data-stu-id="a5c07-205">ClassName</span></span></li><li><span data-ttu-id="a5c07-206">Priorità</span><span class="sxs-lookup"><span data-stu-id="a5c07-206">Priority</span></span></li><li><span data-ttu-id="a5c07-207">TestCategory</span><span class="sxs-lookup"><span data-stu-id="a5c07-207">TestCategory</span></span></li></ul> |
| <span data-ttu-id="a5c07-208">xUnit</span><span class="sxs-lookup"><span data-stu-id="a5c07-208">xUnit</span></span>          | <ul><li><span data-ttu-id="a5c07-209">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="a5c07-209">FullyQualifiedName</span></span></li><li><span data-ttu-id="a5c07-210">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a5c07-210">DisplayName</span></span></li><li><span data-ttu-id="a5c07-211">Tratti</span><span class="sxs-lookup"><span data-stu-id="a5c07-211">Traits</span></span></li></ul>                                   |

<span data-ttu-id="a5c07-212">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="a5c07-212">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="a5c07-213">Operatore</span><span class="sxs-lookup"><span data-stu-id="a5c07-213">Operator</span></span> | <span data-ttu-id="a5c07-214">Funzione</span><span class="sxs-lookup"><span data-stu-id="a5c07-214">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="a5c07-215">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="a5c07-215">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="a5c07-216">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="a5c07-216">Not exact match</span></span> |
| `~`      | <span data-ttu-id="a5c07-217">Contiene</span><span class="sxs-lookup"><span data-stu-id="a5c07-217">Contains</span></span>        |

<span data-ttu-id="a5c07-218">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="a5c07-218">`<value>` is a string.</span></span> <span data-ttu-id="a5c07-219">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="a5c07-219">All the lookups are case insensitive.</span></span>

<span data-ttu-id="a5c07-220">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="a5c07-220">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="a5c07-221">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="a5c07-221">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="a5c07-222">Operatore</span><span class="sxs-lookup"><span data-stu-id="a5c07-222">Operator</span></span>            | <span data-ttu-id="a5c07-223">Funzione</span><span class="sxs-lookup"><span data-stu-id="a5c07-223">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="a5c07-224">OR</span><span class="sxs-lookup"><span data-stu-id="a5c07-224">OR</span></span>       |
| `&`                 | <span data-ttu-id="a5c07-225">AND</span><span class="sxs-lookup"><span data-stu-id="a5c07-225">AND</span></span>      |

<span data-ttu-id="a5c07-226">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="a5c07-226">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="a5c07-227">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="a5c07-227">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a5c07-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5c07-228">See also</span></span>

* [<span data-ttu-id="a5c07-229">Frameworks e destinazioni</span><span class="sxs-lookup"><span data-stu-id="a5c07-229">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="a5c07-230">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a5c07-230">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
