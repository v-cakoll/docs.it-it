---
title: Testing unità di Visual Basic in .NET Core con il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di Visual Basic di esempio con test dotnet e xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 05/18/2020
ms.openlocfilehash: d87550d692e0b7f3bfee1633bd00cbf501cc2e67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502756"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a><span data-ttu-id="6d710-103">Testing unità di librerie .NET Core di Visual Basic usando il test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="6d710-103">Unit testing Visual Basic .NET Core libraries using dotnet test and xUnit</span></span>

<span data-ttu-id="6d710-104">Questa esercitazione illustra come compilare una soluzione contenente un progetto unit test e un progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="6d710-104">This tutorial shows how to build a solution containing a unit test project and library project.</span></span> <span data-ttu-id="6d710-105">Per seguire l'esercitazione usando una soluzione predefinita, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/).</span><span class="sxs-lookup"><span data-stu-id="6d710-105">To follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/).</span></span> <span data-ttu-id="6d710-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="6d710-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="6d710-107">Creare la soluzione</span><span class="sxs-lookup"><span data-stu-id="6d710-107">Create the solution</span></span>

<span data-ttu-id="6d710-108">In questa sezione viene creata una soluzione che contiene i progetti di origine e di test.</span><span class="sxs-lookup"><span data-stu-id="6d710-108">In this section, a solution is created that contains the source and test projects.</span></span> <span data-ttu-id="6d710-109">La soluzione completa presenta la struttura di directory seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-109">The completed solution has the following directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.vb
        PrimeService.vbproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.vb
        PrimeServiceTests.vbproj
```

<span data-ttu-id="6d710-110">Le istruzioni seguenti forniscono i passaggi per creare la soluzione di test.</span><span class="sxs-lookup"><span data-stu-id="6d710-110">The following instructions provide the steps to create the test solution.</span></span> <span data-ttu-id="6d710-111">Per istruzioni su come creare la soluzione di test in un unico passaggio, vedere [comandi per creare una soluzione di test](#create-test-cmd) .</span><span class="sxs-lookup"><span data-stu-id="6d710-111">See [Commands to create test solution](#create-test-cmd) for instructions to create the test solution in one step.</span></span>

* <span data-ttu-id="6d710-112">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="6d710-112">Open a shell window.</span></span>
* <span data-ttu-id="6d710-113">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-113">Run the following command:</span></span>

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  <span data-ttu-id="6d710-114">Il [`dotnet new sln`](../tools/dotnet-new.md) comando crea una nuova soluzione nella directory *unit-testing-using-DotNet-test* .</span><span class="sxs-lookup"><span data-stu-id="6d710-114">The [`dotnet new sln`](../tools/dotnet-new.md) command creates a new solution in the *unit-testing-using-dotnet-test* directory.</span></span>
* <span data-ttu-id="6d710-115">Passare alla cartella *unit-testing-using-DotNet-test* .</span><span class="sxs-lookup"><span data-stu-id="6d710-115">Change directory to the *unit-testing-using-dotnet-test* folder.</span></span>
* <span data-ttu-id="6d710-116">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-116">Run the following command:</span></span>

  ```dotnetcli
  dotnet new classlib -o PrimeService --lang VB
  ```

   <span data-ttu-id="6d710-117">Il [`dotnet new classlib`](../tools/dotnet-new.md) comando crea un nuovo progetto libreria di classi nella cartella *PrimeService* .</span><span class="sxs-lookup"><span data-stu-id="6d710-117">The [`dotnet new classlib`](../tools/dotnet-new.md) command creates a new class library project  in the *PrimeService* folder.</span></span> <span data-ttu-id="6d710-118">La nuova libreria di classi conterrà il codice da testare.</span><span class="sxs-lookup"><span data-stu-id="6d710-118">The new class library will contain the code to be tested.</span></span>
* <span data-ttu-id="6d710-119">Rinominare *Class1. vb* in *PrimeService. vb*.</span><span class="sxs-lookup"><span data-stu-id="6d710-119">Rename *Class1.vb* to *PrimeService.vb*.</span></span>
* <span data-ttu-id="6d710-120">Sostituire il codice in *PrimeService. vb* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-120">Replace the code in *PrimeService.vb* with the following code:</span></span>
  
  ```vb
  Imports System
  
  Namespace Prime.Services
      Public Class PrimeService
          Public Function IsPrime(candidate As Integer) As Boolean
              Throw New NotImplementedException("Not implemented.")
          End Function
      End Class
  End Namespace
  ```

* <span data-ttu-id="6d710-121">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="6d710-121">The preceding code:</span></span>
  * <span data-ttu-id="6d710-122">Genera un'eccezione <xref:System.NotImplementedException> con un messaggio che indica che non è implementato.</span><span class="sxs-lookup"><span data-stu-id="6d710-122">Throws a <xref:System.NotImplementedException> with a message indicating it's not implemented.</span></span>
  * <span data-ttu-id="6d710-123">Viene aggiornato più avanti nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="6d710-123">Is updated later in the tutorial.</span></span>

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* <span data-ttu-id="6d710-124">Nella directory *unit-testing-using-DotNet-test* eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="6d710-124">In the *unit-testing-using-dotnet-test* directory, run the following command to add the class library project to the solution:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.vbproj
  ```

* <span data-ttu-id="6d710-125">Creare il progetto *PrimeService. tests* eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-125">Create the *PrimeService.Tests* project by running the following command:</span></span>

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* <span data-ttu-id="6d710-126">Il comando precedente:</span><span class="sxs-lookup"><span data-stu-id="6d710-126">The preceding command:</span></span>
  * <span data-ttu-id="6d710-127">Crea il progetto *PrimeService. tests* nella directory *PrimeService. tests* .</span><span class="sxs-lookup"><span data-stu-id="6d710-127">Creates the *PrimeService.Tests* project in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="6d710-128">Il progetto di test USA [xUnit](https://xunit.net/) come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="6d710-128">The test project uses [xUnit](https://xunit.net/) as the test library.</span></span>
  * <span data-ttu-id="6d710-129">Configura il test runner aggiungendo gli `<PackageReference />` elementi seguenti al file di progetto:</span><span class="sxs-lookup"><span data-stu-id="6d710-129">Configures the test runner by adding the following `<PackageReference />`elements to the project file:</span></span>
    * <span data-ttu-id="6d710-130">"Microsoft. NET. test. SDK"</span><span class="sxs-lookup"><span data-stu-id="6d710-130">"Microsoft.NET.Test.Sdk"</span></span>
    * <span data-ttu-id="6d710-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="6d710-131">"xunit"</span></span>
    * <span data-ttu-id="6d710-132">"xUnit. Runner. VisualStudio"</span><span class="sxs-lookup"><span data-stu-id="6d710-132">"xunit.runner.visualstudio"</span></span>

* <span data-ttu-id="6d710-133">Aggiungere il progetto di test al file di soluzione eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-133">Add the test project to the solution file by running the following command:</span></span>

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
  ```

* <span data-ttu-id="6d710-134">Aggiungere la `PrimeService` libreria di classi come dipendenza al progetto *PrimeService. tests* :</span><span class="sxs-lookup"><span data-stu-id="6d710-134">Add the `PrimeService` class library as a dependency to the *PrimeService.Tests* project:</span></span>

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a><span data-ttu-id="6d710-135">Comandi per creare la soluzione</span><span class="sxs-lookup"><span data-stu-id="6d710-135">Commands to create the solution</span></span>

<span data-ttu-id="6d710-136">In questa sezione vengono riepilogati tutti i comandi della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="6d710-136">This section summarizes all the commands in the previous section.</span></span> <span data-ttu-id="6d710-137">Ignorare questa sezione se è stata completata la procedura descritta nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="6d710-137">Skip this section if you've completed the steps in the previous section.</span></span>

<span data-ttu-id="6d710-138">I comandi seguenti creano la soluzione di test in un computer Windows.</span><span class="sxs-lookup"><span data-stu-id="6d710-138">The following commands create the test solution on a windows machine.</span></span> <span data-ttu-id="6d710-139">Per macOS e UNIX, aggiornare il `ren` comando alla versione del sistema operativo di `ren` per rinominare un file:</span><span class="sxs-lookup"><span data-stu-id="6d710-139">For macOS and Unix, update the `ren` command to the OS version of `ren` to rename a file:</span></span>

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.vb PrimeService.vb
dotnet sln add ./PrimeService/PrimeService.vbproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
```

<span data-ttu-id="6d710-140">Seguire le istruzioni per "sostituire il codice in *PrimeService. vb* con il codice seguente" nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="6d710-140">Follow the instructions for "Replace the code in *PrimeService.vb* with the following code" in the previous section.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="6d710-141">Creare un test</span><span class="sxs-lookup"><span data-stu-id="6d710-141">Create a test</span></span>

<span data-ttu-id="6d710-142">Un approccio comune nello sviluppo basato su test (TDD) consiste nel scrivere un test prima di implementare il codice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6d710-142">A popular approach in test driven development (TDD) is to write a test before implementing the target code.</span></span> <span data-ttu-id="6d710-143">Questa esercitazione usa l'approccio TDD.</span><span class="sxs-lookup"><span data-stu-id="6d710-143">This tutorial uses the TDD approach.</span></span> <span data-ttu-id="6d710-144">Il `IsPrime` metodo è chiamabile, ma non è implementato.</span><span class="sxs-lookup"><span data-stu-id="6d710-144">The `IsPrime` method is callable, but not implemented.</span></span> <span data-ttu-id="6d710-145">Una chiamata di test a ha `IsPrime` esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6d710-145">A test call to `IsPrime` fails.</span></span> <span data-ttu-id="6d710-146">Con TDD, viene scritto un test noto come non riuscito.</span><span class="sxs-lookup"><span data-stu-id="6d710-146">With TDD, a test is written that is known to fail.</span></span> <span data-ttu-id="6d710-147">Il codice di destinazione viene aggiornato per fare in modo che il test venga superato.</span><span class="sxs-lookup"><span data-stu-id="6d710-147">The target code is updated to make the test pass.</span></span> <span data-ttu-id="6d710-148">Si continua a ripetere questo approccio, scrivendo un test con esito negativo e quindi aggiornando il codice di destinazione da passare.</span><span class="sxs-lookup"><span data-stu-id="6d710-148">You keep repeating this approach, writing a failing test and then updating the target code to pass.</span></span>

<span data-ttu-id="6d710-149">Aggiornare il progetto *PrimeService. tests* :</span><span class="sxs-lookup"><span data-stu-id="6d710-149">Update the *PrimeService.Tests* project:</span></span>

* <span data-ttu-id="6d710-150">Eliminare *PrimeService. tests/UnitTest1. vb*.</span><span class="sxs-lookup"><span data-stu-id="6d710-150">Delete *PrimeService.Tests/UnitTest1.vb*.</span></span>
* <span data-ttu-id="6d710-151">Creare un file *PrimeService. tests/PrimeService_IsPrimeShould. vb* .</span><span class="sxs-lookup"><span data-stu-id="6d710-151">Create a *PrimeService.Tests/PrimeService_IsPrimeShould.vb*  file.</span></span>
* <span data-ttu-id="6d710-152">Sostituire il codice in *PrimeService_IsPrimeShould. vb* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-152">Replace the code in *PrimeService_IsPrimeShould.vb* with the following code:</span></span>

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private ReadOnly _primeService As Prime.Services.PrimeService

        Public Sub New()
            _primeService = New Prime.Services.PrimeService()
        End Sub


        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="6d710-153">L' `[Fact]` attributo dichiara un metodo di test eseguito dal test runner.</span><span class="sxs-lookup"><span data-stu-id="6d710-153">The `[Fact]` attribute declares a test method that's run by the test runner.</span></span> <span data-ttu-id="6d710-154">Dalla cartella *PrimeService. tests* eseguire `dotnet test` .</span><span class="sxs-lookup"><span data-stu-id="6d710-154">From the *PrimeService.Tests* folder, run `dotnet test`.</span></span> <span data-ttu-id="6d710-155">Il comando [DotNet test](../tools/dotnet-test.md) Compila entrambi i progetti ed esegue i test.</span><span class="sxs-lookup"><span data-stu-id="6d710-155">The [dotnet test](../tools/dotnet-test.md) command builds both projects and runs the tests.</span></span> <span data-ttu-id="6d710-156">XUnit Test Runner contiene il punto di ingresso del programma per eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="6d710-156">The xUnit test runner contains the program entry point to run the tests.</span></span> <span data-ttu-id="6d710-157">`dotnet test`avvia il test runner utilizzando il progetto unit test.</span><span class="sxs-lookup"><span data-stu-id="6d710-157">`dotnet test` starts the test runner using the unit test project.</span></span>

<span data-ttu-id="6d710-158">Il test non riesce perché `IsPrime` non è stato implementato.</span><span class="sxs-lookup"><span data-stu-id="6d710-158">The test fails because `IsPrime` hasn't been implemented.</span></span> <span data-ttu-id="6d710-159">Utilizzando l'approccio TDD, scrivere solo codice sufficiente per consentire il superamento del test.</span><span class="sxs-lookup"><span data-stu-id="6d710-159">Using the TDD approach, write only enough code so this test passes.</span></span> <span data-ttu-id="6d710-160">Aggiornare `IsPrime` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-160">Update `IsPrime` with the following code:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Not implemented.")
End Function
```

<span data-ttu-id="6d710-161">Eseguire `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="6d710-161">Run `dotnet test`.</span></span> <span data-ttu-id="6d710-162">Il test viene superato.</span><span class="sxs-lookup"><span data-stu-id="6d710-162">The test passes.</span></span>

### <a name="add-more-tests"></a><span data-ttu-id="6d710-163">Aggiungi altri test</span><span class="sxs-lookup"><span data-stu-id="6d710-163">Add more tests</span></span>

<span data-ttu-id="6d710-164">Aggiungere i test dei numeri primi per 0 e-1.</span><span class="sxs-lookup"><span data-stu-id="6d710-164">Add prime number tests for 0 and -1.</span></span> <span data-ttu-id="6d710-165">È possibile copiare il test precedente e modificare il codice seguente per usare 0 e-1:</span><span class="sxs-lookup"><span data-stu-id="6d710-165">You could copy the preceding test and change the following code to use 0 and -1:</span></span>

```vb
Dim result As Boolean = _primeService.IsPrime(1)

Assert.False(result, "1 should not be prime")
```

<span data-ttu-id="6d710-166">La copia del codice di test quando solo un parametro cambia causa la duplicazione del codice e il sovraccarico dei test.</span><span class="sxs-lookup"><span data-stu-id="6d710-166">Copying test code when only a parameter changes results in code duplication and test bloat.</span></span> <span data-ttu-id="6d710-167">Gli attributi xUnit seguenti consentono di scrivere una suite di test simili:</span><span class="sxs-lookup"><span data-stu-id="6d710-167">The following xUnit attributes enable writing a suite of similar tests:</span></span>

- <span data-ttu-id="6d710-168">`[Theory]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="6d710-168">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>
- <span data-ttu-id="6d710-169">L'attributo `[InlineData]` specifica i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="6d710-169">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="6d710-170">Anziché creare nuovi test, applicare gli attributi xUnit precedenti per creare una singola teoria.</span><span class="sxs-lookup"><span data-stu-id="6d710-170">Rather than creating new tests, apply the preceding xUnit attributes to create a single theory.</span></span> <span data-ttu-id="6d710-171">Sostituire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-171">Replace the following code:</span></span>

```vb
<Fact>
Sub IsPrime_InputIs1_ReturnFalse()
    Dim result As Boolean = _primeService.IsPrime(1)

    Assert.False(result, "1 should not be prime")
End Sub
```

<span data-ttu-id="6d710-172">con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-172">with the following code:</span></span>

```vb
<Theory>
<InlineData(-1)>
<InlineData(0)>
<InlineData(1)>
Sub IsPrime_ValuesLessThan2_ReturnFalse(ByVal value As Integer)
    Dim result As Boolean = _primeService.IsPrime(value)

    Assert.False(result, $"{value} should not be prime")
End Sub
```

<span data-ttu-id="6d710-173">Nel codice precedente, `[Theory]` e `[InlineData]` consentono di testare diversi valori minori di due.</span><span class="sxs-lookup"><span data-stu-id="6d710-173">In the preceding code, `[Theory]` and `[InlineData]` enable testing several values less than two.</span></span> <span data-ttu-id="6d710-174">Due è il numero primo più piccolo.</span><span class="sxs-lookup"><span data-stu-id="6d710-174">Two is the smallest prime number.</span></span>

<span data-ttu-id="6d710-175">Eseguire `dotnet test` , due dei test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6d710-175">Run `dotnet test`, two of the tests fail.</span></span> <span data-ttu-id="6d710-176">Per far passare tutti i test, aggiornare il `IsPrime` metodo con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d710-176">To make all of the tests pass, update the `IsPrime` method with the following code:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate < 2 Then
        Return False
    End If
    Throw New NotImplementedException("Not fully implemented.")
End Function
```

<span data-ttu-id="6d710-177">Seguendo l'approccio di TDD, aggiungere altri test non superati, quindi aggiornare il codice di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6d710-177">Following the TDD approach, add more failing tests, then update the target code.</span></span> <span data-ttu-id="6d710-178">Vedere la [versione completa dei test](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) e l' [implementazione completa della libreria](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="6d710-178">See the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="6d710-179">Il `IsPrime` metodo Completed non è un algoritmo efficiente per il test di primalità.</span><span class="sxs-lookup"><span data-stu-id="6d710-179">The completed `IsPrime` method is not an efficient algorithm for testing primality.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="6d710-180">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6d710-180">Additional resources</span></span>

- [<span data-ttu-id="6d710-181">Sito ufficiale xUnit.net</span><span class="sxs-lookup"><span data-stu-id="6d710-181">xUnit.net official site</span></span>](https://xunit.net/)
- [<span data-ttu-id="6d710-182">Test della logica dei controller in ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6d710-182">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
