---
title: Comando dotnet test - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: d85ca0bf75baa94e63358bd66d11bc29e8b9284b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-test"></a><span data-ttu-id="94166-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="94166-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="94166-104">nome</span><span class="sxs-lookup"><span data-stu-id="94166-104">Name</span></span>

<span data-ttu-id="94166-105">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="94166-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="94166-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="94166-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="94166-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="94166-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="94166-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="94166-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="94166-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94166-109">Description</span></span>

<span data-ttu-id="94166-110">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="94166-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="94166-111">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="94166-111">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="94166-112">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="94166-112">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="94166-113">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="94166-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="94166-114">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="94166-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="94166-115">Argomenti</span><span class="sxs-lookup"><span data-stu-id="94166-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="94166-116">Specifica un percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="94166-116">Specifies a path to the test project.</span></span> <span data-ttu-id="94166-117">Se omesso, per impostazione predefinita sarà la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="94166-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="94166-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="94166-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="94166-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="94166-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="94166-120">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="94166-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="94166-121">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="94166-121">Defines the build configuration.</span></span> <span data-ttu-id="94166-122">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="94166-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="94166-123">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="94166-123">Enables data collector for the test run.</span></span> <span data-ttu-id="94166-124">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="94166-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="94166-125">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="94166-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="94166-126">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="94166-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="94166-127">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="94166-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="94166-128">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="94166-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="94166-129">Per altre informazioni e per esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="94166-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="94166-130">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="94166-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="94166-131">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="94166-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="94166-132">Non compila il progetto di test prima di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="94166-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="94166-133">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="94166-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="94166-134">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="94166-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="94166-135">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="94166-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="94166-136">Se la directory specificata non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="94166-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="94166-137">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="94166-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="94166-138">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="94166-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="94166-139">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="94166-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="94166-140">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="94166-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="94166-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="94166-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="94166-142">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="94166-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="94166-143">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="94166-143">Defines the build configuration.</span></span> <span data-ttu-id="94166-144">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="94166-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="94166-145">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="94166-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="94166-146">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="94166-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="94166-147">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="94166-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="94166-148">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="94166-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="94166-149">Per altre informazioni e per esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="94166-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="94166-150">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="94166-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="94166-151">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="94166-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="94166-152">Non compila il progetto di test prima di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="94166-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="94166-153">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="94166-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="94166-154">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="94166-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="94166-155">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="94166-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="94166-156">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="94166-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="94166-157">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="94166-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="94166-158">Esempi</span><span class="sxs-lookup"><span data-stu-id="94166-158">Examples</span></span>

<span data-ttu-id="94166-159">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="94166-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="94166-160">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="94166-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="94166-161">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="94166-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="94166-162">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="94166-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="94166-163">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="94166-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="94166-164">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="94166-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="94166-165">Framework di test</span><span class="sxs-lookup"><span data-stu-id="94166-165">Test Framework</span></span> | <span data-ttu-id="94166-166">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="94166-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="94166-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="94166-167">MSTest</span></span>         | <ul><li><span data-ttu-id="94166-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="94166-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="94166-169">nome</span><span class="sxs-lookup"><span data-stu-id="94166-169">Name</span></span></li><li><span data-ttu-id="94166-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="94166-170">ClassName</span></span></li><li><span data-ttu-id="94166-171">Priorità</span><span class="sxs-lookup"><span data-stu-id="94166-171">Priority</span></span></li><li><span data-ttu-id="94166-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="94166-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="94166-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="94166-173">Xunit</span></span>          | <ul><li><span data-ttu-id="94166-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="94166-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="94166-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="94166-175">DisplayName</span></span></li><li><span data-ttu-id="94166-176">Tratti</span><span class="sxs-lookup"><span data-stu-id="94166-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="94166-177">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="94166-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="94166-178">Operatore</span><span class="sxs-lookup"><span data-stu-id="94166-178">Operator</span></span> | <span data-ttu-id="94166-179">Funzione</span><span class="sxs-lookup"><span data-stu-id="94166-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="94166-180">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="94166-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="94166-181">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="94166-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="94166-182">Contiene</span><span class="sxs-lookup"><span data-stu-id="94166-182">Contains</span></span>        |

<span data-ttu-id="94166-183">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="94166-183">`<value>` is a string.</span></span> <span data-ttu-id="94166-184">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="94166-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="94166-185">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="94166-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="94166-186">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="94166-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="94166-187">Operatore</span><span class="sxs-lookup"><span data-stu-id="94166-187">Operator</span></span> | <span data-ttu-id="94166-188">Funzione</span><span class="sxs-lookup"><span data-stu-id="94166-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="94166-189">OR</span><span class="sxs-lookup"><span data-stu-id="94166-189">OR</span></span>       |
| `&`      | <span data-ttu-id="94166-190">AND</span><span class="sxs-lookup"><span data-stu-id="94166-190">AND</span></span>      |

<span data-ttu-id="94166-191">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="94166-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="94166-192">Per altre informazioni e per esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="94166-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94166-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94166-193">See also</span></span>

 [<span data-ttu-id="94166-194">Frameworks e destinazioni</span><span class="sxs-lookup"><span data-stu-id="94166-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="94166-195">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="94166-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
