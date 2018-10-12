---
title: Comando dotnet test - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e80ba874ec8d0fbc49858719dc3b9b6e02254c78
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696456"
---
# <a name="dotnet-test"></a><span data-ttu-id="b90fb-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b90fb-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b90fb-104">nome</span><span class="sxs-lookup"><span data-stu-id="b90fb-104">Name</span></span>

<span data-ttu-id="b90fb-105">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b90fb-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b90fb-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b90fb-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b90fb-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b90fb-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b90fb-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b90fb-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b90fb-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="b90fb-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b90fb-110">Description</span></span>

<span data-ttu-id="b90fb-111">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="b90fb-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="b90fb-112">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="b90fb-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="b90fb-113">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="b90fb-114">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="b90fb-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="b90fb-115">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b90fb-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="b90fb-116">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b90fb-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="b90fb-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b90fb-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b90fb-118">Percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-118">Path to the test project.</span></span> <span data-ttu-id="b90fb-119">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b90fb-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="b90fb-120">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b90fb-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b90fb-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b90fb-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="b90fb-122">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="b90fb-123">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="b90fb-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="b90fb-124">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="b90fb-125">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="b90fb-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b90fb-126">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b90fb-126">Defines the build configuration.</span></span> <span data-ttu-id="b90fb-127">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="b90fb-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="b90fb-128">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-128">Enables data collector for the test run.</span></span> <span data-ttu-id="b90fb-129">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="b90fb-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="b90fb-130">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="b90fb-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b90fb-131">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="b90fb-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b90fb-132">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="b90fb-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b90fb-133">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="b90fb-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b90fb-134">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b90fb-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="b90fb-135">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="b90fb-136">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="b90fb-137">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b90fb-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="b90fb-138">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="b90fb-139">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b90fb-140">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="b90fb-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="b90fb-141">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="b90fb-142">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="b90fb-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="b90fb-143">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-143">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="b90fb-144">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="b90fb-144">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b90fb-145">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b90fb-146">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b90fb-147">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b90fb-147">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="b90fb-148">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-148">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b90fb-149">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b90fb-149">Defines the build configuration.</span></span> <span data-ttu-id="b90fb-150">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="b90fb-150">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="b90fb-151">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-151">Enables data collector for the test run.</span></span> <span data-ttu-id="b90fb-152">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="b90fb-152">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="b90fb-153">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="b90fb-153">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b90fb-154">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="b90fb-154">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b90fb-155">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="b90fb-155">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b90fb-156">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="b90fb-156">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b90fb-157">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b90fb-157">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="b90fb-158">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-158">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="b90fb-159">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-159">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="b90fb-160">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b90fb-160">Doesn't build the test project before running it.</span></span> <span data-ttu-id="b90fb-161">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-161">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="b90fb-162">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-162">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b90fb-163">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="b90fb-163">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="b90fb-164">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-164">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="b90fb-165">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="b90fb-165">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="b90fb-166">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-166">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="b90fb-167">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="b90fb-167">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b90fb-168">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b90fb-169">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b90fb-170">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b90fb-170">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="b90fb-171">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-171">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b90fb-172">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b90fb-172">Defines the build configuration.</span></span> <span data-ttu-id="b90fb-173">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="b90fb-173">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="b90fb-174">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="b90fb-174">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b90fb-175">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="b90fb-175">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b90fb-176">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="b90fb-176">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="b90fb-177">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="b90fb-177">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="b90fb-178">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b90fb-178">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="b90fb-179">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-179">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="b90fb-180">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-180">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="b90fb-181">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b90fb-181">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b90fb-182">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="b90fb-182">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="b90fb-183">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="b90fb-183">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="b90fb-184">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="b90fb-184">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b90fb-185">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="b90fb-185">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b90fb-186">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b90fb-187">Esempi</span><span class="sxs-lookup"><span data-stu-id="b90fb-187">Examples</span></span>

<span data-ttu-id="b90fb-188">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="b90fb-188">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="b90fb-189">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="b90fb-189">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="b90fb-190">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati di test in formato trx:</span><span class="sxs-lookup"><span data-stu-id="b90fb-190">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="b90fb-191">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="b90fb-191">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="b90fb-192">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-192">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="b90fb-193">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-193">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="b90fb-194">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="b90fb-194">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="b90fb-195">Framework di test</span><span class="sxs-lookup"><span data-stu-id="b90fb-195">Test Framework</span></span> | <span data-ttu-id="b90fb-196">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="b90fb-196">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b90fb-197">MSTest</span><span class="sxs-lookup"><span data-stu-id="b90fb-197">MSTest</span></span>         | <ul><li><span data-ttu-id="b90fb-198">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b90fb-198">FullyQualifiedName</span></span></li><li><span data-ttu-id="b90fb-199">nome</span><span class="sxs-lookup"><span data-stu-id="b90fb-199">Name</span></span></li><li><span data-ttu-id="b90fb-200">ClassName</span><span class="sxs-lookup"><span data-stu-id="b90fb-200">ClassName</span></span></li><li><span data-ttu-id="b90fb-201">Priorità</span><span class="sxs-lookup"><span data-stu-id="b90fb-201">Priority</span></span></li><li><span data-ttu-id="b90fb-202">TestCategory</span><span class="sxs-lookup"><span data-stu-id="b90fb-202">TestCategory</span></span></li></ul> |
| <span data-ttu-id="b90fb-203">xUnit</span><span class="sxs-lookup"><span data-stu-id="b90fb-203">xUnit</span></span>          | <ul><li><span data-ttu-id="b90fb-204">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b90fb-204">FullyQualifiedName</span></span></li><li><span data-ttu-id="b90fb-205">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b90fb-205">DisplayName</span></span></li><li><span data-ttu-id="b90fb-206">Tratti</span><span class="sxs-lookup"><span data-stu-id="b90fb-206">Traits</span></span></li></ul>                                   |

<span data-ttu-id="b90fb-207">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="b90fb-207">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="b90fb-208">Operatore</span><span class="sxs-lookup"><span data-stu-id="b90fb-208">Operator</span></span> | <span data-ttu-id="b90fb-209">Funzione</span><span class="sxs-lookup"><span data-stu-id="b90fb-209">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="b90fb-210">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="b90fb-210">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="b90fb-211">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="b90fb-211">Not exact match</span></span> |
| `~`      | <span data-ttu-id="b90fb-212">Contiene</span><span class="sxs-lookup"><span data-stu-id="b90fb-212">Contains</span></span>        |

<span data-ttu-id="b90fb-213">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="b90fb-213">`<value>` is a string.</span></span> <span data-ttu-id="b90fb-214">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b90fb-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="b90fb-215">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="b90fb-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="b90fb-216">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="b90fb-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="b90fb-217">Operatore</span><span class="sxs-lookup"><span data-stu-id="b90fb-217">Operator</span></span>            | <span data-ttu-id="b90fb-218">Funzione</span><span class="sxs-lookup"><span data-stu-id="b90fb-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="b90fb-219">OR</span><span class="sxs-lookup"><span data-stu-id="b90fb-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="b90fb-220">AND</span><span class="sxs-lookup"><span data-stu-id="b90fb-220">AND</span></span>      |

<span data-ttu-id="b90fb-221">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="b90fb-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="b90fb-222">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="b90fb-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b90fb-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b90fb-223">See also</span></span>

* [<span data-ttu-id="b90fb-224">Frameworks e destinazioni</span><span class="sxs-lookup"><span data-stu-id="b90fb-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="b90fb-225">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="b90fb-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
