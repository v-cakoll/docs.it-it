---
title: Organizzazione e test di progetti con la riga di comando di .NET Core
description: Questa esercitazione illustra come organizzare e testare i progetti .NET Core dalla riga di comando.
author: cartermp
ms.date: 09/10/2018
ms.openlocfilehash: fdaa42be4d3b8872a3119f97f253ce277564339e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715347"
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a><span data-ttu-id="30d31-103">Organizzazione e test di progetti con la riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="30d31-103">Organizing and testing projects with the .NET Core command line</span></span>

<span data-ttu-id="30d31-104">Questa esercitazione segue [Introduzione all'uso di .NET Core su Windows/Linux/macOS dalla riga di comando](cli-create-console-app.md) e va oltre la creazione di una semplice app console, illustrando lo sviluppo di applicazioni più avanzate e organizzate.</span><span class="sxs-lookup"><span data-stu-id="30d31-104">This tutorial follows [Get started with .NET Core on Windows/Linux/macOS using the command line](cli-create-console-app.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="30d31-105">L'esercitazione indica come usare le cartelle per organizzare il codice, quindi illustra come estendere un'applicazione console con il framework di testo [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="30d31-105">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.github.io/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="30d31-106">Uso di cartelle per organizzare il codice</span><span class="sxs-lookup"><span data-stu-id="30d31-106">Using folders to organize code</span></span>

<span data-ttu-id="30d31-107">È possibile introdurre nuovi tipi in un'app console aggiungendo all'app i file contenenti i tipi.</span><span class="sxs-lookup"><span data-stu-id="30d31-107">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="30d31-108">Se ad esempio si aggiungono al progetto file contenenti i tipi `AccountInformation` e `MonthlyReportRecords`, la struttura del progetto resta semplice e facile da esplorare:</span><span class="sxs-lookup"><span data-stu-id="30d31-108">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="30d31-109">Tuttavia questa soluzione funziona solo quando le dimensioni del progetto sono relativamente piccole.</span><span class="sxs-lookup"><span data-stu-id="30d31-109">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="30d31-110">Si supponga di aggiungere 20 tipi al progetto.</span><span class="sxs-lookup"><span data-stu-id="30d31-110">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="30d31-111">La navigazione e la manutenzione diventano più complicate per la presenza di molti file nella directory radice del progetto.</span><span class="sxs-lookup"><span data-stu-id="30d31-111">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="30d31-112">Per organizzare il progetto, creare una nuova cartella per l'archiviazione dei file dei tipi e denominarla *Models*.</span><span class="sxs-lookup"><span data-stu-id="30d31-112">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="30d31-113">Inserire i file dei tipi nella cartella *Models*:</span><span class="sxs-lookup"><span data-stu-id="30d31-113">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="30d31-114">La navigazione e la manutenzione risultano più facili nei progetti che raggruppano i file in cartelle mediante codice.</span><span class="sxs-lookup"><span data-stu-id="30d31-114">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="30d31-115">Nella sezione successiva viene creato un esempio più complesso con cartelle e unit test.</span><span class="sxs-lookup"><span data-stu-id="30d31-115">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="30d31-116">Organizzare ed eseguire test con l'esempio NewTypes Pets</span><span class="sxs-lookup"><span data-stu-id="30d31-116">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="30d31-117">Compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="30d31-117">Building the sample</span></span>

<span data-ttu-id="30d31-118">Nelle fasi successive è possibile seguire [il progetto di esempio NewTypes Pets](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) o creare file e cartelle personalizzati.</span><span class="sxs-lookup"><span data-stu-id="30d31-118">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="30d31-119">I tipi sono organizzati mediante codice in una struttura di cartelle che consente l'aggiunta di più tipi in un secondo momento. A loro volta i test sono inseriti mediante codice in cartelle che consentono l'aggiunta di altri test in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="30d31-119">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="30d31-120">L'esempio contiene due tipi `Dog` e `Cat` e definisce l'implementazione dell'interfaccia comune `IPet`.</span><span class="sxs-lookup"><span data-stu-id="30d31-120">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="30d31-121">Per il progetto `NewTypes` l'obiettivo è l'organizzazione dei tipi associati agli animali domestici in una cartella *Pets*.</span><span class="sxs-lookup"><span data-stu-id="30d31-121">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="30d31-122">Se in seguito viene aggiunto un altro set di tipi, ad esempio *WildAnimals*, questi vengono inseriti nella cartella *NewTypes* allo stesso livello della cartella *Pets*.</span><span class="sxs-lookup"><span data-stu-id="30d31-122">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="30d31-123">La cartella *WildAnimals* può contenere tipi corrispondenti ad animali non domestici, ad esempio i tipi `Squirrel` e `Rabbit`.</span><span class="sxs-lookup"><span data-stu-id="30d31-123">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="30d31-124">In questo modo mano a mano che vengono aggiunti dei tipi il progetto mantiene un'organizzazione ottimale.</span><span class="sxs-lookup"><span data-stu-id="30d31-124">In this way as types are added, the project remains well organized.</span></span>

<span data-ttu-id="30d31-125">Creare la seguente struttura di cartelle con il contenuto di file indicato:</span><span class="sxs-lookup"><span data-stu-id="30d31-125">Create the following folder structure with file content indicated:</span></span>

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

<span data-ttu-id="30d31-126">*IPet.cs*:</span><span class="sxs-lookup"><span data-stu-id="30d31-126">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="30d31-127">*Dog.cs*:</span><span class="sxs-lookup"><span data-stu-id="30d31-127">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="30d31-128">*Cat.cs*:</span><span class="sxs-lookup"><span data-stu-id="30d31-128">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="30d31-129">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="30d31-129">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

<span data-ttu-id="30d31-130">*NewTypes.csproj*:</span><span class="sxs-lookup"><span data-stu-id="30d31-130">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="30d31-131">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="30d31-131">Execute the following command:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="30d31-132">L'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="30d31-132">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="30d31-133">Esercizio facoltativo: aggiungere un nuovo tipo di animale domestico, ad esempio `Bird`, estendendo il progetto.</span><span class="sxs-lookup"><span data-stu-id="30d31-133">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="30d31-134">Fare in modo che il metodo `TalkToOwner` corrispondente all'uccellino restituisca `Tweet!` al proprietario.</span><span class="sxs-lookup"><span data-stu-id="30d31-134">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="30d31-135">Eseguire nuovamente l'app.</span><span class="sxs-lookup"><span data-stu-id="30d31-135">Run the app again.</span></span> <span data-ttu-id="30d31-136">L'output includerà `Tweet!`.</span><span class="sxs-lookup"><span data-stu-id="30d31-136">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="30d31-137">Test dell'esempio</span><span class="sxs-lookup"><span data-stu-id="30d31-137">Testing the sample</span></span>

<span data-ttu-id="30d31-138">Il progetto `NewTypes` è attivo ed è stato organizzato inserendo i tipi associati agli animali da compagnia in una cartella.</span><span class="sxs-lookup"><span data-stu-id="30d31-138">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="30d31-139">Creare il progetto di test e iniziare a creare test con il framework di test [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="30d31-139">Next, create your test project and start writing tests with the [xUnit](https://xunit.github.io/) test framework.</span></span> <span data-ttu-id="30d31-140">Il testing unità permette di controllare automaticamente il comportamento dei tipi di animali domestici per verificare che funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="30d31-140">Unit testing allows you to automatically check the behavior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="30d31-141">Tornare alla cartella *src* e creare una cartella *test* contenente una sottocartella *NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="30d31-141">Navigate back to the *src* folder and create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="30d31-142">Al prompt dei comandi della cartella *NewTypesTests* eseguire `dotnet new xunit`.</span><span class="sxs-lookup"><span data-stu-id="30d31-142">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="30d31-143">Questa operazione produce due file: *NewTypesTests.csproj* e *UnitTest1.cs*.</span><span class="sxs-lookup"><span data-stu-id="30d31-143">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="30d31-144">Il progetto di test non può verificare i tipi in `NewTypes` e richiede un riferimento al progetto `NewTypes`.</span><span class="sxs-lookup"><span data-stu-id="30d31-144">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="30d31-145">Per aggiungere un riferimento al progetto usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="30d31-145">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="30d31-146">In alternativa è possibile aggiungere manualmente il riferimento al progetto aggiungendo un nodo `<ItemGroup>` al file *NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="30d31-146">Or, you also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="30d31-147">*NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="30d31-147">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="30d31-148">Il file *NewTypesTests.csproj* contiene quanto segue:</span><span class="sxs-lookup"><span data-stu-id="30d31-148">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="30d31-149">Riferimento pacchetto a `Microsoft.NET.Test.Sdk`, l'infrastruttura di test .NET</span><span class="sxs-lookup"><span data-stu-id="30d31-149">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="30d31-150">Riferimento pacchetto a `xunit`, l'infrastruttura di test xUnit</span><span class="sxs-lookup"><span data-stu-id="30d31-150">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="30d31-151">Riferimento pacchetto a `xunit.runner.visualstudio`, il Test Runner</span><span class="sxs-lookup"><span data-stu-id="30d31-151">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="30d31-152">Riferimento progetto a `NewTypes`, il codice da sottoporre ai test</span><span class="sxs-lookup"><span data-stu-id="30d31-152">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="30d31-153">Cambiare il nome *UnitTest1.cs* in *PetTests.cs* e sostituire il codice del file con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="30d31-153">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

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

<span data-ttu-id="30d31-154">Esercizio facoltativo: se in precedenza è stato aggiunto un tipo `Bird` che restituisce `Tweet!` al proprietario, aggiungere al file *PetTests.cs* un metodo di test `BirdTalkToOwnerReturnsTweet` per verificare che il metodo `TalkToOwner` funzioni correttamente per il tipo `Bird`.</span><span class="sxs-lookup"><span data-stu-id="30d31-154">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="30d31-155">Anche se si prevede che i valori `expected` e `actual` siano uguali, un'asserzione iniziale con le verifiche `Assert.NotEqual` specifica che questi valori sono *not equal* (diversi).</span><span class="sxs-lookup"><span data-stu-id="30d31-155">Although you expect that the `expected` and `actual` values are equal, an initial assertion with the `Assert.NotEqual` check specifies that these values are *not equal*.</span></span> <span data-ttu-id="30d31-156">Per verificare la logica del test, inizialmente creare sempre i test in modo che diano esito negativo.</span><span class="sxs-lookup"><span data-stu-id="30d31-156">Always initially create a test to fail in order to check the logic of the test.</span></span> <span data-ttu-id="30d31-157">Dopo aver confermato che il test non riesce, modificare l'asserzione per fare in modo che il test venga superato.</span><span class="sxs-lookup"><span data-stu-id="30d31-157">After you confirm that the test fails, adjust the assertion to allow the test to pass.</span></span>

<span data-ttu-id="30d31-158">Di seguito viene riportata la struttura completa del progetto:</span><span class="sxs-lookup"><span data-stu-id="30d31-158">The following shows the complete project structure:</span></span>

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

<span data-ttu-id="30d31-159">Iniziare nella directory *test/NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="30d31-159">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="30d31-160">Ripristinare il progetto di test con il comando [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="30d31-160">Restore the test project with the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="30d31-161">Eseguire i test con il comando [`dotnet test`](../tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="30d31-161">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="30d31-162">Questo comando avvia il Test Runner specificato nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="30d31-162">This command starts the test runner specified in the project file.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="30d31-163">Come previsto, i test hanno esito negativo e la console visualizza il seguente output:</span><span class="sxs-lookup"><span data-stu-id="30d31-163">As expected, testing fails, and the console displays the following output:</span></span>

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.77]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:00.78]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 1.7000 Seconds
```

<span data-ttu-id="30d31-164">Modificare le asserzioni dei test da `Assert.NotEqual` a `Assert.Equal`:</span><span class="sxs-lookup"><span data-stu-id="30d31-164">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="30d31-165">Eseguire nuovamente i test con il comando `dotnet test`. Si ottiene il seguente output:</span><span class="sxs-lookup"><span data-stu-id="30d31-165">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6029 Seconds
```

<span data-ttu-id="30d31-166">I test hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="30d31-166">Testing passes.</span></span> <span data-ttu-id="30d31-167">I metodi dei tipi di animali da compagnia restituiscono i valori corretti nei messaggi trasmessi al proprietario.</span><span class="sxs-lookup"><span data-stu-id="30d31-167">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="30d31-168">Si sono apprese tecniche per l'organizzazione e il test di progetti con xUnit.</span><span class="sxs-lookup"><span data-stu-id="30d31-168">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="30d31-169">Continuare con queste tecniche applicandole nei propri progetti.</span><span class="sxs-lookup"><span data-stu-id="30d31-169">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="30d31-170">*Buona codifica!*</span><span class="sxs-lookup"><span data-stu-id="30d31-170">*Happy coding!*</span></span>
