---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 02/27/2020
ms.openlocfilehash: 69b8101f9b1052f4726dce8a86234da99f5dc89c
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102743"
---
# <a name="dotnet-test"></a><span data-ttu-id="fb1b0-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fb1b0-103">dotnet test</span></span>

<span data-ttu-id="fb1b0-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="fb1b0-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fb1b0-105">Nome</span><span class="sxs-lookup"><span data-stu-id="fb1b0-105">Name</span></span>

<span data-ttu-id="fb1b0-106">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fb1b0-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fb1b0-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="fb1b0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb1b0-108">Description</span></span>

<span data-ttu-id="fb1b0-109">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="fb1b0-110">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="fb1b0-111">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="fb1b0-112">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="fb1b0-113">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="fb1b0-114">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a><span data-ttu-id="fb1b0-115">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="fb1b0-115">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="fb1b0-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fb1b0-116">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="fb1b0-117">Percorso del progetto o della soluzione di test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-117">Path to the test project or solution.</span></span> <span data-ttu-id="fb1b0-118">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="fb1b0-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fb1b0-119">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="fb1b0-120">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-120">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="fb1b0-121">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-121">Runs the tests in blame mode.</span></span> <span data-ttu-id="fb1b0-122">Questa opzione è utile per isolare i test problematici che causano l'arresto anomalo dell'host di test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-122">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="fb1b0-123">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-123">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="fb1b0-124">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-124">Defines the build configuration.</span></span> <span data-ttu-id="fb1b0-125">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-125">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="fb1b0-126">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-126">Enables data collector for the test run.</span></span> <span data-ttu-id="fb1b0-127">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="fb1b0-127">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="fb1b0-128">Abilita la modalità diagnostica per la piattaforma di test e scrive i messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-128">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fb1b0-129">Cerca i file binari di test per un [framework](../../standard/frameworks.md)specifico.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-129">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="fb1b0-130">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-130">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="fb1b0-131">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="fb1b0-131">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="fb1b0-132">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="fb1b0-132">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="fb1b0-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-133">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="fb1b0-134">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="fb1b0-134">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="fb1b0-135">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-135">For example, to complete authentication.</span></span> <span data-ttu-id="fb1b0-136">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-136">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="fb1b0-137">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-137">Specifies a logger for test results.</span></span> <span data-ttu-id="fb1b0-138">A differenza di `-l "console;v=d"` MSBuild, dotnet test non accetta `-l "console;verbosity=detailed"`abbreviazioni: anziché utilizzare .</span><span class="sxs-lookup"><span data-stu-id="fb1b0-138">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="fb1b0-139">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-139">Doesn't build the test project before running it.</span></span> <span data-ttu-id="fb1b0-140">Imposta anche in modo `--no-restore` implicito il - flag.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-140">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="fb1b0-141">Eseguire test senza visualizzare il banner Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-141">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="fb1b0-142">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-142">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="fb1b0-143">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-143">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="fb1b0-144">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-144">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="fb1b0-145">Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-145">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="fb1b0-146">Per i progetti con più `TargetFrameworks` framework di destinazione (tramite la proprietà), è inoltre necessario definire `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-146">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="fb1b0-147">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-147">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="fb1b0-148">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-148">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="fb1b0-149">Il valore `TestResults` predefinito si trova nella directory che contiene il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-149">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="fb1b0-150">Tempo di esecuzione di destinazione per cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-150">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="fb1b0-151">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-151">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="fb1b0-152">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-152">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="fb1b0-153">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-153">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="fb1b0-154">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-154">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fb1b0-155">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-155">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fb1b0-156">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-156">The default is `minimal`.</span></span> <span data-ttu-id="fb1b0-157">Per altre informazioni, vedere <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-157">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="fb1b0-158">**`RunSettings`** Argomenti</span><span class="sxs-lookup"><span data-stu-id="fb1b0-158">**`RunSettings`** arguments</span></span>

  <span data-ttu-id="fb1b0-159">Gli argomenti `RunSettings` vengono passati come configurazioni per il test.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-159">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="fb1b0-160">Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-160">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="fb1b0-161">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-161">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="fb1b0-162">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="fb1b0-162">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="fb1b0-163">Per ulteriori informazioni, vedere [Passaggio di argomenti RunSettings tramite riga di comando](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="fb1b0-163">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="fb1b0-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="fb1b0-164">Examples</span></span>

- <span data-ttu-id="fb1b0-165">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-165">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="fb1b0-166">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-166">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="fb1b0-167">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati del test nel formato trx:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-167">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="fb1b0-168">Eseguire i test nel progetto nella directory corrente e registrare con livello di dettaglio dettagliato nella console:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-168">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="fb1b0-169">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="fb1b0-169">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="fb1b0-170">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-170">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="fb1b0-171">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-171">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="fb1b0-172">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-172">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="fb1b0-173">Framework di test</span><span class="sxs-lookup"><span data-stu-id="fb1b0-173">Test Framework</span></span> | <span data-ttu-id="fb1b0-174">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="fb1b0-174">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="fb1b0-175">MSTest</span><span class="sxs-lookup"><span data-stu-id="fb1b0-175">MSTest</span></span>         | <ul><li><span data-ttu-id="fb1b0-176">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="fb1b0-176">FullyQualifiedName</span></span></li><li><span data-ttu-id="fb1b0-177">Nome</span><span class="sxs-lookup"><span data-stu-id="fb1b0-177">Name</span></span></li><li><span data-ttu-id="fb1b0-178">ClassName</span><span class="sxs-lookup"><span data-stu-id="fb1b0-178">ClassName</span></span></li><li><span data-ttu-id="fb1b0-179">Priorità</span><span class="sxs-lookup"><span data-stu-id="fb1b0-179">Priority</span></span></li><li><span data-ttu-id="fb1b0-180">TestCategory</span><span class="sxs-lookup"><span data-stu-id="fb1b0-180">TestCategory</span></span></li></ul> |
| <span data-ttu-id="fb1b0-181">xUnit</span><span class="sxs-lookup"><span data-stu-id="fb1b0-181">xUnit</span></span>          | <ul><li><span data-ttu-id="fb1b0-182">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="fb1b0-182">FullyQualifiedName</span></span></li><li><span data-ttu-id="fb1b0-183">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fb1b0-183">DisplayName</span></span></li><li><span data-ttu-id="fb1b0-184">Tratti</span><span class="sxs-lookup"><span data-stu-id="fb1b0-184">Traits</span></span></li></ul>                                   |

<span data-ttu-id="fb1b0-185">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-185">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="fb1b0-186">Operatore</span><span class="sxs-lookup"><span data-stu-id="fb1b0-186">Operator</span></span> | <span data-ttu-id="fb1b0-187">Funzione</span><span class="sxs-lookup"><span data-stu-id="fb1b0-187">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="fb1b0-188">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="fb1b0-188">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="fb1b0-189">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="fb1b0-189">Not exact match</span></span> |
| `~`      | <span data-ttu-id="fb1b0-190">Contiene</span><span class="sxs-lookup"><span data-stu-id="fb1b0-190">Contains</span></span>        |
| `!~`     | <span data-ttu-id="fb1b0-191">Non contiene</span><span class="sxs-lookup"><span data-stu-id="fb1b0-191">Not contains</span></span>    |

<span data-ttu-id="fb1b0-192">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-192">`<value>` is a string.</span></span> <span data-ttu-id="fb1b0-193">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-193">All the lookups are case insensitive.</span></span>

<span data-ttu-id="fb1b0-194">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="fb1b0-194">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="fb1b0-195">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="fb1b0-195">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="fb1b0-196">Operatore</span><span class="sxs-lookup"><span data-stu-id="fb1b0-196">Operator</span></span>            | <span data-ttu-id="fb1b0-197">Funzione</span><span class="sxs-lookup"><span data-stu-id="fb1b0-197">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="fb1b0-198">OR</span><span class="sxs-lookup"><span data-stu-id="fb1b0-198">OR</span></span>       |
| `&`                 | <span data-ttu-id="fb1b0-199">AND</span><span class="sxs-lookup"><span data-stu-id="fb1b0-199">AND</span></span>      |

<span data-ttu-id="fb1b0-200">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="fb1b0-200">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="fb1b0-201">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="fb1b0-201">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb1b0-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb1b0-202">See also</span></span>

- [<span data-ttu-id="fb1b0-203">Quadri e obiettivi</span><span class="sxs-lookup"><span data-stu-id="fb1b0-203">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="fb1b0-204">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="fb1b0-204">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="fb1b0-205">Passaggio di argomenti runsettings tramite riga di comandoPassing runsettings arguments through commandline</span><span class="sxs-lookup"><span data-stu-id="fb1b0-205">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
