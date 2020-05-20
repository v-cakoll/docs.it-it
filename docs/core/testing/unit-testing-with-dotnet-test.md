---
title: Testing unità di codice C# in .NET Core usando il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in C# e .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: d8cf0e29c8a482b39bd7e99bcde1fd60301f046f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702942"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="97025-103">Testing unità di C# in .NET Core usando il test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="97025-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="97025-104">Questa esercitazione illustra come compilare una soluzione contenente un progetto unit test e un progetto di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="97025-104">This tutorial shows how to build a solution containing a unit test project and source code project.</span></span> <span data-ttu-id="97025-105">Per seguire l'esercitazione usando una soluzione predefinita, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/).</span><span class="sxs-lookup"><span data-stu-id="97025-105">To follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/).</span></span> <span data-ttu-id="97025-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="97025-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="97025-107">Creare la soluzione</span><span class="sxs-lookup"><span data-stu-id="97025-107">Create the solution</span></span>

<span data-ttu-id="97025-108">In questa sezione viene creata una soluzione che contiene i progetti di origine e di test.</span><span class="sxs-lookup"><span data-stu-id="97025-108">In this section, a solution is created that contains the source and test projects.</span></span> <span data-ttu-id="97025-109">La soluzione completa presenta la struttura di directory seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-109">The completed solution has the following directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.cs
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.cs
        PrimeServiceTests.csproj
```

<span data-ttu-id="97025-110">Le istruzioni seguenti forniscono i passaggi per creare la soluzione di test.</span><span class="sxs-lookup"><span data-stu-id="97025-110">The following instructions provide the steps to create the test solution.</span></span> <span data-ttu-id="97025-111">Per istruzioni su come creare la soluzione di test in un unico passaggio, vedere [comandi per creare una soluzione di test](#create-test-cmd) .</span><span class="sxs-lookup"><span data-stu-id="97025-111">See [Commands to create test solution](#create-test-cmd) for instructions to create the test solution in one step.</span></span>

* <span data-ttu-id="97025-112">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="97025-112">Open a shell window.</span></span>
* <span data-ttu-id="97025-113">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-113">Run the following command:</span></span>

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  <span data-ttu-id="97025-114">Il [`dotnet new sln`](../tools/dotnet-new.md) comando crea una nuova soluzione nella directory *unit-testing-using-DotNet-test* .</span><span class="sxs-lookup"><span data-stu-id="97025-114">The [`dotnet new sln`](../tools/dotnet-new.md) command creates a new solution in the *unit-testing-using-dotnet-test* directory.</span></span>
* <span data-ttu-id="97025-115">Passare alla cartella *unit-testing-using-DotNet-test* .</span><span class="sxs-lookup"><span data-stu-id="97025-115">Change directory to the *unit-testing-using-dotnet-test* folder.</span></span>
* <span data-ttu-id="97025-116">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-116">Run the following command:</span></span>

  ```dotnetcli
  dotnet new classlib -o PrimeService
  ```

   <span data-ttu-id="97025-117">Il [`dotnet new classlib`](../tools/dotnet-new.md) comando crea un nuovo progetto libreria di classi nella cartella *PrimeService* .</span><span class="sxs-lookup"><span data-stu-id="97025-117">The [`dotnet new classlib`](../tools/dotnet-new.md) command creates a new class library project  in the *PrimeService* folder.</span></span> <span data-ttu-id="97025-118">La nuova libreria di classi conterrà il codice da testare.</span><span class="sxs-lookup"><span data-stu-id="97025-118">The new class library will contain the code to be tested.</span></span>
* <span data-ttu-id="97025-119">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="97025-119">Rename *Class1.cs* to *PrimeService.cs*.</span></span>
* <span data-ttu-id="97025-120">Sostituire il codice in *PrimeService.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-120">Replace the code in *PrimeService.cs* with the following code:</span></span>
  
  ```csharp
  using System;

  namespace Prime.Services
  {
      public class PrimeService
      {
          public bool IsPrime(int candidate)
          {
              throw new NotImplementedException("Not implemented.");
          }
      }
  }
  ```

* <span data-ttu-id="97025-121">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="97025-121">The preceding code:</span></span>
  * <span data-ttu-id="97025-122">Genera un'eccezione <xref:System.NotImplementedException> con un messaggio che indica che non è implementato.</span><span class="sxs-lookup"><span data-stu-id="97025-122">Throws a <xref:System.NotImplementedException> with a message indicating it's not implemented.</span></span>
  * <span data-ttu-id="97025-123">Viene aggiornato più avanti nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="97025-123">Is updated later in the tutorial.</span></span>

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* <span data-ttu-id="97025-124">Nella directory *unit-testing-using-DotNet-test* eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="97025-124">In the *unit-testing-using-dotnet-test* directory, run the following command to add the class library project to the solution:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.csproj
  ```

* <span data-ttu-id="97025-125">Creare il progetto *PrimeService. tests* eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-125">Create the *PrimeService.Tests* project by running the following command:</span></span>

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* <span data-ttu-id="97025-126">Il comando precedente:</span><span class="sxs-lookup"><span data-stu-id="97025-126">The preceding command:</span></span>
  * <span data-ttu-id="97025-127">Crea il progetto *PrimeService. tests* nella directory *PrimeService. tests* .</span><span class="sxs-lookup"><span data-stu-id="97025-127">Creates the *PrimeService.Tests* project in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="97025-128">Il progetto di test USA [xUnit](https://xunit.net/) come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="97025-128">The test project uses [xUnit](https://xunit.net/) as the test library.</span></span>
  * <span data-ttu-id="97025-129">Configura il test runner aggiungendo gli `<PackageReference />` elementi seguenti al file di progetto:</span><span class="sxs-lookup"><span data-stu-id="97025-129">Configures the test runner by adding the following `<PackageReference />`elements to the project file:</span></span>
    * <span data-ttu-id="97025-130">"Microsoft. NET. test. SDK"</span><span class="sxs-lookup"><span data-stu-id="97025-130">"Microsoft.NET.Test.Sdk"</span></span>
    * <span data-ttu-id="97025-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="97025-131">"xunit"</span></span>
    * <span data-ttu-id="97025-132">"xUnit. Runner. VisualStudio"</span><span class="sxs-lookup"><span data-stu-id="97025-132">"xunit.runner.visualstudio"</span></span>

* <span data-ttu-id="97025-133">Aggiungere il progetto di test al file di soluzione eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-133">Add the test project to the solution file by running the following command:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
  ```

* <span data-ttu-id="97025-134">Aggiungere la `PrimeService` libreria di classi come dipendenza al progetto *PrimeService. tests* :</span><span class="sxs-lookup"><span data-stu-id="97025-134">Add the `PrimeService` class library as a dependency to the *PrimeService.Tests* project:</span></span>

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a><span data-ttu-id="97025-135">Comandi per creare la soluzione</span><span class="sxs-lookup"><span data-stu-id="97025-135">Commands to create the solution</span></span>

<span data-ttu-id="97025-136">In questa sezione vengono riepilogati tutti i comandi della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="97025-136">This section summarizes all the commands in the previous section.</span></span> <span data-ttu-id="97025-137">Ignorare questa sezione se è stata completata la procedura descritta nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="97025-137">Skip this section if you've completed the steps in the previous section.</span></span>

<span data-ttu-id="97025-138">I comandi seguenti creano la soluzione di test in un computer Windows.</span><span class="sxs-lookup"><span data-stu-id="97025-138">The following commands create the test solution on a windows machine.</span></span> <span data-ttu-id="97025-139">Per macOS e UNIX, aggiornare il `ren` comando alla versione del sistema operativo di `ren` per rinominare un file:</span><span class="sxs-lookup"><span data-stu-id="97025-139">For macOS and Unix, update the `ren` command to the OS version of `ren` to rename a file:</span></span>

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.cs PrimeService.cs
dotnet sln add ./PrimeService/PrimeService.csproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

<span data-ttu-id="97025-140">Seguire le istruzioni per "sostituire il codice in *PrimeService.cs* con il codice seguente" nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="97025-140">Follow the instructions for "Replace the code in *PrimeService.cs* with the following code" in the previous section.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="97025-141">Creare un test</span><span class="sxs-lookup"><span data-stu-id="97025-141">Create a test</span></span>

<span data-ttu-id="97025-142">Un approccio comune nello sviluppo basato su test (TDD) consiste nel scrivere un test prima di implementare il codice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="97025-142">A popular approach in test driven development (TDD) is to write a test before implementing the target code.</span></span> <span data-ttu-id="97025-143">Questa esercitazione usa l'approccio TDD.</span><span class="sxs-lookup"><span data-stu-id="97025-143">This tutorial uses the TDD approach.</span></span> <span data-ttu-id="97025-144">Il `IsPrime` metodo è chiamabile, ma non è implementato.</span><span class="sxs-lookup"><span data-stu-id="97025-144">The `IsPrime` method is callable, but not implemented.</span></span> <span data-ttu-id="97025-145">Una chiamata di test a ha `IsPrime` esito negativo.</span><span class="sxs-lookup"><span data-stu-id="97025-145">A test call to `IsPrime` fails.</span></span> <span data-ttu-id="97025-146">Con TDD, viene scritto un test noto come non riuscito.</span><span class="sxs-lookup"><span data-stu-id="97025-146">With TDD, a test is written that is known to fail.</span></span> <span data-ttu-id="97025-147">Il codice di destinazione viene aggiornato per fare in modo che il test venga superato.</span><span class="sxs-lookup"><span data-stu-id="97025-147">The target code is updated to make the test pass.</span></span> <span data-ttu-id="97025-148">Si continua a ripetere questo approccio, scrivendo un test con esito negativo e quindi aggiornando il codice di destinazione da passare.</span><span class="sxs-lookup"><span data-stu-id="97025-148">You keep repeating this approach, writing a failing test and then updating the target code to pass.</span></span>

<span data-ttu-id="97025-149">Aggiornare il progetto *PrimeService. tests* :</span><span class="sxs-lookup"><span data-stu-id="97025-149">Update the *PrimeService.Tests* project:</span></span>

* <span data-ttu-id="97025-150">Eliminare *PrimeService. tests/UnitTest1. cs*.</span><span class="sxs-lookup"><span data-stu-id="97025-150">Delete *PrimeService.Tests/UnitTest1.cs*.</span></span>
* <span data-ttu-id="97025-151">Creare un file *PrimeService. tests/PrimeService_IsPrimeShould. cs* .</span><span class="sxs-lookup"><span data-stu-id="97025-151">Create a *PrimeService.Tests/PrimeService_IsPrimeShould.cs*  file.</span></span>
* <span data-ttu-id="97025-152">Sostituire il codice in *PrimeService_IsPrimeShould. cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-152">Replace the code in *PrimeService_IsPrimeShould.cs* with the following code:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="97025-153">L' `[Fact]` attributo dichiara un metodo di test eseguito dal test runner.</span><span class="sxs-lookup"><span data-stu-id="97025-153">The `[Fact]` attribute declares a test method that's run by the test runner.</span></span> <span data-ttu-id="97025-154">Dalla cartella *PrimeService. tests* eseguire `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="97025-154">From the *PrimeService.Tests* folder, run `dotnet test`.</span></span> <span data-ttu-id="97025-155">Il comando [DotNet test](../tools/dotnet-test.md) Compila entrambi i progetti ed esegue i test.</span><span class="sxs-lookup"><span data-stu-id="97025-155">The [dotnet test](../tools/dotnet-test.md) command builds both projects and runs the tests.</span></span> <span data-ttu-id="97025-156">XUnit Test Runner contiene il punto di ingresso del programma per eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="97025-156">The xUnit test runner contains the program entry point to run the tests.</span></span> <span data-ttu-id="97025-157">`dotnet test`avvia il test runner utilizzando il progetto unit test.</span><span class="sxs-lookup"><span data-stu-id="97025-157">`dotnet test` starts the test runner using the unit test project.</span></span>

<span data-ttu-id="97025-158">Il test non riesce perché `IsPrime` non è stato implementato.</span><span class="sxs-lookup"><span data-stu-id="97025-158">The test fails because `IsPrime` hasn't been implemented.</span></span> <span data-ttu-id="97025-159">Utilizzando l'approccio TDD, scrivere solo codice sufficiente per consentire il superamento del test.</span><span class="sxs-lookup"><span data-stu-id="97025-159">Using the TDD approach, write only enough code so this test passes.</span></span> <span data-ttu-id="97025-160">Aggiornare `IsPrime` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-160">Update `IsPrime` with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

<span data-ttu-id="97025-161">Eseguire `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="97025-161">Run `dotnet test`.</span></span> <span data-ttu-id="97025-162">Il test viene superato.</span><span class="sxs-lookup"><span data-stu-id="97025-162">The test passes.</span></span>

### <a name="add-more-tests"></a><span data-ttu-id="97025-163">Aggiungi altri test</span><span class="sxs-lookup"><span data-stu-id="97025-163">Add more tests</span></span>

<span data-ttu-id="97025-164">Aggiungere i test dei numeri primi per 0 e-1.</span><span class="sxs-lookup"><span data-stu-id="97025-164">Add prime number tests for 0 and -1.</span></span> <span data-ttu-id="97025-165">È possibile copiare il test precedente e modificare il codice seguente per usare 0 e-1:</span><span class="sxs-lookup"><span data-stu-id="97025-165">You could copy the preceding test and change the following code to use 0 and -1:</span></span>

```csharp
var result = _primeService.IsPrime(1);

Assert.False(result, "1 should not be prime");
```

<span data-ttu-id="97025-166">La copia del codice di test quando solo un parametro cambia causa la duplicazione del codice e il sovraccarico dei test.</span><span class="sxs-lookup"><span data-stu-id="97025-166">Copying test code when only a parameter changes results in code duplication and test bloat.</span></span> <span data-ttu-id="97025-167">Gli attributi xUnit seguenti consentono di scrivere una suite di test simili:</span><span class="sxs-lookup"><span data-stu-id="97025-167">The following xUnit attributes enable writing a suite of similar tests:</span></span>

- <span data-ttu-id="97025-168">`[Theory]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="97025-168">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>
- <span data-ttu-id="97025-169">L'attributo `[InlineData]` specifica i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="97025-169">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="97025-170">Anziché creare nuovi test, applicare gli attributi xUnit precedenti per creare una singola teoria.</span><span class="sxs-lookup"><span data-stu-id="97025-170">Rather than creating new tests, apply the preceding xUnit attributes to create a single theory.</span></span> <span data-ttu-id="97025-171">Sostituire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-171">Replace the following code:</span></span>

```csharp
[Fact]
public void IsPrime_InputIs1_ReturnFalse()
{
    var result = _primeService.IsPrime(1);

    Assert.False(result, "1 should not be prime");
}
```

<span data-ttu-id="97025-172">con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-172">with the following code:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-dotnet-test/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="97025-173">Nel codice precedente, `[Theory]` e `[InlineData]` consentono di testare diversi valori minori di due.</span><span class="sxs-lookup"><span data-stu-id="97025-173">In the preceding code, `[Theory]` and `[InlineData]` enable testing several values less than two.</span></span> <span data-ttu-id="97025-174">Due è il numero primo più piccolo.</span><span class="sxs-lookup"><span data-stu-id="97025-174">Two is the smallest prime number.</span></span>

<span data-ttu-id="97025-175">Eseguire `dotnet test` , due dei test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="97025-175">Run `dotnet test`, two of the tests fail.</span></span> <span data-ttu-id="97025-176">Per far passare tutti i test, aggiornare il `IsPrime` metodo con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="97025-176">To make all of the tests pass, update the `IsPrime` method with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate < 2)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

<span data-ttu-id="97025-177">Seguendo l'approccio di TDD, aggiungere altri test non superati, quindi aggiornare il codice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="97025-177">Following the TDD approach, add more failing tests, then update the target code.</span></span> <span data-ttu-id="97025-178">Vedere la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l' [implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="97025-178">See the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="97025-179">Il `IsPrime` metodo Completed non è un algoritmo efficiente per il test di primalità.</span><span class="sxs-lookup"><span data-stu-id="97025-179">The completed `IsPrime` method is not an efficient algorithm for testing primality.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="97025-180">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="97025-180">Additional resources</span></span>

- [<span data-ttu-id="97025-181">Sito ufficiale xUnit.net</span><span class="sxs-lookup"><span data-stu-id="97025-181">xUnit.net official site</span></span>](https://xunit.net)
- [<span data-ttu-id="97025-182">Test della logica dei controller in ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97025-182">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
