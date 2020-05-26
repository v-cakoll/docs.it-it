---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 04/29/2020
ms.openlocfilehash: 22b27007d26c98cff40733ef8d449ce334f87848
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802684"
---
# <a name="dotnet-test"></a><span data-ttu-id="95d6f-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="95d6f-103">dotnet test</span></span>

<span data-ttu-id="95d6f-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="95d6f-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="95d6f-105">Nome</span><span class="sxs-lookup"><span data-stu-id="95d6f-105">Name</span></span>

<span data-ttu-id="95d6f-106">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="95d6f-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="95d6f-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
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

## <a name="description"></a><span data-ttu-id="95d6f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95d6f-108">Description</span></span>

<span data-ttu-id="95d6f-109">Il `dotnet test` comando viene usato per eseguire unit test in una determinata soluzione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="95d6f-110">Il `dotnet test` comando Compila la soluzione ed esegue un'applicazione host di test per ogni progetto di test nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="95d6f-111">L'host di test esegue i test nel progetto specificato utilizzando un Framework di test, ad esempio MSTest, NUnit o xUnit, e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="95d6f-112">Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="95d6f-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="95d6f-113">Per i progetti multitargeting, i test vengono eseguiti per ogni Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="95d6f-114">L'host di test e il framework unit test vengono inclusi nel pacchetto come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="95d6f-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="95d6f-115">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="95d6f-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="95d6f-116">Dove `Microsoft.NET.Test.Sdk` è l'host di test, `xunit` è il Framework di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="95d6f-117">E `xunit.runner.visualstudio` è un adattatore di test, che consente al Framework xUnit di funzionare con l'host di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="95d6f-118">Ripristino implicito</span><span class="sxs-lookup"><span data-stu-id="95d6f-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="95d6f-119">Argomenti</span><span class="sxs-lookup"><span data-stu-id="95d6f-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="95d6f-120">Percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-120">Path to the test project.</span></span>
  - <span data-ttu-id="95d6f-121">Percorso della soluzione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-121">Path to the solution.</span></span>
  - <span data-ttu-id="95d6f-122">Percorso di una directory che contiene un progetto o una soluzione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="95d6f-123">Percorso di un file con estensione *dll* del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="95d6f-124">Se non specificato, Cerca un progetto o una soluzione nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="95d6f-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="95d6f-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="95d6f-125">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="95d6f-126">Percorso di una directory in cui eseguire la ricerca di altri adattatori di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="95d6f-127">Vengono controllati solo i file con *estensione dll* con suffisso `.TestAdapter.dll` .</span><span class="sxs-lookup"><span data-stu-id="95d6f-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="95d6f-128">Se non specificato, viene eseguita una ricerca nella directory della *dll* test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="95d6f-129">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="95d6f-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="95d6f-130">Questa opzione è utile per isolare i test problematici che provocano l'arresto anomalo dell'host di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="95d6f-131">Quando viene rilevato un arresto anomalo del sistema, viene creato un file di sequenza in `TestResults/<Guid>/<Guid>_Sequence.xml` che acquisisce l'ordine dei test eseguiti prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="95d6f-131">When a crash is detected, it creates an sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="95d6f-132">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-132">Defines the build configuration.</span></span> <span data-ttu-id="95d6f-133">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="95d6f-133">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="95d6f-134">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-134">Enables data collector for the test run.</span></span> <span data-ttu-id="95d6f-135">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="95d6f-135">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="95d6f-136">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato e nei file accanto.</span><span class="sxs-lookup"><span data-stu-id="95d6f-136">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="95d6f-137">Il processo che registra i messaggi determina quali file vengono creati, ad esempio `*.host_<date>.txt` per il log dell'host di test e `*.datacollector_<date>.txt` per il log dell'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="95d6f-137">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="95d6f-138">Impone l'uso di `dotnet` o .NET Framework host di test per i file binari del test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-138">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="95d6f-139">Questa opzione determina solo il tipo di host da usare.</span><span class="sxs-lookup"><span data-stu-id="95d6f-139">This option only determines which type of host to use.</span></span> <span data-ttu-id="95d6f-140">La versione effettiva del Framework da usare è determinata da *runtimeconfig. JSON* del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-140">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="95d6f-141">Quando non è specificato, viene usato l' [attributo dell'assembly TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute) per determinare il tipo di host.</span><span class="sxs-lookup"><span data-stu-id="95d6f-141">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="95d6f-142">Quando tale attributo viene rimosso dal file con *estensione dll*, viene utilizzato l'host .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95d6f-142">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="95d6f-143">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="95d6f-143">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="95d6f-144">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="95d6f-144">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="95d6f-145">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="95d6f-145">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="95d6f-146">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="95d6f-146">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="95d6f-147">Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente,</span><span class="sxs-lookup"><span data-stu-id="95d6f-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="95d6f-148">ad esempio il completamento dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-148">For example, to complete authentication.</span></span> <span data-ttu-id="95d6f-149">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="95d6f-149">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="95d6f-150">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-150">Specifies a logger for test results.</span></span> <span data-ttu-id="95d6f-151">Diversamente da MSBuild, il test DotNet non accetta abbreviazioni: invece di `-l "console;v=d"` usare `-l "console;verbosity=detailed"` .</span><span class="sxs-lookup"><span data-stu-id="95d6f-151">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="95d6f-152">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-152">Doesn't build the test project before running it.</span></span> <span data-ttu-id="95d6f-153">Viene inoltre impostato in modo implicito il `--no-restore` flag-.</span><span class="sxs-lookup"><span data-stu-id="95d6f-153">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="95d6f-154">Esegui test senza visualizzare il banner Microsoft TestPlatform.</span><span class="sxs-lookup"><span data-stu-id="95d6f-154">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="95d6f-155">Disponibile a partire da .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="95d6f-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="95d6f-156">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="95d6f-156">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="95d6f-157">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="95d6f-157">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="95d6f-158">Se non specificata, il percorso predefinito è `./bin/<configuration>/<framework>/`.</span><span class="sxs-lookup"><span data-stu-id="95d6f-158">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="95d6f-159">Per i progetti con più framework di destinazione (tramite la `TargetFrameworks` proprietà), è necessario definire anche `--framework` quando si specifica questa opzione.</span><span class="sxs-lookup"><span data-stu-id="95d6f-159">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="95d6f-160">`dotnet test`esegue sempre i test dalla directory di output.</span><span class="sxs-lookup"><span data-stu-id="95d6f-160">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="95d6f-161">È possibile usare <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> per utilizzare gli asset di test nella directory di output.</span><span class="sxs-lookup"><span data-stu-id="95d6f-161">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="95d6f-162">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-162">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="95d6f-163">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="95d6f-163">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="95d6f-164">Il valore predefinito è `TestResults` la directory che contiene il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="95d6f-164">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="95d6f-165">Runtime di destinazione di cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-165">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="95d6f-166">Il file `.runsettings` da usare per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-166">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="95d6f-167">Si noti che l' `TargetPlatform` elemento (x86 | x64) non ha alcun effetto per `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="95d6f-167">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="95d6f-168">Per eseguire test destinati a x86, installare la versione x86 di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95d6f-168">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="95d6f-169">Il bit di *dotnet. exe* che si trova nel percorso è quello che verrà usato per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="95d6f-169">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="95d6f-170">Per altre informazioni, vedere le seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="95d6f-170">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="95d6f-171">Configurare unit test usando un file `.runsettings`.</span><span class="sxs-lookup"><span data-stu-id="95d6f-171">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="95d6f-172">Configurare un agente di test</span><span class="sxs-lookup"><span data-stu-id="95d6f-172">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="95d6f-173">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="95d6f-173">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="95d6f-174">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="95d6f-174">Sets the verbosity level of the command.</span></span> <span data-ttu-id="95d6f-175">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="95d6f-175">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="95d6f-176">Il valore predefinito è `minimal`.</span><span class="sxs-lookup"><span data-stu-id="95d6f-176">The default is `minimal`.</span></span> <span data-ttu-id="95d6f-177">Per altre informazioni, vedere <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span><span class="sxs-lookup"><span data-stu-id="95d6f-177">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="95d6f-178">**`RunSettings`** argomenti</span><span class="sxs-lookup"><span data-stu-id="95d6f-178">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="95d6f-179">Inline `RunSettings` vengono passati come ultimi argomenti nella riga di comando dopo "--" (si noti lo spazio dopo--).</span><span class="sxs-lookup"><span data-stu-id="95d6f-179">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="95d6f-180">Inline `RunSettings` sono specificati come `[name]=[value]` coppie.</span><span class="sxs-lookup"><span data-stu-id="95d6f-180">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="95d6f-181">Per separare più coppie `[name]=[value]`, viene usato uno spazio.</span><span class="sxs-lookup"><span data-stu-id="95d6f-181">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="95d6f-182">Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="95d6f-182">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="95d6f-183">Per ulteriori informazioni, vedere [passaggio di argomenti runsettings tramite la riga di comando](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span><span class="sxs-lookup"><span data-stu-id="95d6f-183">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="95d6f-184">Esempi</span><span class="sxs-lookup"><span data-stu-id="95d6f-184">Examples</span></span>

- <span data-ttu-id="95d6f-185">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="95d6f-185">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="95d6f-186">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="95d6f-186">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="95d6f-187">Eseguire i test nel progetto nella directory corrente e generare un file dei risultati del test nel formato TRX:</span><span class="sxs-lookup"><span data-stu-id="95d6f-187">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="95d6f-188">Eseguire i test nel progetto nella directory corrente e accedere con un livello di dettaglio dettagliato alla console:</span><span class="sxs-lookup"><span data-stu-id="95d6f-188">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - <span data-ttu-id="95d6f-189">Eseguire i test nel progetto nella directory corrente e segnalare i test in corso quando l'host di test si è arrestato in modo anomalo:</span><span class="sxs-lookup"><span data-stu-id="95d6f-189">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="95d6f-190">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="95d6f-190">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="95d6f-191">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="95d6f-191">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="95d6f-192">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="95d6f-192">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="95d6f-193">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="95d6f-193">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="95d6f-194">Framework di test</span><span class="sxs-lookup"><span data-stu-id="95d6f-194">Test Framework</span></span> | <span data-ttu-id="95d6f-195">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="95d6f-195">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="95d6f-196">MSTest</span><span class="sxs-lookup"><span data-stu-id="95d6f-196">MSTest</span></span>         | <ul><li><span data-ttu-id="95d6f-197">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="95d6f-197">FullyQualifiedName</span></span></li><li><span data-ttu-id="95d6f-198">Nome</span><span class="sxs-lookup"><span data-stu-id="95d6f-198">Name</span></span></li><li><span data-ttu-id="95d6f-199">ClassName</span><span class="sxs-lookup"><span data-stu-id="95d6f-199">ClassName</span></span></li><li><span data-ttu-id="95d6f-200">Priorità</span><span class="sxs-lookup"><span data-stu-id="95d6f-200">Priority</span></span></li><li><span data-ttu-id="95d6f-201">TestCategory</span><span class="sxs-lookup"><span data-stu-id="95d6f-201">TestCategory</span></span></li></ul> |
| <span data-ttu-id="95d6f-202">xUnit</span><span class="sxs-lookup"><span data-stu-id="95d6f-202">xUnit</span></span>          | <ul><li><span data-ttu-id="95d6f-203">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="95d6f-203">FullyQualifiedName</span></span></li><li><span data-ttu-id="95d6f-204">DisplayName</span><span class="sxs-lookup"><span data-stu-id="95d6f-204">DisplayName</span></span></li><li><span data-ttu-id="95d6f-205">Tratti</span><span class="sxs-lookup"><span data-stu-id="95d6f-205">Traits</span></span></li></ul>                                   |

<span data-ttu-id="95d6f-206">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="95d6f-206">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="95d6f-207">Operatore</span><span class="sxs-lookup"><span data-stu-id="95d6f-207">Operator</span></span> | <span data-ttu-id="95d6f-208">Funzione</span><span class="sxs-lookup"><span data-stu-id="95d6f-208">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="95d6f-209">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="95d6f-209">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="95d6f-210">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="95d6f-210">Not exact match</span></span> |
| `~`      | <span data-ttu-id="95d6f-211">Contiene</span><span class="sxs-lookup"><span data-stu-id="95d6f-211">Contains</span></span>        |
| `!~`     | <span data-ttu-id="95d6f-212">Non contiene</span><span class="sxs-lookup"><span data-stu-id="95d6f-212">Not contains</span></span>    |

<span data-ttu-id="95d6f-213">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="95d6f-213">`<value>` is a string.</span></span> <span data-ttu-id="95d6f-214">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="95d6f-214">All the lookups are case insensitive.</span></span>

<span data-ttu-id="95d6f-215">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="95d6f-215">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="95d6f-216">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="95d6f-216">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="95d6f-217">Operatore</span><span class="sxs-lookup"><span data-stu-id="95d6f-217">Operator</span></span>            | <span data-ttu-id="95d6f-218">Funzione</span><span class="sxs-lookup"><span data-stu-id="95d6f-218">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="95d6f-219">OR</span><span class="sxs-lookup"><span data-stu-id="95d6f-219">OR</span></span>       |
| `&`                 | <span data-ttu-id="95d6f-220">AND</span><span class="sxs-lookup"><span data-stu-id="95d6f-220">AND</span></span>      |

<span data-ttu-id="95d6f-221">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="95d6f-221">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="95d6f-222">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="95d6f-222">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="95d6f-223">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95d6f-223">See also</span></span>

- [<span data-ttu-id="95d6f-224">Framework e destinazioni</span><span class="sxs-lookup"><span data-stu-id="95d6f-224">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="95d6f-225">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="95d6f-225">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="95d6f-226">Passaggio di argomenti runsettings tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="95d6f-226">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
