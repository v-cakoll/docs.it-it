---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 04/29/2020
ms.openlocfilehash: 9b1e190579902dda71547b01f31dd5adcc22fe9c
ms.sourcegitcommit: c8c3e1c63a00b7d27f76f5e50ee6469e6bdc8987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251192"
---
# <a name="dotnet-test"></a><span data-ttu-id="db527-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="db527-103">dotnet test</span></span>

<span data-ttu-id="db527-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="db527-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="db527-105">Nome</span><span class="sxs-lookup"><span data-stu-id="db527-105">Name</span></span>

<span data-ttu-id="db527-106">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="db527-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="db527-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="db527-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <ADAPTER_PATH>] [--blame] [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>] [--blame-crash-collect-always]
    [--blame-hang] [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <RESULTS_DIR>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="db527-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db527-108">Description</span></span>

<span data-ttu-id="db527-109">Il `dotnet test` comando viene usato per eseguire unit test in una determinata soluzione.</span><span class="sxs-lookup"><span data-stu-id="db527-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="db527-110">Il `dotnet test` comando Compila la soluzione ed esegue un'applicazione host di test per ogni progetto di test nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="db527-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="db527-111">L'host di test esegue i test nel progetto specificato utilizzando un Framework di test, ad esempio MSTest, NUnit o xUnit, e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="db527-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="db527-112">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="db527-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="db527-113">Per i progetti multitargeting, i test vengono eseguiti per ogni Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="db527-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="db527-114">L'host di test e il framework unit test vengono inclusi nel pacchetto come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="db527-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="db527-115">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="db527-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="db527-116">Dove `Microsoft.NET.Test.Sdk` è l'host di test, `xunit` è il Framework di test.</span><span class="sxs-lookup"><span data-stu-id="db527-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="db527-117">E `xunit.runner.visualstudio` è un adattatore di test, che consente al Framework xUnit di funzionare con l'host di test.</span><span class="sxs-lookup"><span data-stu-id="db527-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="db527-118">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="db527-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="db527-119">Argomenti</span><span class="sxs-lookup"><span data-stu-id="db527-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="db527-120">Percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="db527-120">Path to the test project.</span></span>
  - <span data-ttu-id="db527-121">Percorso della soluzione.</span><span class="sxs-lookup"><span data-stu-id="db527-121">Path to the solution.</span></span>
  - <span data-ttu-id="db527-122">Percorso di una directory che contiene un progetto o una soluzione.</span><span class="sxs-lookup"><span data-stu-id="db527-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="db527-123">Percorso di un file con estensione *dll* del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="db527-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="db527-124">Se non specificato, Cerca un progetto o una soluzione nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="db527-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="db527-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="db527-125">Options</span></span>

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  <span data-ttu-id="db527-126">Percorso di una directory in cui eseguire la ricerca di altri adattatori di test.</span><span class="sxs-lookup"><span data-stu-id="db527-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="db527-127">Vengono controllati solo i file con *estensione dll* con suffisso `.TestAdapter.dll` .</span><span class="sxs-lookup"><span data-stu-id="db527-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="db527-128">Se non specificato, viene eseguita una ricerca nella directory della *dll* test.</span><span class="sxs-lookup"><span data-stu-id="db527-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="db527-129">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="db527-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="db527-130">Questa opzione è utile per isolare i test problematici che provocano l'arresto anomalo dell'host di test.</span><span class="sxs-lookup"><span data-stu-id="db527-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="db527-131">Quando viene rilevato un arresto anomalo del sistema, viene creato un file di sequenza in `TestResults/<Guid>/<Guid>_Sequence.xml` che acquisisce l'ordine dei test eseguiti prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="db527-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- <span data-ttu-id="db527-132">**`--blame-crash`**(Disponibile a partire da .NET 5,0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="db527-132">**`--blame-crash`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="db527-133">Esegue i test in modalità di incolpa e raccoglie un dump di arresto anomalo del sistema quando l'host di test viene terminato in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="db527-133">Runs the tests in blame mode and collects a crash dump when the test host exits unexpectedly.</span></span> <span data-ttu-id="db527-134">Questa opzione è supportata solo in Windows.</span><span class="sxs-lookup"><span data-stu-id="db527-134">This option is only supported on Windows.</span></span> <span data-ttu-id="db527-135">Una directory che contiene *procdump.exe* e *procdump64.exe* deve trovarsi nella variabile di ambiente path o PROCDUMP_PATH.</span><span class="sxs-lookup"><span data-stu-id="db527-135">A directory that contains *procdump.exe* and *procdump64.exe* must be in the PATH or PROCDUMP_PATH environment variable.</span></span> <span data-ttu-id="db527-136">[Scaricare gli strumenti](https://docs.microsoft.com/sysinternals/downloads/procdump).</span><span class="sxs-lookup"><span data-stu-id="db527-136">[Download the tools](https://docs.microsoft.com/sysinternals/downloads/procdump).</span></span> <span data-ttu-id="db527-137">Implica `--blame` .</span><span class="sxs-lookup"><span data-stu-id="db527-137">Implies `--blame`.</span></span>

- <span data-ttu-id="db527-138">**`--blame-crash-dump-type <DUMP_TYPE>`**(Disponibile a partire da .NET 5,0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="db527-138">**`--blame-crash-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="db527-139">Tipo di dump di arresto anomalo del sistema da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="db527-139">The type of crash dump to be collected.</span></span> <span data-ttu-id="db527-140">Implica `--blame-crash` .</span><span class="sxs-lookup"><span data-stu-id="db527-140">Implies `--blame-crash`.</span></span>

- <span data-ttu-id="db527-141">**`--blame-crash-collect-always`**(Disponibile a partire da .NET 5,0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="db527-141">**`--blame-crash-collect-always`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="db527-142">Raccoglie un dump di arresto anomalo del sistema durante l'uscita prevista dell'host di test.</span><span class="sxs-lookup"><span data-stu-id="db527-142">Collects a crash dump on expected as well as unexpected test host exit.</span></span>

- <span data-ttu-id="db527-143">**`--blame-hang`**(Disponibile a partire da .NET 5,0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="db527-143">**`--blame-hang`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="db527-144">Eseguire i test in modalità di incolpa e raccoglie un dump di blocco quando un test supera il timeout specificato.</span><span class="sxs-lookup"><span data-stu-id="db527-144">Run the tests in blame mode and collects a hang dump when a test exceeds the given timeout.</span></span>

- <span data-ttu-id="db527-145">**`--blame-hang-dump-type <DUMP_TYPE>`**(Disponibile a partire da .NET 5,0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="db527-145">**`--blame-hang-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="db527-146">Tipo di dump di arresto anomalo del sistema da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="db527-146">The type of crash dump to be collected.</span></span> <span data-ttu-id="db527-147">Deve essere `full` , `mini` o `none` .</span><span class="sxs-lookup"><span data-stu-id="db527-147">It should be `full`, `mini`, or `none`.</span></span> <span data-ttu-id="db527-148">Quando `none` si specifica, l'host di test viene terminato in caso di timeout, ma non viene raccolto alcun dump.</span><span class="sxs-lookup"><span data-stu-id="db527-148">When `none` is specified, test host is terminated on timeout, but no dump is collected.</span></span> <span data-ttu-id="db527-149">Implica `--blame-hang` .</span><span class="sxs-lookup"><span data-stu-id="db527-149">Implies `--blame-hang`.</span></span>

- <span data-ttu-id="db527-150">**`--blame-hang-timeout <TIMESPAN>`**(Disponibile a partire da .NET 5,0 Preview SDK)</span><span class="sxs-lookup"><span data-stu-id="db527-150">**`--blame-hang-timeout <TIMESPAN>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="db527-151">Timeout per test, dopo il quale viene attivato un dump di blocco e il processo host di test viene terminato.</span><span class="sxs-lookup"><span data-stu-id="db527-151">Per-test timeout, after which a hang dump is triggered and the test host process is terminated.</span></span> <span data-ttu-id="db527-152">Il valore di timeout viene specificato in uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="db527-152">The timeout value is specified in one of the following formats:</span></span>
  
  - <span data-ttu-id="db527-153">1.5 h</span><span class="sxs-lookup"><span data-stu-id="db527-153">1.5h</span></span>
  - <span data-ttu-id="db527-154">90m</span><span class="sxs-lookup"><span data-stu-id="db527-154">90m</span></span>
  - <span data-ttu-id="db527-155">5400</span><span class="sxs-lookup"><span data-stu-id="db527-155">5400s</span></span>
  - <span data-ttu-id="db527-156">5400000ms</span><span class="sxs-lookup"><span data-stu-id="db527-156">5400000ms</span></span>

  <span data-ttu-id="db527-157">Quando non viene utilizzata alcuna unità (ad esempio, 5,4 milioni), si presuppone che il valore sia in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="db527-157">When no unit is used (for example, 5400000), the value is assumed to be in milliseconds.</span></span> <span data-ttu-id="db527-158">Quando viene utilizzato insieme ai test basati sui dati, il comportamento di timeout dipende dall'adattatore di test utilizzato.</span><span class="sxs-lookup"><span data-stu-id="db527-158">When used together with data driven tests, the timeout behavior depends on the test adapter used.</span></span> <span data-ttu-id="db527-159">Per xUnit e NUnit il timeout viene rinnovato dopo ogni test case.</span><span class="sxs-lookup"><span data-stu-id="db527-159">For xUnit and NUnit the timeout is renewed after every test case.</span></span> <span data-ttu-id="db527-160">Per MSTest, il timeout viene usato per tutti testCases.</span><span class="sxs-lookup"><span data-stu-id="db527-160">For MSTest, the timeout is used for all testcases.</span></span> <span data-ttu-id="db527-161">Questa opzione è supportata in Windows con netcoreapp 2.1 e versioni successive e in Linux con netcoreapp 3.1 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="db527-161">This option is supported on Windows with netcoreapp2.1 and later, and on Linux with netcoreapp3.1 and later.</span></span> <span data-ttu-id="db527-162">macOS non è supportato.</span><span class="sxs-lookup"><span data-stu-id="db527-162">macOS is not supported.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="db527-163">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="db527-163">Defines the build configuration.</span></span> <span data-ttu-id="db527-164">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="db527-164">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_NAME>`**

  <span data-ttu-id="db527-165">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="db527-165">Enables data collector for the test run.</span></span> <span data-ttu-id="db527-166">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="db527-166">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="db527-167">Per raccogliere code coverage su qualsiasi piattaforma supportata da .NET Core, installare [copriletto](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) e usare l' `--collect:"XPlat Code Coverage"` opzione.</span><span class="sxs-lookup"><span data-stu-id="db527-167">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="db527-168">In Windows è possibile raccogliere code coverage utilizzando l' `--collect "Code Coverage"` opzione.</span><span class="sxs-lookup"><span data-stu-id="db527-168">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="db527-169">Questa opzione genera un file con *estensione coverage* , che può essere aperto in Visual Studio 2019 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="db527-169">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="db527-170">Per ulteriori informazioni, vedere [utilizzare code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) e [personalizzare code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span><span class="sxs-lookup"><span data-stu-id="db527-170">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <LOG_FILE>`**

  <span data-ttu-id="db527-171">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato e nei file accanto.</span><span class="sxs-lookup"><span data-stu-id="db527-171">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="db527-172">Il processo che registra i messaggi determina quali file vengono creati, ad esempio `*.host_<date>.txt` per il log dell'host di test e `*.datacollector_<date>.txt` per il log dell'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="db527-172">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="db527-173">Impone l'uso di `dotnet` o .NET Framework host di test per i file binari del test.</span><span class="sxs-lookup"><span data-stu-id="db527-173">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="db527-174">Questa opzione determina solo il tipo di host da usare.</span><span class="sxs-lookup"><span data-stu-id="db527-174">This option only determines which type of host to use.</span></span> <span data-ttu-id="db527-175">La versione effettiva del Framework da utilizzare è determinata dalla *runtimeconfig.js* del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="db527-175">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="db527-176">Quando non è specificato, viene usato l' [attributo dell'assembly TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute) per determinare il tipo di host.</span><span class="sxs-lookup"><span data-stu-id="db527-176">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="db527-177">Quando tale attributo viene rimosso dal file con *estensione dll*, viene utilizzato l'host .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db527-177">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="db527-178">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="db527-178">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="db527-179">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="db527-179">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="db527-180">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="db527-180">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="db527-181">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="db527-181">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="db527-182">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="db527-182">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="db527-183">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="db527-183">For example, to complete authentication.</span></span> <span data-ttu-id="db527-184">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="db527-184">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER>`**

  <span data-ttu-id="db527-185">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="db527-185">Specifies a logger for test results.</span></span> <span data-ttu-id="db527-186">Diversamente da MSBuild, il test DotNet non accetta abbreviazioni: invece di `-l "console;v=d"` usare `-l "console;verbosity=detailed"` .</span><span class="sxs-lookup"><span data-stu-id="db527-186">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="db527-187">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="db527-187">Doesn't build the test project before running it.</span></span> <span data-ttu-id="db527-188">Viene inoltre impostato in modo implicito il `--no-restore` flag-.</span><span class="sxs-lookup"><span data-stu-id="db527-188">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="db527-189">Esegui test senza visualizzare il banner Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="db527-189">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="db527-190">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="db527-190">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="db527-191">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="db527-191">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="db527-192">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="db527-192">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="db527-193">Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="db527-193">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="db527-194">Per i progetti con più framework di destinazione (tramite la `TargetFrameworks` proprietà), è necessario definire anche `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="db527-194">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="db527-195">`dotnet test`esegue sempre i test dalla directory di output.</span><span class="sxs-lookup"><span data-stu-id="db527-195">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="db527-196">È possibile usare <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> per utilizzare gli asset di test nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="db527-196">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <RESULTS_DIR>`**

  <span data-ttu-id="db527-197">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="db527-197">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="db527-198">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="db527-198">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="db527-199">Il valore predefinito è `TestResults` la directory che contiene il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="db527-199">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="db527-200">Runtime di destinazione di cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="db527-200">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="db527-201">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="db527-201">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="db527-202">L' `TargetPlatform` elemento (x86 | x64) non ha alcun effetto per `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="db527-202">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="db527-203">Per eseguire test destinati a x86, installare la versione x86 di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="db527-203">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="db527-204">Il bit del *dotnet.exe* che si trova nel percorso è quello che verrà usato per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="db527-204">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="db527-205">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="db527-205">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="db527-206">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="db527-206">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="db527-207">Configurare un agente di test</span><span class="sxs-lookup"><span data-stu-id="db527-207">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="db527-208">Elenca i test individuati anziché eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="db527-208">List the discovered tests instead of running the tests.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="db527-209">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="db527-209">Sets the verbosity level of the command.</span></span> <span data-ttu-id="db527-210">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="db527-210">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="db527-211">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="db527-211">The default is `minimal`.</span></span> <span data-ttu-id="db527-212">Per altre informazioni, vedere <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="db527-212">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="db527-213">**`RunSettings`** argomenti</span><span class="sxs-lookup"><span data-stu-id="db527-213">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="db527-214">Inline `RunSettings` vengono passati come ultimi argomenti nella riga di comando dopo "--" (si noti lo spazio dopo--).</span><span class="sxs-lookup"><span data-stu-id="db527-214">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="db527-215">Inline `RunSettings` sono specificati come `[name]=[value]` coppie.</span><span class="sxs-lookup"><span data-stu-id="db527-215">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="db527-216">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="db527-216">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="db527-217">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="db527-217">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="db527-218">Per ulteriori informazioni, vedere [passaggio di argomenti runsettings tramite la riga di comando](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="db527-218">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="db527-219">Esempi</span><span class="sxs-lookup"><span data-stu-id="db527-219">Examples</span></span>

- <span data-ttu-id="db527-220">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="db527-220">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="db527-221">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="db527-221">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="db527-222">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati del test nel formato TRX:</span><span class="sxs-lookup"><span data-stu-id="db527-222">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="db527-223">Eseguire i test nel progetto nella directory corrente e generare un file di code coverage (dopo l'installazione dell'integrazione di [copriletto](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) Collectors):</span><span class="sxs-lookup"><span data-stu-id="db527-223">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) collectors integration):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="db527-224">Eseguire i test nel progetto nella directory corrente e generare un file di code coverage (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="db527-224">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="db527-225">Eseguire i test nel progetto nella directory corrente e accedere con un livello di dettaglio dettagliato alla console:</span><span class="sxs-lookup"><span data-stu-id="db527-225">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- <span data-ttu-id="db527-226">Eseguire i test nel progetto nella directory corrente e segnalare i test in corso quando l'host di test si è arrestato in modo anomalo:</span><span class="sxs-lookup"><span data-stu-id="db527-226">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="db527-227">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="db527-227">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="db527-228">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="db527-228">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="db527-229">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="db527-229">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="db527-230">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="db527-230">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="db527-231">Framework di test</span><span class="sxs-lookup"><span data-stu-id="db527-231">Test Framework</span></span> | <span data-ttu-id="db527-232">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="db527-232">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="db527-233">MSTest</span><span class="sxs-lookup"><span data-stu-id="db527-233">MSTest</span></span>         | <ul><li><span data-ttu-id="db527-234">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="db527-234">FullyQualifiedName</span></span></li><li><span data-ttu-id="db527-235">Nome</span><span class="sxs-lookup"><span data-stu-id="db527-235">Name</span></span></li><li><span data-ttu-id="db527-236">ClassName</span><span class="sxs-lookup"><span data-stu-id="db527-236">ClassName</span></span></li><li><span data-ttu-id="db527-237">Priorità</span><span class="sxs-lookup"><span data-stu-id="db527-237">Priority</span></span></li><li><span data-ttu-id="db527-238">TestCategory</span><span class="sxs-lookup"><span data-stu-id="db527-238">TestCategory</span></span></li></ul> |
| <span data-ttu-id="db527-239">xUnit</span><span class="sxs-lookup"><span data-stu-id="db527-239">xUnit</span></span>          | <ul><li><span data-ttu-id="db527-240">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="db527-240">FullyQualifiedName</span></span></li><li><span data-ttu-id="db527-241">DisplayName</span><span class="sxs-lookup"><span data-stu-id="db527-241">DisplayName</span></span></li><li><span data-ttu-id="db527-242">Tratti</span><span class="sxs-lookup"><span data-stu-id="db527-242">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="db527-243">NUnit</span><span class="sxs-lookup"><span data-stu-id="db527-243">NUnit</span></span>          | <ul><li><span data-ttu-id="db527-244">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="db527-244">FullyQualifiedName</span></span></li><li><span data-ttu-id="db527-245">Nome</span><span class="sxs-lookup"><span data-stu-id="db527-245">Name</span></span></li><li><span data-ttu-id="db527-246">TestCategory</span><span class="sxs-lookup"><span data-stu-id="db527-246">TestCategory</span></span></li><li><span data-ttu-id="db527-247">Priorità</span><span class="sxs-lookup"><span data-stu-id="db527-247">Priority</span></span></li></ul>                                   |

<span data-ttu-id="db527-248">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="db527-248">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="db527-249">Operatore</span><span class="sxs-lookup"><span data-stu-id="db527-249">Operator</span></span> | <span data-ttu-id="db527-250">Funzione</span><span class="sxs-lookup"><span data-stu-id="db527-250">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="db527-251">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="db527-251">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="db527-252">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="db527-252">Not exact match</span></span> |
| `~`      | <span data-ttu-id="db527-253">Contiene</span><span class="sxs-lookup"><span data-stu-id="db527-253">Contains</span></span>        |
| `!~`     | <span data-ttu-id="db527-254">Non contiene</span><span class="sxs-lookup"><span data-stu-id="db527-254">Not contains</span></span>    |

<span data-ttu-id="db527-255">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="db527-255">`<value>` is a string.</span></span> <span data-ttu-id="db527-256">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="db527-256">All the lookups are case insensitive.</span></span>

<span data-ttu-id="db527-257">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="db527-257">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="db527-258">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="db527-258">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="db527-259">Operatore</span><span class="sxs-lookup"><span data-stu-id="db527-259">Operator</span></span>            | <span data-ttu-id="db527-260">Funzione</span><span class="sxs-lookup"><span data-stu-id="db527-260">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="db527-261">O</span><span class="sxs-lookup"><span data-stu-id="db527-261">OR</span></span>       |
| `&`                 | <span data-ttu-id="db527-262">AND</span><span class="sxs-lookup"><span data-stu-id="db527-262">AND</span></span>      |

<span data-ttu-id="db527-263">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="db527-263">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="db527-264">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="db527-264">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db527-265">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db527-265">See also</span></span>

- [<span data-ttu-id="db527-266">Framework e destinazioni</span><span class="sxs-lookup"><span data-stu-id="db527-266">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="db527-267">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="db527-267">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="db527-268">Passaggio di argomenti runsettings tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="db527-268">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
