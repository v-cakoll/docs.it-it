---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624891"
---
# <a name="dotnet-test"></a><span data-ttu-id="1f763-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1f763-103">dotnet test</span></span>

<span data-ttu-id="1f763-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1f763-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1f763-105">Nome</span><span class="sxs-lookup"><span data-stu-id="1f763-105">Name</span></span>

<span data-ttu-id="1f763-106">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="1f763-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1f763-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1f763-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="1f763-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f763-108">Description</span></span>

<span data-ttu-id="1f763-109">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="1f763-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="1f763-110">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="1f763-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="1f763-111">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="1f763-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="1f763-112">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="1f763-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="1f763-113">Per i progetti multitargeting, i test vengono eseguiti per ogni Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1f763-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="1f763-114">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1f763-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="1f763-115">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1f763-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a><span data-ttu-id="1f763-116">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="1f763-116">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="1f763-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1f763-117">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="1f763-118">Percorso del progetto o della soluzione di test.</span><span class="sxs-lookup"><span data-stu-id="1f763-118">Path to the test project or solution.</span></span> <span data-ttu-id="1f763-119">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1f763-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="1f763-120">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1f763-120">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="1f763-121">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="1f763-121">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="1f763-122">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="1f763-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="1f763-123">Questa opzione è utile per isolare i test problematici che provocano l'arresto anomalo dell'host di test.</span><span class="sxs-lookup"><span data-stu-id="1f763-123">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="1f763-124">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="1f763-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="1f763-125">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1f763-125">Defines the build configuration.</span></span> <span data-ttu-id="1f763-126">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="1f763-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="1f763-127">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="1f763-127">Enables data collector for the test run.</span></span> <span data-ttu-id="1f763-128">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="1f763-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="1f763-129">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="1f763-129">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1f763-130">Cerca i file binari di test per un [Framework](../../standard/frameworks.md)specifico.</span><span class="sxs-lookup"><span data-stu-id="1f763-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="1f763-131">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="1f763-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1f763-132">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="1f763-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1f763-133">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1f763-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="1f763-134">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1f763-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="1f763-135">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="1f763-135">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="1f763-136">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1f763-136">For example, to complete authentication.</span></span> <span data-ttu-id="1f763-137">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1f763-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="1f763-138">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="1f763-138">Specifies a logger for test results.</span></span> <span data-ttu-id="1f763-139">Diversamente da MSBuild, il test DotNet non accetta abbreviazioni: invece `-l "console;v=d"` di `-l "console;verbosity=detailed"`usare.</span><span class="sxs-lookup"><span data-stu-id="1f763-139">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="1f763-140">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1f763-140">Doesn't build the test project before running it.</span></span> <span data-ttu-id="1f763-141">Viene inoltre impostato in modo implicito `--no-restore` il flag-.</span><span class="sxs-lookup"><span data-stu-id="1f763-141">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="1f763-142">Esegui test senza visualizzare il banner Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="1f763-142">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="1f763-143">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1f763-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1f763-144">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="1f763-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="1f763-145">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1f763-145">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="1f763-146">Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="1f763-146">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="1f763-147">Per i progetti con più framework di destinazione (tramite `TargetFrameworks` la proprietà), è necessario definire `--framework` anche quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1f763-147">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="1f763-148">`dotnet test`eseguire sempre i test dalla directory di output.</span><span class="sxs-lookup"><span data-stu-id="1f763-148">`dotnet test` always run tests from the output directory.</span></span> <span data-ttu-id="1f763-149">È possibile usare <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> per utilizzare gli asset di test nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="1f763-149">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="1f763-150">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="1f763-150">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="1f763-151">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="1f763-151">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="1f763-152">Il valore predefinito `TestResults` è la directory che contiene il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1f763-152">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="1f763-153">Runtime di destinazione di cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="1f763-153">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="1f763-154">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="1f763-154">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="1f763-155">Si noti che `TargetPlatform` l'elemento (x86 | x64) non ha alcun `dotnet test`effetto per.</span><span class="sxs-lookup"><span data-stu-id="1f763-155">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="1f763-156">Per eseguire test destinati a x86, installare la versione x86 di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1f763-156">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="1f763-157">Il bit di *dotnet. exe* che si trova nel percorso è quello che verrà usato per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="1f763-157">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="1f763-158">Per ulteriori informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f763-158">for more information, see the following resources:</span></span>

  - [<span data-ttu-id="1f763-159">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="1f763-159">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="1f763-160">Configurare un agente di test</span><span class="sxs-lookup"><span data-stu-id="1f763-160">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="1f763-161">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="1f763-161">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="1f763-162">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="1f763-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1f763-163">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1f763-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1f763-164">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="1f763-164">The default is `minimal`.</span></span> <span data-ttu-id="1f763-165">Per altre informazioni, vedere <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="1f763-165">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="1f763-166">**`RunSettings`** argomenti</span><span class="sxs-lookup"><span data-stu-id="1f763-166">**`RunSettings`** arguments</span></span>

  <span data-ttu-id="1f763-167">Gli argomenti vengono passati `RunSettings` come configurazioni per il test.</span><span class="sxs-lookup"><span data-stu-id="1f763-167">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="1f763-168">Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --.</span><span class="sxs-lookup"><span data-stu-id="1f763-168">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="1f763-169">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="1f763-169">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="1f763-170">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="1f763-170">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="1f763-171">Per ulteriori informazioni, vedere [passaggio di argomenti runsettings tramite la riga di comando](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="1f763-171">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="1f763-172">Esempi</span><span class="sxs-lookup"><span data-stu-id="1f763-172">Examples</span></span>

- <span data-ttu-id="1f763-173">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1f763-173">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="1f763-174">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="1f763-174">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="1f763-175">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati del test nel formato TRX:</span><span class="sxs-lookup"><span data-stu-id="1f763-175">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="1f763-176">Eseguire i test nel progetto nella directory corrente e accedere con un livello di dettaglio dettagliato alla console:</span><span class="sxs-lookup"><span data-stu-id="1f763-176">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="1f763-177">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="1f763-177">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1f763-178">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="1f763-178">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="1f763-179">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="1f763-179">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="1f763-180">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="1f763-180">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="1f763-181">Framework di test</span><span class="sxs-lookup"><span data-stu-id="1f763-181">Test Framework</span></span> | <span data-ttu-id="1f763-182">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="1f763-182">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1f763-183">MSTest</span><span class="sxs-lookup"><span data-stu-id="1f763-183">MSTest</span></span>         | <ul><li><span data-ttu-id="1f763-184">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1f763-184">FullyQualifiedName</span></span></li><li><span data-ttu-id="1f763-185">Nome</span><span class="sxs-lookup"><span data-stu-id="1f763-185">Name</span></span></li><li><span data-ttu-id="1f763-186">ClassName</span><span class="sxs-lookup"><span data-stu-id="1f763-186">ClassName</span></span></li><li><span data-ttu-id="1f763-187">Priorità</span><span class="sxs-lookup"><span data-stu-id="1f763-187">Priority</span></span></li><li><span data-ttu-id="1f763-188">TestCategory</span><span class="sxs-lookup"><span data-stu-id="1f763-188">TestCategory</span></span></li></ul> |
| <span data-ttu-id="1f763-189">xUnit</span><span class="sxs-lookup"><span data-stu-id="1f763-189">xUnit</span></span>          | <ul><li><span data-ttu-id="1f763-190">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1f763-190">FullyQualifiedName</span></span></li><li><span data-ttu-id="1f763-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1f763-191">DisplayName</span></span></li><li><span data-ttu-id="1f763-192">Tratti</span><span class="sxs-lookup"><span data-stu-id="1f763-192">Traits</span></span></li></ul>                                   |

<span data-ttu-id="1f763-193">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="1f763-193">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="1f763-194">Operatore</span><span class="sxs-lookup"><span data-stu-id="1f763-194">Operator</span></span> | <span data-ttu-id="1f763-195">Funzione</span><span class="sxs-lookup"><span data-stu-id="1f763-195">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="1f763-196">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="1f763-196">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="1f763-197">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="1f763-197">Not exact match</span></span> |
| `~`      | <span data-ttu-id="1f763-198">Contiene</span><span class="sxs-lookup"><span data-stu-id="1f763-198">Contains</span></span>        |
| `!~`     | <span data-ttu-id="1f763-199">Non contiene</span><span class="sxs-lookup"><span data-stu-id="1f763-199">Not contains</span></span>    |

<span data-ttu-id="1f763-200">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="1f763-200">`<value>` is a string.</span></span> <span data-ttu-id="1f763-201">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="1f763-201">All the lookups are case insensitive.</span></span>

<span data-ttu-id="1f763-202">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="1f763-202">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="1f763-203">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="1f763-203">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="1f763-204">Operatore</span><span class="sxs-lookup"><span data-stu-id="1f763-204">Operator</span></span>            | <span data-ttu-id="1f763-205">Funzione</span><span class="sxs-lookup"><span data-stu-id="1f763-205">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="1f763-206">OR</span><span class="sxs-lookup"><span data-stu-id="1f763-206">OR</span></span>       |
| `&`                 | <span data-ttu-id="1f763-207">AND</span><span class="sxs-lookup"><span data-stu-id="1f763-207">AND</span></span>      |

<span data-ttu-id="1f763-208">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="1f763-208">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="1f763-209">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1f763-209">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1f763-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f763-210">See also</span></span>

- [<span data-ttu-id="1f763-211">Framework e destinazioni</span><span class="sxs-lookup"><span data-stu-id="1f763-211">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="1f763-212">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1f763-212">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="1f763-213">Passaggio di argomenti runsettings tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="1f763-213">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
