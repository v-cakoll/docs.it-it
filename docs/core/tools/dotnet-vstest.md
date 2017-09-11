---
title: Comando dotnet vstest - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet vstest consente di compilare un progetto e tutte le relative dipendenze.
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: c5a7ee0ba306cea641b0ff34f0b521c92bd03719
ms.contentlocale: it-it
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-vstest"></a><span data-ttu-id="42c57-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="42c57-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="42c57-104">nome</span><span class="sxs-lookup"><span data-stu-id="42c57-104">Name</span></span>

<span data-ttu-id="42c57-105">`dotnet-vstest`: esegue test dai file specificati.</span><span class="sxs-lookup"><span data-stu-id="42c57-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="42c57-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="42c57-106">Synopsis</span></span>

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a><span data-ttu-id="42c57-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42c57-107">Description</span></span>

<span data-ttu-id="42c57-108">Il comando `dotnet-vstest` esegue l'applicazione della riga di comando `VSTest.Console` per eseguire unit test automatici e test sull'applicazione UI codificata.</span><span class="sxs-lookup"><span data-stu-id="42c57-108">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit and coded UI application tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="42c57-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="42c57-109">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="42c57-110">Eseguire i test dagli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="42c57-110">Run tests from the specified assemblies.</span></span> <span data-ttu-id="42c57-111">Per separare più nomi di assembly di test, usare gli spazi.</span><span class="sxs-lookup"><span data-stu-id="42c57-111">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="42c57-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="42c57-112">Options</span></span>

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="42c57-113">Impostazioni da usare durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="42c57-113">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="42c57-114">Esegue test con nomi corrispondenti ai valori specificati.</span><span class="sxs-lookup"><span data-stu-id="42c57-114">Run tests with names that match the provided values.</span></span> <span data-ttu-id="42c57-115">Se si specificano più valori, separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="42c57-115">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="42c57-116">Durante l'esecuzione dei test, vengono usati adattatori di test personalizzati da un percorso specificato (se presenti).</span><span class="sxs-lookup"><span data-stu-id="42c57-116">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="42c57-117">Architettura della piattaforma di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="42c57-117">Target platform architecture used for test execution.</span></span> <span data-ttu-id="42c57-118">I valori validi sono `x86`, `x64` e `ARM`.</span><span class="sxs-lookup"><span data-stu-id="42c57-118">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="42c57-119">Versione di .NET Framework di destinazione usata per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="42c57-119">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="42c57-120">Esempi di valori validi sono `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0` e così via. Altri valori supportati sono `Framework35`, `Framework40`, `Framework45` e `FrameworkCore10`.</span><span class="sxs-lookup"><span data-stu-id="42c57-120">Examples of valid values are `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Other supported values are `Framework35`, `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="42c57-121">Esegue test in parallelo.</span><span class="sxs-lookup"><span data-stu-id="42c57-121">Execute tests in parallel.</span></span> <span data-ttu-id="42c57-122">Per impostazione predefinita, tutti i core presenti nel computer sono disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="42c57-122">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="42c57-123">Impostare un numero esplicito di core con un file di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="42c57-123">Set an explicit number of cores with a settings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="42c57-124">Esegue test corrispondenti all'espressione specificata.</span><span class="sxs-lookup"><span data-stu-id="42c57-124">Run tests that match the given expression.</span></span> <span data-ttu-id="42c57-125">`<Expression>` è in formato `<property>Operator<value>[|&<Expression>]`, dove Operator è `=`, `!=` o `~`.</span><span class="sxs-lookup"><span data-stu-id="42c57-125">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span>  <span data-ttu-id="42c57-126">L'operatore `~` usa la semantica 'contains' ed è applicabile per le proprietà stringa come `DisplayName`.</span><span class="sxs-lookup"><span data-stu-id="42c57-126">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="42c57-127">Per raggruppare le sottoespressioni vengono usate le parentesi `()`.</span><span class="sxs-lookup"><span data-stu-id="42c57-127">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="42c57-128">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="42c57-128">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="42c57-129">Specifica un logger per i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="42c57-129">Specify a logger for test results.</span></span>  

* <span data-ttu-id="42c57-130">Per pubblicare i risultati dei test in Team Foundation Server, usare il provider di logger `TfsPublisher`:</span><span class="sxs-lookup"><span data-stu-id="42c57-130">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="42c57-131">Per registrare i risultati in un file di risultati dei test di Visual Studio (con estensione trx), usare il provider di logger `trx`.</span><span class="sxs-lookup"><span data-stu-id="42c57-131">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="42c57-132">Questa opzione crea un file nella directory dei risultati dei test con nome di file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="42c57-132">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="42c57-133">Se `LogFileName` non è specificato, viene creato un nome di file univoco per contenere i risultati dei test.</span><span class="sxs-lookup"><span data-stu-id="42c57-133">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="42c57-134">Elenca i test individuati dal contenitore di test specificato.</span><span class="sxs-lookup"><span data-stu-id="42c57-134">Lists discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="42c57-135">ID del processo padre responsabile dell'avvio del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="42c57-135">Process Id of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="42c57-136">Specifica la porta per la connessione socket e la ricezione dei messaggi di evento.</span><span class="sxs-lookup"><span data-stu-id="42c57-136">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="42c57-137">Abilita i log dettagliati per la piattaforma di test.</span><span class="sxs-lookup"><span data-stu-id="42c57-137">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="42c57-138">I log vengono scritti nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="42c57-138">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="42c57-139">Specifica argomenti aggiuntivi da passare all'adattatore.</span><span class="sxs-lookup"><span data-stu-id="42c57-139">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="42c57-140">Gli argomenti sono specificati come coppie nome-valore nel formato `<n>=<v>`, dove `<n>` è il nome dell'argomento e `<v>` è il valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="42c57-140">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="42c57-141">Per separare più argomenti usare uno spazio.</span><span class="sxs-lookup"><span data-stu-id="42c57-141">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="42c57-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="42c57-142">Examples</span></span>

<span data-ttu-id="42c57-143">Eseguire test in `mytestproject.dll`:</span><span class="sxs-lookup"><span data-stu-id="42c57-143">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="42c57-144">Eseguire test in `mytestproject.dll` e `myothertestproject.exe`:</span><span class="sxs-lookup"><span data-stu-id="42c57-144">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="42c57-145">Eseguire test `TestMethod1`:</span><span class="sxs-lookup"><span data-stu-id="42c57-145">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="42c57-146">Eseguire test `TestMethod1` e `TestMethod2`:</span><span class="sxs-lookup"><span data-stu-id="42c57-146">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`

