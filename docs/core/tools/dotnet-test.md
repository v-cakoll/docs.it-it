---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 02/27/2020
ms.openlocfilehash: bac2f0e613c34bc9f657551a5eac4038207a93ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847898"
---
# <a name="dotnet-test"></a><span data-ttu-id="75f0a-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="75f0a-103">dotnet test</span></span>

<span data-ttu-id="75f0a-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="75f0a-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="75f0a-105">Nome</span><span class="sxs-lookup"><span data-stu-id="75f0a-105">Name</span></span>

<span data-ttu-id="75f0a-106">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="75f0a-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="75f0a-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="75f0a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f0a-108">Description</span></span>

<span data-ttu-id="75f0a-109">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="75f0a-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="75f0a-110">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="75f0a-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="75f0a-111">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="75f0a-112">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="75f0a-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="75f0a-113">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="75f0a-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="75f0a-114">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="75f0a-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="75f0a-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="75f0a-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="75f0a-116">Percorso del progetto o della soluzione di test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-116">Path to the test project or solution.</span></span> <span data-ttu-id="75f0a-117">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="75f0a-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="75f0a-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="75f0a-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="75f0a-119">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`-blame`**

  <span data-ttu-id="75f0a-120">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="75f0a-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="75f0a-121">Questa opzione è utile per isolare i test problematici che causano l'arresto anomalo dell'host di test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="75f0a-122">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="75f0a-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="75f0a-123">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="75f0a-123">Defines the build configuration.</span></span> <span data-ttu-id="75f0a-124">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="75f0a-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="75f0a-125">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-125">Enables data collector for the test run.</span></span> <span data-ttu-id="75f0a-126">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="75f0a-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="75f0a-127">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="75f0a-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="75f0a-128">Cerca i file binari di test per un [framework](../../standard/frameworks.md)specifico.</span><span class="sxs-lookup"><span data-stu-id="75f0a-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="75f0a-129">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="75f0a-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="75f0a-130">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="75f0a-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="75f0a-131">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="75f0a-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="75f0a-132">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="75f0a-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="75f0a-133">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="75f0a-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="75f0a-134">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="75f0a-134">For example, to complete authentication.</span></span> <span data-ttu-id="75f0a-135">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="75f0a-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="75f0a-136">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-136">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="75f0a-137">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="75f0a-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="75f0a-138">Imposta anche in modo `--no-restore` implicito il - flag.</span><span class="sxs-lookup"><span data-stu-id="75f0a-138">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="75f0a-139">Eseguire test senza visualizzare il banner Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="75f0a-139">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="75f0a-140">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="75f0a-140">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="75f0a-141">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="75f0a-141">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="75f0a-142">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="75f0a-142">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="75f0a-143">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-143">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="75f0a-144">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="75f0a-144">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="75f0a-145">Tempo di esecuzione di destinazione per cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-145">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="75f0a-146">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-146">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="75f0a-147">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="75f0a-147">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="75f0a-148">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="75f0a-148">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="75f0a-149">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="75f0a-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="75f0a-150">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="75f0a-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="75f0a-151">`RunSettings`Argomenti</span><span class="sxs-lookup"><span data-stu-id="75f0a-151">`RunSettings` arguments</span></span>

  <span data-ttu-id="75f0a-152">Gli argomenti `RunSettings` vengono passati come configurazioni per il test.</span><span class="sxs-lookup"><span data-stu-id="75f0a-152">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="75f0a-153">Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --.</span><span class="sxs-lookup"><span data-stu-id="75f0a-153">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="75f0a-154">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="75f0a-154">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="75f0a-155">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="75f0a-155">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="75f0a-156">Per ulteriori informazioni, vedere [vstest.console.exe: passaggio degli argomenti RunSettings](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="75f0a-156">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="75f0a-157">Esempi</span><span class="sxs-lookup"><span data-stu-id="75f0a-157">Examples</span></span>

- <span data-ttu-id="75f0a-158">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="75f0a-158">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="75f0a-159">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="75f0a-159">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="75f0a-160">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati di test in formato trx:</span><span class="sxs-lookup"><span data-stu-id="75f0a-160">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="75f0a-161">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="75f0a-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="75f0a-162">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="75f0a-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="75f0a-163">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="75f0a-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="75f0a-164">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="75f0a-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="75f0a-165">Framework di test</span><span class="sxs-lookup"><span data-stu-id="75f0a-165">Test Framework</span></span> | <span data-ttu-id="75f0a-166">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="75f0a-166">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="75f0a-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="75f0a-167">MSTest</span></span>         | <ul><li><span data-ttu-id="75f0a-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="75f0a-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="75f0a-169">Nome</span><span class="sxs-lookup"><span data-stu-id="75f0a-169">Name</span></span></li><li><span data-ttu-id="75f0a-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="75f0a-170">ClassName</span></span></li><li><span data-ttu-id="75f0a-171">Priorità</span><span class="sxs-lookup"><span data-stu-id="75f0a-171">Priority</span></span></li><li><span data-ttu-id="75f0a-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="75f0a-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="75f0a-173">xUnit</span><span class="sxs-lookup"><span data-stu-id="75f0a-173">xUnit</span></span>          | <ul><li><span data-ttu-id="75f0a-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="75f0a-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="75f0a-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="75f0a-175">DisplayName</span></span></li><li><span data-ttu-id="75f0a-176">Tratti</span><span class="sxs-lookup"><span data-stu-id="75f0a-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="75f0a-177">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="75f0a-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="75f0a-178">Operatore</span><span class="sxs-lookup"><span data-stu-id="75f0a-178">Operator</span></span> | <span data-ttu-id="75f0a-179">Funzione</span><span class="sxs-lookup"><span data-stu-id="75f0a-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="75f0a-180">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="75f0a-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="75f0a-181">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="75f0a-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="75f0a-182">Contiene</span><span class="sxs-lookup"><span data-stu-id="75f0a-182">Contains</span></span>        |
| `!~`     | <span data-ttu-id="75f0a-183">Non contiene</span><span class="sxs-lookup"><span data-stu-id="75f0a-183">Not contains</span></span>    |

<span data-ttu-id="75f0a-184">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="75f0a-184">`<value>` is a string.</span></span> <span data-ttu-id="75f0a-185">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="75f0a-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="75f0a-186">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="75f0a-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="75f0a-187">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="75f0a-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="75f0a-188">Operatore</span><span class="sxs-lookup"><span data-stu-id="75f0a-188">Operator</span></span>            | <span data-ttu-id="75f0a-189">Funzione</span><span class="sxs-lookup"><span data-stu-id="75f0a-189">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="75f0a-190">o</span><span class="sxs-lookup"><span data-stu-id="75f0a-190">OR</span></span>       |
| `&`                 | <span data-ttu-id="75f0a-191">AND</span><span class="sxs-lookup"><span data-stu-id="75f0a-191">AND</span></span>      |

<span data-ttu-id="75f0a-192">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="75f0a-192">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="75f0a-193">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="75f0a-193">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75f0a-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f0a-194">See also</span></span>

- [<span data-ttu-id="75f0a-195">Quadri e obiettivi</span><span class="sxs-lookup"><span data-stu-id="75f0a-195">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="75f0a-196">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="75f0a-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
