---
title: Comando dotnet test - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 55329bed71be21a787d6e77d8c0ea67d607676b8
ms.contentlocale: it-it
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-test"></a><span data-ttu-id="0f7a7-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="0f7a7-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0f7a7-104">nome</span><span class="sxs-lookup"><span data-stu-id="0f7a7-104">Name</span></span>

<span data-ttu-id="0f7a7-105">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0f7a7-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0f7a7-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0f7a7-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0f7a7-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0f7a7-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0f7a7-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="0f7a7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f7a7-109">Description</span></span>

<span data-ttu-id="0f7a7-110">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="0f7a7-111">Gli unit test sono progetti dell'applicazione console con dipendenze nel framework di unit test (ad esempio MSText, NUnit o xUnit) e nel Test Runner dotnet per il framework di unit test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="0f7a7-112">Sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="0f7a7-113">Anche i progetti di test devono specificare il Test Runner.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="0f7a7-114">Quest'ultimo viene specificato usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0f7a7-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

<span data-ttu-id="0f7a7-115">[!code-xml[Modello di base XUnit](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span><span class="sxs-lookup"><span data-stu-id="0f7a7-115">[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span></span>

## <a name="arguments"></a><span data-ttu-id="0f7a7-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0f7a7-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="0f7a7-117">Specifica un percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-117">Specifies a path to the test project.</span></span> <span data-ttu-id="0f7a7-118">Se omesso, per impostazione predefinita sarà la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-118">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="0f7a7-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0f7a7-119">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0f7a7-120">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0f7a7-120">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="0f7a7-121">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-121">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="0f7a7-122">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-122">Defines the build configuration.</span></span> <span data-ttu-id="0f7a7-123">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-123">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="0f7a7-124">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-124">Enables data collector for the test run.</span></span> <span data-ttu-id="0f7a7-125">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="0f7a7-125">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="0f7a7-126">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-126">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0f7a7-127">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-127">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="0f7a7-128">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-128">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="0f7a7-129">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="0f7a7-129">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="0f7a7-130">Per altre informazioni e per esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="0f7a7-130">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="0f7a7-131">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-131">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="0f7a7-132">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-132">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="0f7a7-133">Non compila il progetto di test prima di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-133">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="0f7a7-134">Non eseguire un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-134">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0f7a7-135">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-135">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="0f7a7-136">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-136">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="0f7a7-137">Se la directory specificata non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-137">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="0f7a7-138">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-138">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="0f7a7-139">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-139">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="0f7a7-140">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="0f7a7-141">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0f7a7-142">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0f7a7-142">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="0f7a7-143">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-143">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="0f7a7-144">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-144">Defines the build configuration.</span></span> <span data-ttu-id="0f7a7-145">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-145">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="0f7a7-146">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-146">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0f7a7-147">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-147">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="0f7a7-148">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-148">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="0f7a7-149">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="0f7a7-149">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="0f7a7-150">Per altre informazioni e per esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="0f7a7-150">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="0f7a7-151">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-151">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="0f7a7-152">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-152">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="0f7a7-153">Non compila il progetto di test prima di eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-153">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0f7a7-154">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-154">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="0f7a7-155">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-155">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="0f7a7-156">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-156">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="0f7a7-157">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="0f7a7-158">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="0f7a7-159">Esempi</span><span class="sxs-lookup"><span data-stu-id="0f7a7-159">Examples</span></span>

<span data-ttu-id="0f7a7-160">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="0f7a7-160">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="0f7a7-161">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="0f7a7-161">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="0f7a7-162">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="0f7a7-162">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="0f7a7-163">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-163">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="0f7a7-164">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-164">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="0f7a7-165">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="0f7a7-165">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="0f7a7-166">Framework di test</span><span class="sxs-lookup"><span data-stu-id="0f7a7-166">Test Framework</span></span> | <span data-ttu-id="0f7a7-167">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="0f7a7-167">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0f7a7-168">MSTest</span><span class="sxs-lookup"><span data-stu-id="0f7a7-168">MSTest</span></span>         | <ul><li><span data-ttu-id="0f7a7-169">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="0f7a7-169">FullyQualifiedName</span></span></li><li><span data-ttu-id="0f7a7-170">Nome</span><span class="sxs-lookup"><span data-stu-id="0f7a7-170">Name</span></span></li><li><span data-ttu-id="0f7a7-171">ClassName</span><span class="sxs-lookup"><span data-stu-id="0f7a7-171">ClassName</span></span></li><li><span data-ttu-id="0f7a7-172">Priorità</span><span class="sxs-lookup"><span data-stu-id="0f7a7-172">Priority</span></span></li><li><span data-ttu-id="0f7a7-173">TestCategory</span><span class="sxs-lookup"><span data-stu-id="0f7a7-173">TestCategory</span></span></li></ul> |
| <span data-ttu-id="0f7a7-174">Xunit</span><span class="sxs-lookup"><span data-stu-id="0f7a7-174">Xunit</span></span>          | <ul><li><span data-ttu-id="0f7a7-175">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="0f7a7-175">FullyQualifiedName</span></span></li><li><span data-ttu-id="0f7a7-176">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0f7a7-176">DisplayName</span></span></li><li><span data-ttu-id="0f7a7-177">Tratti</span><span class="sxs-lookup"><span data-stu-id="0f7a7-177">Traits</span></span></li></ul>                                   |

<span data-ttu-id="0f7a7-178">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="0f7a7-178">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="0f7a7-179">Operatore</span><span class="sxs-lookup"><span data-stu-id="0f7a7-179">Operator</span></span> | <span data-ttu-id="0f7a7-180">Funzione</span><span class="sxs-lookup"><span data-stu-id="0f7a7-180">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="0f7a7-181">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="0f7a7-181">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="0f7a7-182">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="0f7a7-182">Not exact match</span></span> |
| `~`      | <span data-ttu-id="0f7a7-183">Contiene</span><span class="sxs-lookup"><span data-stu-id="0f7a7-183">Contains</span></span>        |

<span data-ttu-id="0f7a7-184">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-184">`<value>` is a string.</span></span> <span data-ttu-id="0f7a7-185">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="0f7a7-186">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="0f7a7-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="0f7a7-187">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="0f7a7-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="0f7a7-188">Operatore</span><span class="sxs-lookup"><span data-stu-id="0f7a7-188">Operator</span></span> | <span data-ttu-id="0f7a7-189">Funzione</span><span class="sxs-lookup"><span data-stu-id="0f7a7-189">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="0f7a7-190">OR</span><span class="sxs-lookup"><span data-stu-id="0f7a7-190">OR</span></span>       |
| `&`      | <span data-ttu-id="0f7a7-191">AND</span><span class="sxs-lookup"><span data-stu-id="0f7a7-191">AND</span></span>      |

<span data-ttu-id="0f7a7-192">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="0f7a7-192">You can enclose expressions in paranthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="0f7a7-193">Per altre informazioni e per esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="0f7a7-193">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f7a7-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f7a7-194">See also</span></span>

 <span data-ttu-id="0f7a7-195">[Framework e destinazioni](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="0f7a7-195">[Frameworks and Targets](../../standard/frameworks.md) </span></span>  
 [<span data-ttu-id="0f7a7-196">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="0f7a7-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

