---
title: Comando dotnet test - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 2bee78ca44026f28c51fac3bcf87d976b53e48a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390690"
---
# <a name="dotnet-test"></a><span data-ttu-id="d59f6-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="d59f6-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d59f6-104">nome</span><span class="sxs-lookup"><span data-stu-id="d59f6-104">Name</span></span>

<span data-ttu-id="d59f6-105">`dotnet test`: driver di test .NET usato per eseguire gli unit test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d59f6-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d59f6-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d59f6-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d59f6-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d59f6-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d59f6-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d59f6-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d59f6-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="d59f6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d59f6-110">Description</span></span>

<span data-ttu-id="d59f6-111">Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto.</span><span class="sxs-lookup"><span data-stu-id="d59f6-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="d59f6-112">Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto.</span><span class="sxs-lookup"><span data-stu-id="d59f6-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="d59f6-113">L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="d59f6-114">L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d59f6-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="d59f6-115">I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d59f6-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="d59f6-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d59f6-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d59f6-117">Percorso del progetto di test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-117">Path to the test project.</span></span> <span data-ttu-id="d59f6-118">Se non specificato, per impostazione predefinita viene usata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d59f6-118">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="d59f6-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d59f6-119">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d59f6-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d59f6-120">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="d59f6-121">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-121">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="d59f6-122">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="d59f6-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="d59f6-123">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-123">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="d59f6-124">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="d59f6-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d59f6-125">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d59f6-125">Defines the build configuration.</span></span> <span data-ttu-id="d59f6-126">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="d59f6-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="d59f6-127">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-127">Enables data collector for the test run.</span></span> <span data-ttu-id="d59f6-128">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="d59f6-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="d59f6-129">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="d59f6-129">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d59f6-130">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="d59f6-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d59f6-131">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="d59f6-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d59f6-132">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d59f6-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d59f6-133">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d59f6-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="d59f6-134">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-134">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="d59f6-135">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-135">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="d59f6-136">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d59f6-136">Doesn't build the test project before running it.</span></span> <span data-ttu-id="d59f6-137">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="d59f6-138">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-138">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d59f6-139">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d59f6-139">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="d59f6-140">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-140">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="d59f6-141">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="d59f6-141">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="d59f6-142">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-142">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="d59f6-143">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="d59f6-143">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d59f6-144">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d59f6-145">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d59f6-146">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d59f6-146">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="d59f6-147">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-147">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d59f6-148">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d59f6-148">Defines the build configuration.</span></span> <span data-ttu-id="d59f6-149">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="d59f6-149">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="d59f6-150">Abilita l'agente di raccolta dati per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-150">Enables data collector for the test run.</span></span> <span data-ttu-id="d59f6-151">Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).</span><span class="sxs-lookup"><span data-stu-id="d59f6-151">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="d59f6-152">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="d59f6-152">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d59f6-153">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="d59f6-153">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d59f6-154">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="d59f6-154">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d59f6-155">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d59f6-155">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d59f6-156">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d59f6-156">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="d59f6-157">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-157">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="d59f6-158">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-158">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="d59f6-159">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d59f6-159">Doesn't build the test project before running it.</span></span> <span data-ttu-id="d59f6-160">Imposta anche in modo implicito il flag `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-160">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="d59f6-161">Non esegue un ripristino implicito quando si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-161">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d59f6-162">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d59f6-162">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="d59f6-163">Directory in cui verranno inseriti i risultati del test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-163">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="d59f6-164">Se la directory specificata non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="d59f6-164">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="d59f6-165">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-165">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="d59f6-166">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="d59f6-166">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d59f6-167">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d59f6-168">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d59f6-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d59f6-169">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="d59f6-170">Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-170">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="d59f6-171">Definisce la configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d59f6-171">Defines the build configuration.</span></span> <span data-ttu-id="d59f6-172">Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="d59f6-172">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="d59f6-173">Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="d59f6-173">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="d59f6-174">Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="d59f6-174">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d59f6-175">Filtra i test nel progetto corrente usando l'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="d59f6-175">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="d59f6-176">Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details).</span><span class="sxs-lookup"><span data-stu-id="d59f6-176">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="d59f6-177">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d59f6-177">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="d59f6-178">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-178">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="d59f6-179">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-179">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="d59f6-180">Non compila il progetto di test prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d59f6-180">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d59f6-181">Directory in cui trovare i file binari da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d59f6-181">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="d59f6-182">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="d59f6-182">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="d59f6-183">Elenca tutti i test individuati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="d59f6-183">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="d59f6-184">Imposta il livello di dettaglio del comando.</span><span class="sxs-lookup"><span data-stu-id="d59f6-184">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d59f6-185">I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-185">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d59f6-186">Esempi</span><span class="sxs-lookup"><span data-stu-id="d59f6-186">Examples</span></span>

<span data-ttu-id="d59f6-187">Eseguire i test nel progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="d59f6-187">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="d59f6-188">Eseguire i test nel progetto `test1`:</span><span class="sxs-lookup"><span data-stu-id="d59f6-188">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="d59f6-189">Dettagli dell'opzione filter</span><span class="sxs-lookup"><span data-stu-id="d59f6-189">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="d59f6-190">`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-190">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="d59f6-191">`<property>` è un attributo di `Test Case`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-191">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="d59f6-192">La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:</span><span class="sxs-lookup"><span data-stu-id="d59f6-192">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="d59f6-193">Framework di test</span><span class="sxs-lookup"><span data-stu-id="d59f6-193">Test Framework</span></span> | <span data-ttu-id="d59f6-194">Proprietà supportate</span><span class="sxs-lookup"><span data-stu-id="d59f6-194">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d59f6-195">MSTest</span><span class="sxs-lookup"><span data-stu-id="d59f6-195">MSTest</span></span>         | <ul><li><span data-ttu-id="d59f6-196">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d59f6-196">FullyQualifiedName</span></span></li><li><span data-ttu-id="d59f6-197">nome</span><span class="sxs-lookup"><span data-stu-id="d59f6-197">Name</span></span></li><li><span data-ttu-id="d59f6-198">ClassName</span><span class="sxs-lookup"><span data-stu-id="d59f6-198">ClassName</span></span></li><li><span data-ttu-id="d59f6-199">Priorità</span><span class="sxs-lookup"><span data-stu-id="d59f6-199">Priority</span></span></li><li><span data-ttu-id="d59f6-200">TestCategory</span><span class="sxs-lookup"><span data-stu-id="d59f6-200">TestCategory</span></span></li></ul> |
| <span data-ttu-id="d59f6-201">xUnit</span><span class="sxs-lookup"><span data-stu-id="d59f6-201">xUnit</span></span>          | <ul><li><span data-ttu-id="d59f6-202">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d59f6-202">FullyQualifiedName</span></span></li><li><span data-ttu-id="d59f6-203">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d59f6-203">DisplayName</span></span></li><li><span data-ttu-id="d59f6-204">Tratti</span><span class="sxs-lookup"><span data-stu-id="d59f6-204">Traits</span></span></li></ul>                                   |

<span data-ttu-id="d59f6-205">`<operator>` descrive la relazione tra la proprietà e il valore:</span><span class="sxs-lookup"><span data-stu-id="d59f6-205">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="d59f6-206">Operatore</span><span class="sxs-lookup"><span data-stu-id="d59f6-206">Operator</span></span> | <span data-ttu-id="d59f6-207">Funzione</span><span class="sxs-lookup"><span data-stu-id="d59f6-207">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="d59f6-208">Corrispondenza esatta</span><span class="sxs-lookup"><span data-stu-id="d59f6-208">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="d59f6-209">Corrispondenza non esatta</span><span class="sxs-lookup"><span data-stu-id="d59f6-209">Not exact match</span></span> |
| `~`      | <span data-ttu-id="d59f6-210">Contiene</span><span class="sxs-lookup"><span data-stu-id="d59f6-210">Contains</span></span>        |

<span data-ttu-id="d59f6-211">`<value>` è una stringa.</span><span class="sxs-lookup"><span data-stu-id="d59f6-211">`<value>` is a string.</span></span> <span data-ttu-id="d59f6-212">Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d59f6-212">All the lookups are case insensitive.</span></span>

<span data-ttu-id="d59f6-213">Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.</span><span class="sxs-lookup"><span data-stu-id="d59f6-213">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="d59f6-214">Le espressioni possono essere unite con operatori condizionali:</span><span class="sxs-lookup"><span data-stu-id="d59f6-214">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="d59f6-215">Operatore</span><span class="sxs-lookup"><span data-stu-id="d59f6-215">Operator</span></span>            | <span data-ttu-id="d59f6-216">Funzione</span><span class="sxs-lookup"><span data-stu-id="d59f6-216">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="d59f6-217">OR</span><span class="sxs-lookup"><span data-stu-id="d59f6-217">OR</span></span>       |
| `&`                 | <span data-ttu-id="d59f6-218">AND</span><span class="sxs-lookup"><span data-stu-id="d59f6-218">AND</span></span>      |

<span data-ttu-id="d59f6-219">È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="d59f6-219">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="d59f6-220">Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).</span><span class="sxs-lookup"><span data-stu-id="d59f6-220">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d59f6-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d59f6-221">See also</span></span>

* [<span data-ttu-id="d59f6-222">Frameworks e destinazioni</span><span class="sxs-lookup"><span data-stu-id="d59f6-222">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
* [<span data-ttu-id="d59f6-223">Catalogo dei RID (Runtime IDentifier) di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d59f6-223">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
