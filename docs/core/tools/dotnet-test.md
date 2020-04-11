---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 02/27/2020
ms.openlocfilehash: 359e4522b26e2b59092d55eea3fca575d2afaf1f
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121032"
---
# <a name="dotnet-test"></a><span data-ttu-id="1e479-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1e479-103">dotnet test</span></span>

<span data-ttu-id="1e479-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1e479-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1e479-105">Nome</span><span class="sxs-lookup"><span data-stu-id="1e479-105">Name</span></span>

<span data-ttu-id="1e479-106">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="1e479-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1e479-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1e479-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path] [--blame] [-c|--configuration]
    [--collect] [-d|--diag] [-f|--framework] [--filter]
    [--interactive] [-l|--logger] [--no-build] [--nologo]
    [--no-restore] [-o|--output] [-r|--results-directory]
    [--runtime] [-s|--settings] [-t|--list-tests]
    [-v|--verbosity] [[--] <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="1e479-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e479-108">Description</span></span>

<span data-ttu-id="1e479-109">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="1e479-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="1e479-110">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="1e479-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="1e479-111">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="1e479-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="1e479-112">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="1e479-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="1e479-113">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1e479-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="1e479-114">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1e479-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="1e479-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1e479-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="1e479-116">Percorso del progetto o della soluzione di test.</span><span class="sxs-lookup"><span data-stu-id="1e479-116">Path to the test project or solution.</span></span> <span data-ttu-id="1e479-117">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1e479-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="1e479-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1e479-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="1e479-119">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="1e479-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="1e479-120">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="1e479-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="1e479-121">Questa opzione è utile per isolare i test problematici che causano l'arresto anomalo dell'host di test.</span><span class="sxs-lookup"><span data-stu-id="1e479-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="1e479-122">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="1e479-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="1e479-123">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1e479-123">Defines the build configuration.</span></span> <span data-ttu-id="1e479-124">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="1e479-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="1e479-125">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="1e479-125">Enables data collector for the test run.</span></span> <span data-ttu-id="1e479-126">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="1e479-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="1e479-127">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="1e479-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1e479-128">Cerca i file binari di test per un [framework](../../standard/frameworks.md)specifico.</span><span class="sxs-lookup"><span data-stu-id="1e479-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="1e479-129">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="1e479-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="1e479-130">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="1e479-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="1e479-131">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1e479-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="1e479-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1e479-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="1e479-133">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="1e479-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="1e479-134">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1e479-134">For example, to complete authentication.</span></span> <span data-ttu-id="1e479-135">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1e479-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="1e479-136">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="1e479-136">Specifies a logger for test results.</span></span> <span data-ttu-id="1e479-137">A differenza di `-l "console;v=d"` MSBuild, dotnet test non accetta `-l "console;verbosity=detailed"`abbreviazioni: anziché utilizzare .</span><span class="sxs-lookup"><span data-stu-id="1e479-137">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="1e479-138">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1e479-138">Doesn't build the test project before running it.</span></span> <span data-ttu-id="1e479-139">Imposta anche in modo `--no-restore` implicito il - flag.</span><span class="sxs-lookup"><span data-stu-id="1e479-139">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="1e479-140">Eseguire test senza visualizzare il banner Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="1e479-140">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="1e479-141">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="1e479-141">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="1e479-142">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="1e479-142">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="1e479-143">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1e479-143">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="1e479-144">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="1e479-144">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="1e479-145">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="1e479-145">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="1e479-146">Tempo di esecuzione di destinazione per cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="1e479-146">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="1e479-147">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="1e479-147">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="1e479-148">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="1e479-148">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="1e479-149">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="1e479-149">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="1e479-150">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="1e479-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1e479-151">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="1e479-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1e479-152">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="1e479-152">The default is `minimal`.</span></span> <span data-ttu-id="1e479-153">Per altre informazioni, vedere <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="1e479-153">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="1e479-154">`RunSettings`Argomenti</span><span class="sxs-lookup"><span data-stu-id="1e479-154">`RunSettings` arguments</span></span>

  <span data-ttu-id="1e479-155">Gli argomenti `RunSettings` vengono passati come configurazioni per il test.</span><span class="sxs-lookup"><span data-stu-id="1e479-155">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="1e479-156">Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --.</span><span class="sxs-lookup"><span data-stu-id="1e479-156">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="1e479-157">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="1e479-157">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="1e479-158">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="1e479-158">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="1e479-159">Per ulteriori informazioni, vedere [vstest.console.exe: passaggio degli argomenti RunSettings](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="1e479-159">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="1e479-160">Esempi</span><span class="sxs-lookup"><span data-stu-id="1e479-160">Examples</span></span>

- <span data-ttu-id="1e479-161">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1e479-161">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="1e479-162">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="1e479-162">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="1e479-163">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati del test nel formato trx:</span><span class="sxs-lookup"><span data-stu-id="1e479-163">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="1e479-164">Eseguire i test nel progetto nella directory corrente e registrare con livello di dettaglio dettagliato nella console:</span><span class="sxs-lookup"><span data-stu-id="1e479-164">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="1e479-165">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="1e479-165">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="1e479-166">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="1e479-166">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="1e479-167">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="1e479-167">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="1e479-168">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="1e479-168">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="1e479-169">Framework di test</span><span class="sxs-lookup"><span data-stu-id="1e479-169">Test Framework</span></span> | <span data-ttu-id="1e479-170">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="1e479-170">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1e479-171">MSTest</span><span class="sxs-lookup"><span data-stu-id="1e479-171">MSTest</span></span>         | <ul><li><span data-ttu-id="1e479-172">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1e479-172">FullyQualifiedName</span></span></li><li><span data-ttu-id="1e479-173">Nome</span><span class="sxs-lookup"><span data-stu-id="1e479-173">Name</span></span></li><li><span data-ttu-id="1e479-174">ClassName</span><span class="sxs-lookup"><span data-stu-id="1e479-174">ClassName</span></span></li><li><span data-ttu-id="1e479-175">Priorità</span><span class="sxs-lookup"><span data-stu-id="1e479-175">Priority</span></span></li><li><span data-ttu-id="1e479-176">TestCategory</span><span class="sxs-lookup"><span data-stu-id="1e479-176">TestCategory</span></span></li></ul> |
| <span data-ttu-id="1e479-177">xUnit</span><span class="sxs-lookup"><span data-stu-id="1e479-177">xUnit</span></span>          | <ul><li><span data-ttu-id="1e479-178">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1e479-178">FullyQualifiedName</span></span></li><li><span data-ttu-id="1e479-179">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1e479-179">DisplayName</span></span></li><li><span data-ttu-id="1e479-180">Tratti</span><span class="sxs-lookup"><span data-stu-id="1e479-180">Traits</span></span></li></ul>                                   |

<span data-ttu-id="1e479-181">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="1e479-181">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="1e479-182">Operatore</span><span class="sxs-lookup"><span data-stu-id="1e479-182">Operator</span></span> | <span data-ttu-id="1e479-183">Funzione</span><span class="sxs-lookup"><span data-stu-id="1e479-183">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="1e479-184">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="1e479-184">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="1e479-185">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="1e479-185">Not exact match</span></span> |
| `~`      | <span data-ttu-id="1e479-186">Contiene</span><span class="sxs-lookup"><span data-stu-id="1e479-186">Contains</span></span>        |
| `!~`     | <span data-ttu-id="1e479-187">Non contiene</span><span class="sxs-lookup"><span data-stu-id="1e479-187">Not contains</span></span>    |

<span data-ttu-id="1e479-188">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="1e479-188">`<value>` is a string.</span></span> <span data-ttu-id="1e479-189">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="1e479-189">All the lookups are case insensitive.</span></span>

<span data-ttu-id="1e479-190">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="1e479-190">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="1e479-191">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="1e479-191">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="1e479-192">Operatore</span><span class="sxs-lookup"><span data-stu-id="1e479-192">Operator</span></span>            | <span data-ttu-id="1e479-193">Funzione</span><span class="sxs-lookup"><span data-stu-id="1e479-193">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="1e479-194">OR</span><span class="sxs-lookup"><span data-stu-id="1e479-194">OR</span></span>       |
| `&`                 | <span data-ttu-id="1e479-195">AND</span><span class="sxs-lookup"><span data-stu-id="1e479-195">AND</span></span>      |

<span data-ttu-id="1e479-196">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="1e479-196">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="1e479-197">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="1e479-197">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e479-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e479-198">See also</span></span>

- [<span data-ttu-id="1e479-199">Quadri e obiettivi</span><span class="sxs-lookup"><span data-stu-id="1e479-199">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="1e479-200">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="1e479-200">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="1e479-201">Passaggio di argomenti runsettings tramite riga di comandoPassing runsettings arguments through commandline</span><span class="sxs-lookup"><span data-stu-id="1e479-201">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
