---
title: Organizzazione e test di progetti con la riga di comando di .NET Core
description: Questa esercitazione illustra come organizzare e testare i progetti .NET Core dalla riga di comando.
author: cartermp
ms.author: mairaw
ms.date: 05/16/2017
ms.openlocfilehash: a49eb1d398ab80a4ece703b7889083ea967df862
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a><span data-ttu-id="f8624-103">Organizzazione e test di progetti con la riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f8624-103">Organizing and testing projects with the .NET Core command line</span></span>

<span data-ttu-id="f8624-104">Questa esercitazione segue [Introduzione all'uso di .NET Core su Windows/Linux/macOS dalla riga di comando](using-with-xplat-cli.md) e va oltre la creazione di una semplice app console, illustrando lo sviluppo di applicazioni più avanzate e organizzate.</span><span class="sxs-lookup"><span data-stu-id="f8624-104">This tutorial follows [Getting started with .NET Core on Windows/Linux/macOS using the command line](using-with-xplat-cli.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="f8624-105">L'esercitazione indica come usare le cartelle per organizzare il codice, quindi illustra come estendere un'applicazione console con il framework di testo [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="f8624-105">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.github.io/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="f8624-106">Uso di cartelle per organizzare il codice</span><span class="sxs-lookup"><span data-stu-id="f8624-106">Using folders to organize code</span></span>

<span data-ttu-id="f8624-107">È possibile introdurre nuovi tipi in un'app console aggiungendo all'app i file contenenti i tipi.</span><span class="sxs-lookup"><span data-stu-id="f8624-107">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="f8624-108">Se ad esempio si aggiungono al progetto file contenenti i tipi `AccountInformation` e `MonthlyReportRecords`, la struttura del progetto resta semplice e facile da esplorare:</span><span class="sxs-lookup"><span data-stu-id="f8624-108">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="f8624-109">Tuttavia questa soluzione funziona solo quando le dimensioni del progetto sono relativamente piccole.</span><span class="sxs-lookup"><span data-stu-id="f8624-109">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="f8624-110">Si supponga di aggiungere 20 tipi al progetto.</span><span class="sxs-lookup"><span data-stu-id="f8624-110">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="f8624-111">La navigazione e la manutenzione diventano più complicate per la presenza di molti file nella directory radice del progetto.</span><span class="sxs-lookup"><span data-stu-id="f8624-111">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="f8624-112">Per organizzare il progetto, creare una nuova cartella per l'archiviazione dei file dei tipi e denominarla *Models*.</span><span class="sxs-lookup"><span data-stu-id="f8624-112">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="f8624-113">Inserire i file dei tipi nella cartella *Models*:</span><span class="sxs-lookup"><span data-stu-id="f8624-113">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="f8624-114">La navigazione e la manutenzione risultano più facili nei progetti che raggruppano i file in cartelle mediante codice.</span><span class="sxs-lookup"><span data-stu-id="f8624-114">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="f8624-115">Nella sezione successiva viene creato un esempio più complesso con cartelle e unit test.</span><span class="sxs-lookup"><span data-stu-id="f8624-115">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="f8624-116">Organizzare ed eseguire test con l'esempio NewTypes Pets</span><span class="sxs-lookup"><span data-stu-id="f8624-116">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="f8624-117">Compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="f8624-117">Building the sample</span></span>

<span data-ttu-id="f8624-118">Nelle fasi successive è possibile seguire [il progetto di esempio NewTypes Pets](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) o creare file e cartelle personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f8624-118">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="f8624-119">I tipi sono organizzati mediante codice in una struttura di cartelle che consente l'aggiunta di più tipi in un secondo momento. A loro volta i test sono inseriti mediante codice in cartelle che consentono l'aggiunta di altri test in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f8624-119">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="f8624-120">L'esempio contiene due tipi `Dog` e `Cat` e definisce l'implementazione dell'interfaccia comune `IPet`.</span><span class="sxs-lookup"><span data-stu-id="f8624-120">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="f8624-121">Per il progetto `NewTypes` l'obiettivo è l'organizzazione dei tipi associati agli animali domestici in una cartella *Pets*.</span><span class="sxs-lookup"><span data-stu-id="f8624-121">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="f8624-122">Se in seguito viene aggiunto un altro set di tipi, ad esempio *WildAnimals*, questi vengono inseriti nella cartella *NewTypes* allo stesso livello della cartella *Pets*.</span><span class="sxs-lookup"><span data-stu-id="f8624-122">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="f8624-123">La cartella *WildAnimals* può contenere tipi corrispondenti ad animali non domestici, ad esempio i tipi `Squirrel` e `Rabbit`.</span><span class="sxs-lookup"><span data-stu-id="f8624-123">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="f8624-124">In questo modo mano a mano che vengono aggiunti dei tipi il progetto mantiene un'organizzazione ottimale.</span><span class="sxs-lookup"><span data-stu-id="f8624-124">In this way as types are added, the project remains well organized.</span></span> 

<span data-ttu-id="f8624-125">Creare la seguente struttura di cartelle con il contenuto di file indicato:</span><span class="sxs-lookup"><span data-stu-id="f8624-125">Create the following folder structure with file content indicated:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

<span data-ttu-id="f8624-126">*IPet.cs*:</span><span class="sxs-lookup"><span data-stu-id="f8624-126">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="f8624-127">*Dog.cs*:</span><span class="sxs-lookup"><span data-stu-id="f8624-127">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="f8624-128">*Cat.cs*:</span><span class="sxs-lookup"><span data-stu-id="f8624-128">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="f8624-129">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="f8624-129">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

<span data-ttu-id="f8624-130">*NewTypes.csproj*:</span><span class="sxs-lookup"><span data-stu-id="f8624-130">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="f8624-131">Eseguire i seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="f8624-131">Execute the following commands:</span></span>

```console
dotnet run
```

<span data-ttu-id="f8624-132">L'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f8624-132">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="f8624-133">Esercizio facoltativo: aggiungere un nuovo tipo di animale domestico, ad esempio `Bird`, estendendo il progetto.</span><span class="sxs-lookup"><span data-stu-id="f8624-133">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="f8624-134">Fare in modo che il metodo `TalkToOwner` corrispondente all'uccellino restituisca `Tweet!` al proprietario.</span><span class="sxs-lookup"><span data-stu-id="f8624-134">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="f8624-135">Eseguire nuovamente l'app.</span><span class="sxs-lookup"><span data-stu-id="f8624-135">Run the app again.</span></span> <span data-ttu-id="f8624-136">L'output includerà `Tweet!`.</span><span class="sxs-lookup"><span data-stu-id="f8624-136">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="f8624-137">Test dell'esempio</span><span class="sxs-lookup"><span data-stu-id="f8624-137">Testing the sample</span></span>

<span data-ttu-id="f8624-138">Il progetto `NewTypes` è attivo ed è stato organizzato inserendo i tipi associati agli animali da compagnia in una cartella.</span><span class="sxs-lookup"><span data-stu-id="f8624-138">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="f8624-139">Creare il progetto di test e iniziare a creare test con il framework di test [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="f8624-139">Next, create your test project and start writing tests with the [xUnit](https://xunit.github.io/) test framework.</span></span> <span data-ttu-id="f8624-140">Gli unit test consentono di verificare automaticamente che i tipi di animali domestici funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8624-140">Unit testing allows you to automatically check the bevahior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="f8624-141">Creare una cartella *test* contenente una sottocartella *NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="f8624-141">Create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="f8624-142">Al prompt dei comandi della cartella *NewTypesTests* eseguire `dotnet new xunit`.</span><span class="sxs-lookup"><span data-stu-id="f8624-142">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="f8624-143">Questa operazione produce due file: *NewTypesTests.csproj* e *UnitTest1.cs*.</span><span class="sxs-lookup"><span data-stu-id="f8624-143">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="f8624-144">Il progetto di test non può verificare i tipi in `NewTypes` e richiede un riferimento al progetto `NewTypes`.</span><span class="sxs-lookup"><span data-stu-id="f8624-144">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="f8624-145">Per aggiungere un riferimento al progetto usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="f8624-145">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="f8624-146">In alternativa è possibile aggiungere manualmente il riferimento al progetto aggiungendo un nodo `<ItemGroup>` al file *NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="f8624-146">You also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="f8624-147">*NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="f8624-147">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="f8624-148">Il file *NewTypesTests.csproj* contiene quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f8624-148">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="f8624-149">Riferimento pacchetto a `Microsoft.NET.Test.Sdk`, l'infrastruttura di test .NET</span><span class="sxs-lookup"><span data-stu-id="f8624-149">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="f8624-150">Riferimento pacchetto a `xunit`, l'infrastruttura di test xUnit</span><span class="sxs-lookup"><span data-stu-id="f8624-150">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="f8624-151">Riferimento pacchetto a `xunit.runner.visualstudio`, il Test Runner</span><span class="sxs-lookup"><span data-stu-id="f8624-151">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="f8624-152">Riferimento progetto a `NewTypes`, il codice da sottoporre ai test</span><span class="sxs-lookup"><span data-stu-id="f8624-152">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="f8624-153">Cambiare il nome *UnitTest1.cs* in *PetTests.cs* e sostituire il codice del file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f8624-153">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
    
    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
}
```

<span data-ttu-id="f8624-154">Esercizio facoltativo: se in precedenza è stato aggiunto un tipo `Bird` che restituisce `Tweet!` al proprietario, aggiungere al file *PetTests.cs* un metodo di test `BirdTalkToOwnerReturnsTweet` per verificare che il metodo `TalkToOwner` funzioni correttamente per il tipo `Bird`.</span><span class="sxs-lookup"><span data-stu-id="f8624-154">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="f8624-155">Anche se si prevede che i valori `expected` e `actual` siano uguali, le asserzioni iniziali con le verifiche `Assert.NotEqual` specificano che sono *not equal* (diversi).</span><span class="sxs-lookup"><span data-stu-id="f8624-155">Although you expect that the `expected` and `actual` values are equal, the initial assertions with the `Assert.NotEqual` checks specify that they are *not equal*.</span></span> <span data-ttu-id="f8624-156">Inizialmente creare sempre i test in modo che diano esito negativo almeno una volta, per verificare la struttura del codice.</span><span class="sxs-lookup"><span data-stu-id="f8624-156">Always initially create your tests to fail once in order to check the logic of the tests.</span></span> <span data-ttu-id="f8624-157">Questo è un passaggio importante nella metodologia di design basato su test (TDD, Test-Driven Design).</span><span class="sxs-lookup"><span data-stu-id="f8624-157">This is an important step in test-driven design (TDD) methodology.</span></span> <span data-ttu-id="f8624-158">Dopo aver verificato che i test hanno dato esito negativo, modificare le asserzioni per fare in modo che diano esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f8624-158">After you confirm the tests fail, you adjust the assertions to allow them to pass.</span></span>

<span data-ttu-id="f8624-159">Di seguito viene riportata la struttura completa del progetto:</span><span class="sxs-lookup"><span data-stu-id="f8624-159">The following shows the complete project structure:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

<span data-ttu-id="f8624-160">Iniziare nella directory *test/NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="f8624-160">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="f8624-161">Ripristinare il progetto di test con il comando [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="f8624-161">Restore the test project with the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="f8624-162">Eseguire i test con il comando [`dotnet test`](../tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="f8624-162">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="f8624-163">Questo comando avvia il Test Runner specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="f8624-163">This command starts the test runner specified in the project file.</span></span>

 [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

 
<span data-ttu-id="f8624-164">Come previsto, i test hanno esito negativo e la console visualizza il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f8624-164">As expected, testing fails, and the console displays the following output:</span></span>
 
```
Test run for C:\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp1.1\NewTypesTests.dll(.NETCoreApp,Version=v1.1)
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.7271827]   Discovering: NewTypesTests
[xUnit.net 00:00:00.8258687]   Discovered:  NewTypesTests
[xUnit.net 00:00:00.8663545]   Starting:    NewTypesTests
[xUnit.net 00:00:01.0109236]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
[xUnit.net 00:00:01.0119107]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0120278]       Expected: Not "Meow!"
[xUnit.net 00:00:01.0120968]       Actual:   "Meow!"
[xUnit.net 00:00:01.0130500]       Stack Trace:
[xUnit.net 00:00:01.0141240]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(22,0): at PetTests.CatTalkToOwnerReturnsMeow()
[xUnit.net 00:00:01.0272364]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:01.0273649]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0274166]       Expected: Not "Woof!"
[xUnit.net 00:00:01.0274690]       Actual:   "Woof!"
[xUnit.net 00:00:01.0275264]       Stack Trace:
[xUnit.net 00:00:01.0275960]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(13,0): at PetTests.DogTalkToOwnerReturnsWoof()
[xUnit.net 00:00:01.0294509]   Finished:    NewTypesTests
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 2.1371 Seconds
```

<span data-ttu-id="f8624-165">Modificare le asserzioni dei test da `Assert.NotEqual` a `Assert.Equal`:</span><span class="sxs-lookup"><span data-stu-id="f8624-165">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="f8624-166">Eseguire nuovamente i test con il comando `dotnet test`. Si ottiene il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f8624-166">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:01.3882374]   Discovering: NewTypesTests
[xUnit.net 00:00:01.4767970]   Discovered:  NewTypesTests
[xUnit.net 00:00:01.5157667]   Starting:    NewTypesTests
[xUnit.net 00:00:01.6408870]   Finished:    NewTypesTests

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6634 Seconds
```

<span data-ttu-id="f8624-167">I test hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f8624-167">Testing passes.</span></span> <span data-ttu-id="f8624-168">I metodi dei tipi di animali da compagnia restituiscono i valori corretti nei messaggi trasmessi al proprietario.</span><span class="sxs-lookup"><span data-stu-id="f8624-168">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="f8624-169">Si sono apprese tecniche per l'organizzazione e il test di progetti con xUnit.</span><span class="sxs-lookup"><span data-stu-id="f8624-169">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="f8624-170">Continuare con queste tecniche applicandole nei propri progetti.</span><span class="sxs-lookup"><span data-stu-id="f8624-170">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="f8624-171">*Buona codifica!*</span><span class="sxs-lookup"><span data-stu-id="f8624-171">*Happy coding!*</span></span>

