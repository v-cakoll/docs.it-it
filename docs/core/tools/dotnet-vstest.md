---
title: Comando dotnet vstest
description: Il comando dotnet vstest consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 02/27/2020
ms.openlocfilehash: e8fa94cf12ca2fe5fb99c6e3c1dcdb52185798c0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463291"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="8ee69-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="8ee69-103">dotnet vstest</span></span>

<span data-ttu-id="8ee69-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="8ee69-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8ee69-105">Nome</span><span class="sxs-lookup"><span data-stu-id="8ee69-105">Name</span></span>

<span data-ttu-id="8ee69-106">`dotnet-vstest`: esegue test dai file specificati.</span><span class="sxs-lookup"><span data-stu-id="8ee69-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8ee69-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="8ee69-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="8ee69-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ee69-108">Description</span></span>

<span data-ttu-id="8ee69-109">Il comando `dotnet-vstest` esegue l'applicazione della riga di comando `VSTest.Console` per eseguire unit test automatizzati.</span><span class="sxs-lookup"><span data-stu-id="8ee69-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="8ee69-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8ee69-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="8ee69-111">Eseguire i test dagli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="8ee69-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="8ee69-112">Per separare più nomi di assembly di test, usare gli spazi.</span><span class="sxs-lookup"><span data-stu-id="8ee69-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="8ee69-113">Sono supportati caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="8ee69-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="8ee69-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8ee69-114">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="8ee69-115">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="8ee69-115">Runs the tests in blame mode.</span></span> <span data-ttu-id="8ee69-116">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="8ee69-116">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="8ee69-117">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="8ee69-117">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="8ee69-118">Abilita i log dettagliati per la piattaforma di test.</span><span class="sxs-lookup"><span data-stu-id="8ee69-118">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="8ee69-119">I log vengono scritti nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="8ee69-119">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="8ee69-120">Versione di .NET Framework di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="8ee69-120">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="8ee69-121">Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="8ee69-121">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="8ee69-122">Altri valori supportati sono `Framework40`, `Framework45`, `FrameworkCore10` e `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="8ee69-122">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="8ee69-123">Esegue i test in un processo isolato.</span><span class="sxs-lookup"><span data-stu-id="8ee69-123">Runs the tests in an isolated process.</span></span> <span data-ttu-id="8ee69-124">In questo modo si riduce la probabilità di arresto del processo di *vstest.console.exe* a causa di un errore durante i test, sebbene questi ultimi potrebbero risultare più lenti.</span><span class="sxs-lookup"><span data-stu-id="8ee69-124">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="8ee69-125">Elenca tutti i test individuati dal contenitore di test specificato.</span><span class="sxs-lookup"><span data-stu-id="8ee69-125">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="8ee69-126">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="8ee69-126">Specify a logger for test results.</span></span>

  - <span data-ttu-id="8ee69-127">Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="8ee69-127">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="8ee69-128">Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`.</span><span class="sxs-lookup"><span data-stu-id="8ee69-128">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="8ee69-129">Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="8ee69-129">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="8ee69-130">Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="8ee69-130">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="8ee69-131">Eseguire test in parallelo.</span><span class="sxs-lookup"><span data-stu-id="8ee69-131">Run tests in parallel.</span></span> <span data-ttu-id="8ee69-132">Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="8ee69-132">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="8ee69-133">Specificare un numero esplicito `MaxCpuCount` di core `RunConfiguration` impostando la proprietà nel nodo nel file *runsettings.*</span><span class="sxs-lookup"><span data-stu-id="8ee69-133">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="8ee69-134">ID del processo padre responsabile dell'avvio del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="8ee69-134">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="8ee69-135">Architettura della piattaforma di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="8ee69-135">Target platform architecture used for test execution.</span></span> <span data-ttu-id="8ee69-136">I valori validi sono `x86`, `x64` e `ARM`.</span><span class="sxs-lookup"><span data-stu-id="8ee69-136">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="8ee69-137">Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.</span><span class="sxs-lookup"><span data-stu-id="8ee69-137">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="8ee69-138">Directory dei risultati dei test che verrà creata nel percorso specificato, se non esistente.</span><span class="sxs-lookup"><span data-stu-id="8ee69-138">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="8ee69-139">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="8ee69-139">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="8ee69-140">Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).</span><span class="sxs-lookup"><span data-stu-id="8ee69-140">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="8ee69-141">Esegue test corrispondenti all'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="8ee69-141">Run tests that match the given expression.</span></span> <span data-ttu-id="8ee69-142">`<EXPRESSION>` è in formato `<property>Operator<value>[|&<EXPRESSION>]`, dove Operator è `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="8ee69-142">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="8ee69-143">L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="8ee69-143">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="8ee69-144">Le parentesi `()` vengono utilizzate per raggruppare le sottoespressioni.</span><span class="sxs-lookup"><span data-stu-id="8ee69-144">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="8ee69-145">Per ulteriori informazioni, vedere [Filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="8ee69-145">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="8ee69-146">Esegue test con nomi corrispondenti ai valori specificati.</span><span class="sxs-lookup"><span data-stu-id="8ee69-146">Run tests with names that match the provided values.</span></span> <span data-ttu-id="8ee69-147">Se si specificano più valori, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="8ee69-147">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="8ee69-148">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="8ee69-148">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="8ee69-149">Legge un file di risposta per altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="8ee69-149">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="8ee69-150">Specifica argomenti aggiuntivi da passare all'adattatore.</span><span class="sxs-lookup"><span data-stu-id="8ee69-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="8ee69-151">Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="8ee69-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="8ee69-152">Per separare più argomenti usare uno spazio.</span><span class="sxs-lookup"><span data-stu-id="8ee69-152">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="8ee69-153">Esempi</span><span class="sxs-lookup"><span data-stu-id="8ee69-153">Examples</span></span>

<span data-ttu-id="8ee69-154">Eseguire test in *mytestproject.dll*:</span><span class="sxs-lookup"><span data-stu-id="8ee69-154">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="8ee69-155">Eseguire test in *mytestproject.dll*, esportando in una cartella personalizzata con nome personalizzato:</span><span class="sxs-lookup"><span data-stu-id="8ee69-155">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="8ee69-156">Eseguire test in *mytestproject.dll* e *myothertestproject.exe*:</span><span class="sxs-lookup"><span data-stu-id="8ee69-156">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="8ee69-157">Eseguire test `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="8ee69-157">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="8ee69-158">Eseguire test `TestMethod1` e `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="8ee69-158">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="8ee69-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ee69-159">See also</span></span>

- [<span data-ttu-id="8ee69-160">Opzioni della riga di comando di VSTest.Console.exe</span><span class="sxs-lookup"><span data-stu-id="8ee69-160">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
