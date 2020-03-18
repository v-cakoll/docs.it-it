---
title: Comando dotnet vstest
description: Il comando dotnet vstest consente di compilare un progetto e tutte le relative dipendenze.
ms.date: 02/27/2020
ms.openlocfilehash: 88e5b6a8966d78d0746f9ea5ccbccab142a2e0f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156933"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="76892-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="76892-103">dotnet vstest</span></span>

<span data-ttu-id="76892-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="76892-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="76892-105">Nome</span><span class="sxs-lookup"><span data-stu-id="76892-105">Name</span></span>

<span data-ttu-id="76892-106">`dotnet-vstest`: esegue test dai file specificati.</span><span class="sxs-lookup"><span data-stu-id="76892-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="76892-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="76892-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings] [--Tests]
    [--TestAdapterPath] [--Platform] [--Framework] [--Parallel]
    [--TestCaseFilter] [--logger] [-lt|--ListTests]
    [--ParentProcessId] [--Port] [--Diag] [--Blame]
    [--InIsolation] [[--] <args>...]] [-?|--Help]
```

## <a name="description"></a><span data-ttu-id="76892-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76892-108">Description</span></span>

<span data-ttu-id="76892-109">Il comando `dotnet-vstest` esegue l'applicazione della riga di comando `VSTest.Console` per eseguire unit test automatizzati.</span><span class="sxs-lookup"><span data-stu-id="76892-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="76892-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="76892-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="76892-111">Eseguire i test dagli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="76892-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="76892-112">Per separare più nomi di assembly di test, usare gli spazi.</span><span class="sxs-lookup"><span data-stu-id="76892-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="76892-113">Sono supportati caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="76892-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="76892-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="76892-114">Options</span></span>

- **`--Settings <Settings File>`**

  <span data-ttu-id="76892-115">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="76892-115">Settings to use when running tests.</span></span>

- **`--Tests <Test Names>`**

  <span data-ttu-id="76892-116">Esegue test con nomi corrispondenti ai valori specificati.</span><span class="sxs-lookup"><span data-stu-id="76892-116">Run tests with names that match the provided values.</span></span> <span data-ttu-id="76892-117">Se si specificano più valori, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="76892-117">Separate multiple values with commas.</span></span>

- **`--TestAdapterPath`**

  <span data-ttu-id="76892-118">Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).</span><span class="sxs-lookup"><span data-stu-id="76892-118">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--Platform <Platform type>`**

  <span data-ttu-id="76892-119">Architettura della piattaforma di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="76892-119">Target platform architecture used for test execution.</span></span> <span data-ttu-id="76892-120">I valori validi sono `x86`, `x64` e `ARM`.</span><span class="sxs-lookup"><span data-stu-id="76892-120">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Framework <Framework Version>`**

  <span data-ttu-id="76892-121">Versione di .NET Framework di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="76892-121">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="76892-122">Esempi di valori validi sono `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`.</span><span class="sxs-lookup"><span data-stu-id="76892-122">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="76892-123">Altri valori supportati sono `Framework40`, `Framework45`, `FrameworkCore10` e `FrameworkUap10`.</span><span class="sxs-lookup"><span data-stu-id="76892-123">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--Parallel`**

  <span data-ttu-id="76892-124">Eseguire test in parallelo.</span><span class="sxs-lookup"><span data-stu-id="76892-124">Run tests in parallel.</span></span> <span data-ttu-id="76892-125">Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="76892-125">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="76892-126">Specificare un numero esplicito `MaxCpuCount` di core `RunConfiguration` impostando la proprietà nel nodo nel file *runsettings.*</span><span class="sxs-lookup"><span data-stu-id="76892-126">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--TestCaseFilter <Expression>`**

  <span data-ttu-id="76892-127">Esegue test corrispondenti all'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="76892-127">Run tests that match the given expression.</span></span> <span data-ttu-id="76892-128">`<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="76892-128">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="76892-129">L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="76892-129">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="76892-130">Le `()` parentesi vengono utilizzate per raggruppare le sottoespressioni.</span><span class="sxs-lookup"><span data-stu-id="76892-130">Parenthesis `()` are used to group subexpressions.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="76892-131">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="76892-131">Prints out a short help for the command.</span></span>

- **`--logger <Logger Uri/FriendlyName>`**

  <span data-ttu-id="76892-132">Specifica un logger per i risultati di test.</span><span class="sxs-lookup"><span data-stu-id="76892-132">Specify a logger for test results.</span></span>

  - <span data-ttu-id="76892-133">Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="76892-133">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="76892-134">Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`.</span><span class="sxs-lookup"><span data-stu-id="76892-134">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="76892-135">Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="76892-135">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="76892-136">Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="76892-136">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`-lt|--ListTests <File Name>`**

  <span data-ttu-id="76892-137">Elenca tutti i test individuati dal contenitore di test specificato.</span><span class="sxs-lookup"><span data-stu-id="76892-137">Lists all discovered tests from the given test container.</span></span>

- **`--ParentProcessId <ParentProcessId>`**

  <span data-ttu-id="76892-138">ID del processo padre responsabile dell'avvio del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="76892-138">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Port <Port>`**

  <span data-ttu-id="76892-139">Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.</span><span class="sxs-lookup"><span data-stu-id="76892-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--Diag <Path to log file>`**

  <span data-ttu-id="76892-140">Abilita i log dettagliati per la piattaforma di test.</span><span class="sxs-lookup"><span data-stu-id="76892-140">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="76892-141">I log vengono scritti nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="76892-141">Logs are written to the provided file.</span></span>

- **`--Blame`**

  <span data-ttu-id="76892-142">Esegue i test in modalità di segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="76892-142">Runs the tests in blame mode.</span></span> <span data-ttu-id="76892-143">Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test.</span><span class="sxs-lookup"><span data-stu-id="76892-143">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="76892-144">Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="76892-144">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="76892-145">Esegue i test in un processo isolato.</span><span class="sxs-lookup"><span data-stu-id="76892-145">Runs the tests in an isolated process.</span></span> <span data-ttu-id="76892-146">In questo modo si riduce la probabilità di arresto del processo di *vstest.console.exe* a causa di un errore durante i test, sebbene questi ultimi potrebbero risultare più lenti.</span><span class="sxs-lookup"><span data-stu-id="76892-146">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`@<file>`**

  <span data-ttu-id="76892-147">Legge un file di risposta per altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="76892-147">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="76892-148">Specifica argomenti aggiuntivi da passare all'adattatore.</span><span class="sxs-lookup"><span data-stu-id="76892-148">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="76892-149">Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="76892-149">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="76892-150">Per separare più argomenti usare uno spazio.</span><span class="sxs-lookup"><span data-stu-id="76892-150">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="76892-151">Esempi</span><span class="sxs-lookup"><span data-stu-id="76892-151">Examples</span></span>

<span data-ttu-id="76892-152">Eseguire test in *mytestproject.dll*:</span><span class="sxs-lookup"><span data-stu-id="76892-152">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="76892-153">Eseguire test in *mytestproject.dll*, esportando in una cartella personalizzata con nome personalizzato:</span><span class="sxs-lookup"><span data-stu-id="76892-153">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="76892-154">Eseguire test in *mytestproject.dll* e *myothertestproject.exe*:</span><span class="sxs-lookup"><span data-stu-id="76892-154">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="76892-155">Eseguire test `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="76892-155">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="76892-156">Eseguire test `TestMethod1` e `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="76892-156">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```
