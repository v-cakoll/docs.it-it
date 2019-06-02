---
title: Comando dotnet vstest
description: Il comando dotnet vstest consente di compilare un progetto e tutte le relative dipendenze.
author: mairaw
ms.date: 05/30/2018
ms.openlocfilehash: 45fda3b34d2649bc6f20cf3f35c65277a9a53cec
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300038"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="89927-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="89927-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="89927-104">nome</span><span class="sxs-lookup"><span data-stu-id="89927-104">Name</span></span>

<span data-ttu-id="89927-105">`dotnet-vstest`: esegue test dai file specificati.</span><span class="sxs-lookup"><span data-stu-id="89927-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="89927-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="89927-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89927-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89927-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89927-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89927-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89927-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89927-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a><span data-ttu-id="89927-110">Description</span><span class="sxs-lookup"><span data-stu-id="89927-110">Description</span></span>

<span data-ttu-id="89927-111">Il comando `dotnet-vstest` esegue l'applicazione della riga di comando `VSTest.Console` per eseguire unit test automatizzati.</span><span class="sxs-lookup"><span data-stu-id="89927-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="89927-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="89927-112">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="89927-113">Eseguire i test dagli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="89927-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="89927-114">Per separare più nomi di assembly di test, usare gli spazi.</span><span class="sxs-lookup"><span data-stu-id="89927-114">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="89927-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="89927-115">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89927-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89927-116">.NET Core 2.1</span></span>](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="89927-117">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="89927-117">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="89927-118">Esegue test con nomi corrispondenti ai valori specificati.</span><span class="sxs-lookup"><span data-stu-id="89927-118">Run tests with names that match the provided values.</span></span> <span data-ttu-id="89927-119">Se si specificano più valori, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="89927-119">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="89927-120">Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).</span><span class="sxs-lookup"><span data-stu-id="89927-120">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="89927-121">Architettura della piattaforma di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-121">Target platform architecture used for test execution.</span></span> <span data-ttu-id="89927-122">I valori validi sono `x86`, `x64` e `ARM`.</span><span class="sxs-lookup"><span data-stu-id="89927-122">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="89927-123">Versione di .NET Framework di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-123">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="89927-124">Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="89927-124">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="89927-125">Altri valori supportati sono `Framework40`, `Framework45`, `FrameworkCore10` e `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="89927-125">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="89927-126">Esegue test in parallelo.</span><span class="sxs-lookup"><span data-stu-id="89927-126">Execute tests in parallel.</span></span> <span data-ttu-id="89927-127">Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="89927-127">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="89927-128">Specificare un numero esplicito di core impostando la proprietà MaxCpuCount nel nodo RunConfiguration nel file runsettings.</span><span class="sxs-lookup"><span data-stu-id="89927-128">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="89927-129">Esegue test corrispondenti all'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="89927-129">Run tests that match the given expression.</span></span> <span data-ttu-id="89927-130">`<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="89927-130">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="89927-131">L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="89927-131">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="89927-132">Per raggruppare le sottoespressioni vengono usate le parentesi `()`.</span><span class="sxs-lookup"><span data-stu-id="89927-132">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="89927-133">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="89927-133">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="89927-134">Specifica un logger per i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-134">Specify a logger for test results.</span></span>

* <span data-ttu-id="89927-135">Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="89927-135">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="89927-136">Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`.</span><span class="sxs-lookup"><span data-stu-id="89927-136">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="89927-137">Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-137">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="89927-138">Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-138">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="89927-139">Elenca tutti i test individuati dal contenitore di test specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-139">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="89927-140">ID del processo padre responsabile dell'avvio del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="89927-140">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="89927-141">Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.</span><span class="sxs-lookup"><span data-stu-id="89927-141">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="89927-142">Abilita i log dettagliati per la piattaforma di test.</span><span class="sxs-lookup"><span data-stu-id="89927-142">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="89927-143">I log vengono scritti nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-143">Logs are written to the provided file.</span></span>

`--Blame|/Blame`

<span data-ttu-id="89927-144">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="89927-144">Runs the tests in blame mode.</span></span> <span data-ttu-id="89927-145">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-145">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="89927-146">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="89927-146">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`--InIsolation|/InIsolation`

<span data-ttu-id="89927-147">Esegue i test in un processo isolato.</span><span class="sxs-lookup"><span data-stu-id="89927-147">Runs the tests in an isolated process.</span></span> <span data-ttu-id="89927-148">In questo modo si riduce la probabilità di arresto del processo di *vstest.console.exe* a causa di un errore durante i test, sebbene questi ultimi potrebbero risultare più lenti.</span><span class="sxs-lookup"><span data-stu-id="89927-148">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

`@<file>`

<span data-ttu-id="89927-149">Legge un file di risposta per altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="89927-149">Reads response file for more options.</span></span>

`args`

<span data-ttu-id="89927-150">Specifica argomenti aggiuntivi da passare all'adattatore.</span><span class="sxs-lookup"><span data-stu-id="89927-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="89927-151">Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="89927-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="89927-152">Per separare più argomenti usare uno spazio.</span><span class="sxs-lookup"><span data-stu-id="89927-152">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89927-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89927-153">.NET Core 2.0</span></span>](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="89927-154">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="89927-154">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="89927-155">Esegue test con nomi corrispondenti ai valori specificati.</span><span class="sxs-lookup"><span data-stu-id="89927-155">Run tests with names that match the provided values.</span></span> <span data-ttu-id="89927-156">Se si specificano più valori, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="89927-156">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="89927-157">Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).</span><span class="sxs-lookup"><span data-stu-id="89927-157">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="89927-158">Architettura della piattaforma di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-158">Target platform architecture used for test execution.</span></span> <span data-ttu-id="89927-159">I valori validi sono `x86`, `x64` e `ARM`.</span><span class="sxs-lookup"><span data-stu-id="89927-159">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="89927-160">Versione di .NET Framework di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-160">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="89927-161">Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="89927-161">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="89927-162">Altri valori supportati sono `Framework40`, `Framework45` e `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="89927-162">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="89927-163">Esegue test in parallelo.</span><span class="sxs-lookup"><span data-stu-id="89927-163">Execute tests in parallel.</span></span> <span data-ttu-id="89927-164">Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="89927-164">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="89927-165">Specificare un numero esplicito di core impostando la proprietà MaxCpuCount nel nodo RunConfiguration nel file runsettings.</span><span class="sxs-lookup"><span data-stu-id="89927-165">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="89927-166">Esegue test corrispondenti all'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="89927-166">Run tests that match the given expression.</span></span> <span data-ttu-id="89927-167">`<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="89927-167">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="89927-168">L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="89927-168">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="89927-169">Per raggruppare le sottoespressioni vengono usate le parentesi `()`.</span><span class="sxs-lookup"><span data-stu-id="89927-169">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="89927-170">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="89927-170">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="89927-171">Specifica un logger per i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-171">Specify a logger for test results.</span></span>

* <span data-ttu-id="89927-172">Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="89927-172">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="89927-173">Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`.</span><span class="sxs-lookup"><span data-stu-id="89927-173">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="89927-174">Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-174">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="89927-175">Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-175">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="89927-176">Elenca tutti i test individuati dal contenitore di test specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-176">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="89927-177">ID del processo padre responsabile dell'avvio del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="89927-177">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="89927-178">Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.</span><span class="sxs-lookup"><span data-stu-id="89927-178">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="89927-179">Abilita i log dettagliati per la piattaforma di test.</span><span class="sxs-lookup"><span data-stu-id="89927-179">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="89927-180">I log vengono scritti nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-180">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="89927-181">Specifica argomenti aggiuntivi da passare all'adattatore.</span><span class="sxs-lookup"><span data-stu-id="89927-181">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="89927-182">Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="89927-182">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="89927-183">Per separare più argomenti usare uno spazio.</span><span class="sxs-lookup"><span data-stu-id="89927-183">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89927-184">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89927-184">.NET Core 1.x</span></span>](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="89927-185">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="89927-185">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="89927-186">Esegue test con nomi corrispondenti ai valori specificati.</span><span class="sxs-lookup"><span data-stu-id="89927-186">Run tests with names that match the provided values.</span></span> <span data-ttu-id="89927-187">Se si specificano più valori, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="89927-187">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="89927-188">Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).</span><span class="sxs-lookup"><span data-stu-id="89927-188">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="89927-189">Architettura della piattaforma di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-189">Target platform architecture used for test execution.</span></span> <span data-ttu-id="89927-190">I valori validi sono `x86`, `x64` e `ARM`.</span><span class="sxs-lookup"><span data-stu-id="89927-190">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="89927-191">Versione di .NET Framework di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-191">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="89927-192">Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="89927-192">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="89927-193">Altri valori supportati sono `Framework40`, `Framework45` e `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="89927-193">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="89927-194">Esegue test in parallelo.</span><span class="sxs-lookup"><span data-stu-id="89927-194">Execute tests in parallel.</span></span> <span data-ttu-id="89927-195">Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="89927-195">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="89927-196">Specificare un numero esplicito di core impostando la proprietà MaxCpuCount nel nodo RunConfiguration nel file runsettings.</span><span class="sxs-lookup"><span data-stu-id="89927-196">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="89927-197">Esegue test corrispondenti all'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="89927-197">Run tests that match the given expression.</span></span> <span data-ttu-id="89927-198">`<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="89927-198">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="89927-199">L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="89927-199">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="89927-200">Per raggruppare le sottoespressioni vengono usate le parentesi `()`.</span><span class="sxs-lookup"><span data-stu-id="89927-200">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="89927-201">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="89927-201">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="89927-202">Specifica un logger per i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-202">Specify a logger for test results.</span></span>

* <span data-ttu-id="89927-203">Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="89927-203">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="89927-204">Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`.</span><span class="sxs-lookup"><span data-stu-id="89927-204">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="89927-205">Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-205">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="89927-206">Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="89927-206">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="89927-207">Elenca tutti i test individuati dal contenitore di test specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-207">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="89927-208">ID del processo padre responsabile dell'avvio del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="89927-208">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="89927-209">Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.</span><span class="sxs-lookup"><span data-stu-id="89927-209">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="89927-210">Abilita i log dettagliati per la piattaforma di test.</span><span class="sxs-lookup"><span data-stu-id="89927-210">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="89927-211">I log vengono scritti nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="89927-211">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="89927-212">Specifica argomenti aggiuntivi da passare all'adattatore.</span><span class="sxs-lookup"><span data-stu-id="89927-212">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="89927-213">Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="89927-213">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="89927-214">Per separare più argomenti usare uno spazio.</span><span class="sxs-lookup"><span data-stu-id="89927-214">Use a space to separate multiple arguments.</span></span>

---

## <a name="examples"></a><span data-ttu-id="89927-215">Esempi</span><span class="sxs-lookup"><span data-stu-id="89927-215">Examples</span></span>

<span data-ttu-id="89927-216">Eseguire test in `mytestproject.dll`:</span><span class="sxs-lookup"><span data-stu-id="89927-216">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="89927-217">Eseguire test in `mytestproject.dll`, esportando in una cartella personalizzata con il nome personalizzato:</span><span class="sxs-lookup"><span data-stu-id="89927-217">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="89927-218">Eseguire test in `mytestproject.dll` e `myothertestproject.exe`:</span><span class="sxs-lookup"><span data-stu-id="89927-218">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="89927-219">Eseguire test `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="89927-219">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="89927-220">Eseguire test `TestMethod1` e `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="89927-220">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
