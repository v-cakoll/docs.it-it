---
title: Testing unità di F# in .NET Core con il test dotnet e MSTest
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e MSTest.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: a685ed8a56393fb6e1c1b9400f0ed4bcef15f9b5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714269"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a><span data-ttu-id="0199c-103">Testing unità di librerie F# in .NET Core usando il test dotnet e MSTest</span><span class="sxs-lookup"><span data-stu-id="0199c-103">Unit testing F# libraries in .NET Core using dotnet test and MSTest</span></span>

<span data-ttu-id="0199c-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="0199c-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="0199c-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="0199c-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/) before you begin.</span></span> <span data-ttu-id="0199c-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="0199c-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="0199c-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="0199c-107">Creating the source project</span></span>

<span data-ttu-id="0199c-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="0199c-108">Open a shell window.</span></span> <span data-ttu-id="0199c-109">Creare una directory denominata *unit-testing-with-fsharp* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="0199c-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="0199c-110">All'interno di questa nuova directory eseguire `dotnet new sln` per creare una nuova soluzione.</span><span class="sxs-lookup"><span data-stu-id="0199c-110">Inside this new directory, run `dotnet new sln` to create a new solution.</span></span> <span data-ttu-id="0199c-111">Questo rende più semplice gestire sia la libreria di classi che il progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="0199c-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="0199c-112">All'interno della directory della soluzione creare una directory *MathService*.</span><span class="sxs-lookup"><span data-stu-id="0199c-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="0199c-113">La struttura della directory e dei file fino a questo momento è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0199c-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="0199c-114">Rendere *MathService* la directory corrente ed eseguire `dotnet new classlib -lang "F#"` per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="0199c-114">Make *MathService* the current directory and run `dotnet new classlib -lang "F#"` to create the source project.</span></span>  <span data-ttu-id="0199c-115">Si creerà un'implementazione non corretta del servizio matematico:</span><span class="sxs-lookup"><span data-stu-id="0199c-115">You'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="0199c-116">Tornare alla directory *unit-test-con-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="0199c-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="0199c-117">Eseguire `dotnet sln add .\MathService\MathService.fsproj` per aggiungere il progetto libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="0199c-117">Run `dotnet sln add .\MathService\MathService.fsproj` to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="0199c-118">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="0199c-118">Creating the test project</span></span>

<span data-ttu-id="0199c-119">Creare quindi la directory *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="0199c-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="0199c-120">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="0199c-120">The following outline shows the directory structure:</span></span>

```console
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="0199c-121">Rendere la directory *MathService. tests* la directory corrente e creare un nuovo progetto usando `dotnet new mstest -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="0199c-121">Make the *MathService.Tests* directory the current directory and create a new project using `dotnet new mstest -lang "F#"`.</span></span> <span data-ttu-id="0199c-122">Ciò crea un progetto di test che usa MSTest come framework di test.</span><span class="sxs-lookup"><span data-stu-id="0199c-122">This creates a test project that uses MSTest as the test framework.</span></span> <span data-ttu-id="0199c-123">Il modello generato configura il Test Runner nel file *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="0199c-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="0199c-124">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="0199c-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="0199c-125">Nel passaggio precedente `dotnet new` ha aggiunto MSTest e il Runner di MSTest.</span><span class="sxs-lookup"><span data-stu-id="0199c-125">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="0199c-126">Aggiungere ora la libreria di classi `MathService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="0199c-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="0199c-127">Usare il comando `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="0199c-127">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="0199c-128">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="0199c-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="0199c-129">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="0199c-129">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="0199c-130">Eseguire `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` nella directory *Unit-Testing-with-FSharp* .</span><span class="sxs-lookup"><span data-stu-id="0199c-130">Execute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="0199c-131">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="0199c-131">Creating the first test</span></span>

<span data-ttu-id="0199c-132">Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo.</span><span class="sxs-lookup"><span data-stu-id="0199c-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="0199c-133">Aprire *Tests.fs* e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0199c-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

<span data-ttu-id="0199c-134">L'attributo `[<TestClass>]` indica una classe che contiene test.</span><span class="sxs-lookup"><span data-stu-id="0199c-134">The `[<TestClass>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="0199c-135">L'attributo `[<TestMethod>]` indica un metodo di test eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="0199c-135">The `[<TestMethod>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="0199c-136">Dalla directory *Unit-Testing-with-FSharp* eseguire `dotnet test` per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="0199c-136">From the *unit-testing-with-fsharp* directory, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="0199c-137">Il Test Runner di MSTest include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="0199c-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="0199c-138">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="0199c-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="0199c-139">Questi due test mostrano i test più semplici superati e non superati.</span><span class="sxs-lookup"><span data-stu-id="0199c-139">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="0199c-140">`My test` viene superato e `Fail every time` non viene superato.</span><span class="sxs-lookup"><span data-stu-id="0199c-140">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="0199c-141">A questo punto, creare un test per il metodo `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="0199c-141">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="0199c-142">Il metodo `squaresOfOdds` restituisce un elenco di quadrati di tutti i valori interi dispari che fanno parte della sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="0199c-142">The `squaresOfOdds` method returns a list of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="0199c-143">Anziché tentare di scrivere tutte queste funzioni in una sola volta, è possibile creare in modo iterativo test per la convalida della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0199c-143">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="0199c-144">Fare in modo che ogni test venga superato significa creare le funzionalità necessarie per il metodo.</span><span class="sxs-lookup"><span data-stu-id="0199c-144">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="0199c-145">Il test più semplice che si può scrivere consiste nel chiamare `squaresOfOdds` con tutti i numeri pari. In questo caso il risultato dovrebbe essere una sequenza vuota di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="0199c-145">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="0199c-146">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="0199c-146">Here's that test:</span></span>

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="0199c-147">Si noti che la sequenza `expected` è stata convertita in elenco.</span><span class="sxs-lookup"><span data-stu-id="0199c-147">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="0199c-148">La libreria MSTest si basa su molti tipi .NET standard.</span><span class="sxs-lookup"><span data-stu-id="0199c-148">The MSTest library relies on many standard .NET types.</span></span> <span data-ttu-id="0199c-149">Questa dipendenza indica che l'interfaccia pubblica e i risultati previsti supportano <xref:System.Collections.ICollection> invece di <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="0199c-149">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="0199c-150">Quando si esegue il test, si noterà che non viene superato.</span><span class="sxs-lookup"><span data-stu-id="0199c-150">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="0199c-151">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="0199c-151">You haven't created the implementation yet.</span></span> <span data-ttu-id="0199c-152">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `Mathservice`:</span><span class="sxs-lookup"><span data-stu-id="0199c-152">Make this test pass by writing the simplest code in the `Mathservice` class that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="0199c-153">Nella directory *unit-test-con-fsharp* eseguire di nuovo `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="0199c-153">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="0199c-154">Il comando `dotnet test` esegue prima una compilazione del progetto `MathService` e quindi del progetto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="0199c-154">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="0199c-155">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="0199c-155">After building both projects, it runs this single test.</span></span> <span data-ttu-id="0199c-156">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="0199c-156">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="0199c-157">Completamento dei requisiti</span><span class="sxs-lookup"><span data-stu-id="0199c-157">Completing the requirements</span></span>

<span data-ttu-id="0199c-158">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="0199c-158">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="0199c-159">Il prossimo test case semplice opera su una sequenza in cui l'unico numero dispari è `1`.</span><span class="sxs-lookup"><span data-stu-id="0199c-159">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="0199c-160">Il numero 1 è più semplice perché il quadrato di 1 è 1.</span><span class="sxs-lookup"><span data-stu-id="0199c-160">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="0199c-161">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="0199c-161">Here's that next test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="0199c-162">Il nuovo test non viene superato con l'esecuzione di `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="0199c-162">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="0199c-163">È necessario aggiornare il metodo `squaresOfOdds` per gestire il nuovo test.</span><span class="sxs-lookup"><span data-stu-id="0199c-163">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="0199c-164">È necessario filtrare tutti i numeri pari fuori sequenza per fare in modo che il test venga superato.</span><span class="sxs-lookup"><span data-stu-id="0199c-164">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="0199c-165">È possibile farlo scrivendo una breve funzione di filtro e usando `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="0199c-165">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

<span data-ttu-id="0199c-166">Si noti la chiamata a `Seq.toList`,</span><span class="sxs-lookup"><span data-stu-id="0199c-166">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="0199c-167">che crea un elenco che implementa l'interfaccia <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="0199c-167">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="0199c-168">Manca un altro passaggio: elevare al quadrato ciascuno dei numeri di dispari.</span><span class="sxs-lookup"><span data-stu-id="0199c-168">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="0199c-169">Per iniziare, scrivere un nuovo test:</span><span class="sxs-lookup"><span data-stu-id="0199c-169">Start by writing a new test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="0199c-170">È possibile correggere il test tramite il piping della sequenza filtrata attraverso un'operazione di mapping per calcolare il quadrato di ogni numero dispari:</span><span class="sxs-lookup"><span data-stu-id="0199c-170">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="0199c-171">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="0199c-171">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="0199c-172">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0199c-172">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="0199c-173">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0199c-173">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="0199c-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0199c-174">See also</span></span>

- [<span data-ttu-id="0199c-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="0199c-175">dotnet new</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="0199c-176">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="0199c-176">dotnet sln</span></span>](../tools/dotnet-sln.md)
- [<span data-ttu-id="0199c-177">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="0199c-177">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="0199c-178">dotnet test</span><span class="sxs-lookup"><span data-stu-id="0199c-178">dotnet test</span></span>](../tools/dotnet-test.md)
