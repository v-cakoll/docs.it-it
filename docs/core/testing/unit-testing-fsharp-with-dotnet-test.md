---
title: Testing unità di F# in .NET Core con il test dotnet e xUnit
description: Informazioni sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e xUnit.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 5fe4a8faddd87334439513368f24d808abc58e65
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157310"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="ce72d-103">Testing unità di librerie F# in .NET Core usando il test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="ce72d-103">Unit testing F# libraries in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="ce72d-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="ce72d-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="ce72d-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="ce72d-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) before you begin.</span></span> <span data-ttu-id="ce72d-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="ce72d-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="ce72d-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="ce72d-107">Creating the source project</span></span>

<span data-ttu-id="ce72d-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="ce72d-108">Open a shell window.</span></span> <span data-ttu-id="ce72d-109">Creare una directory denominata *unit-testing-with-fsharp* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ce72d-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="ce72d-110">In questa nuova directory eseguire `dotnet new sln` per creare una nuova soluzione.</span><span class="sxs-lookup"><span data-stu-id="ce72d-110">Inside this new directory, run `dotnet new sln` to create a new solution.</span></span> <span data-ttu-id="ce72d-111">Questo rende più semplice gestire sia la libreria di classi che il progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="ce72d-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="ce72d-112">All'interno della directory della soluzione creare una directory *MathService*.</span><span class="sxs-lookup"><span data-stu-id="ce72d-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="ce72d-113">La struttura della directory e dei file fino a questo momento è la seguente:</span><span class="sxs-lookup"><span data-stu-id="ce72d-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="ce72d-114">Impostare *MathService* come directory `dotnet new classlib -lang "F#"` corrente ed eseguire per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="ce72d-114">Make *MathService* the current directory, and run `dotnet new classlib -lang "F#"` to create the source project.</span></span> <span data-ttu-id="ce72d-115">Si creerà un'implementazione non corretta del servizio matematico:</span><span class="sxs-lookup"><span data-stu-id="ce72d-115">You'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="ce72d-116">Tornare alla directory *unit-test-con-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="ce72d-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="ce72d-117">Eseguire `dotnet sln add .\MathService\MathService.fsproj` per aggiungere il progetto di libreria di classi alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="ce72d-117">Run `dotnet sln add .\MathService\MathService.fsproj` to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="ce72d-118">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="ce72d-118">Creating the test project</span></span>

<span data-ttu-id="ce72d-119">Creare quindi la directory *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="ce72d-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="ce72d-120">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="ce72d-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="ce72d-121">Impostare *MathService.Tests* come directory corrente e creare un nuovo progetto usando `dotnet new xunit -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="ce72d-121">Make the *MathService.Tests* directory the current directory and create a new project using `dotnet new xunit -lang "F#"`.</span></span> <span data-ttu-id="ce72d-122">In questo modo viene creato un progetto di test che usa xUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="ce72d-122">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="ce72d-123">Il modello generato configura il Test Runner nel file *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="ce72d-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="ce72d-124">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="ce72d-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="ce72d-125">Nel passaggio precedente `dotnet new` ha aggiunto xUnit e il Runner di xUnit.</span><span class="sxs-lookup"><span data-stu-id="ce72d-125">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="ce72d-126">Aggiungere ora la libreria di classi `MathService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="ce72d-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="ce72d-127">Utilizzare `dotnet add reference` il comando:</span><span class="sxs-lookup"><span data-stu-id="ce72d-127">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="ce72d-128">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="ce72d-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="ce72d-129">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ce72d-129">You have the following final solution layout:</span></span>

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

<span data-ttu-id="ce72d-130">Eseguire `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` nella directory *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="ce72d-130">Execute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="ce72d-131">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="ce72d-131">Creating the first test</span></span>

<span data-ttu-id="ce72d-132">Scrivere un test che genera errore, fare in modo che venga superato e quindi ripetere il processo.</span><span class="sxs-lookup"><span data-stu-id="ce72d-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="ce72d-133">Aprire *Tests.fs* e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce72d-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
[<Fact>]
let ``My test`` () =
    Assert.True(true)

[<Fact>]
let ``Fail every time`` () = Assert.True(false)
```

<span data-ttu-id="ce72d-134">L'attributo `[<Fact>]` indica un metodo di test eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="ce72d-134">The `[<Fact>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="ce72d-135">Da *unit-test-con-fsharp* eseguire `dotnet test` per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="ce72d-135">From the *unit-testing-with-fsharp*, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="ce72d-136">Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="ce72d-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="ce72d-137">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="ce72d-137">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="ce72d-138">Questi due test mostrano i test più semplici superati e non superati.</span><span class="sxs-lookup"><span data-stu-id="ce72d-138">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="ce72d-139">`My test` viene superato e `Fail every time` non viene superato.</span><span class="sxs-lookup"><span data-stu-id="ce72d-139">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="ce72d-140">A questo punto, creare un test per il metodo `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="ce72d-140">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="ce72d-141">Il metodo `squaresOfOdds` restituisce una sequenza di quadrati di tutti i valori interi dispari che fanno parte della sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="ce72d-141">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="ce72d-142">Anziché tentare di scrivere tutte queste funzioni in una sola volta, è possibile creare in modo iterativo test per la convalida della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ce72d-142">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="ce72d-143">Fare in modo che ogni test venga superato significa creare le funzionalità necessarie per il metodo.</span><span class="sxs-lookup"><span data-stu-id="ce72d-143">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="ce72d-144">Il test più semplice che si può scrivere consiste nel chiamare `squaresOfOdds` con tutti i numeri pari. In questo caso il risultato dovrebbe essere una sequenza vuota di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="ce72d-144">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="ce72d-145">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="ce72d-145">Here's that test:</span></span>

```fsharp
[<Fact>]
let ``Sequence of Evens returns empty collection`` () =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="ce72d-146">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ce72d-146">Your test fails.</span></span> <span data-ttu-id="ce72d-147">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="ce72d-147">You haven't created the implementation yet.</span></span> <span data-ttu-id="ce72d-148">Fare in modo che questo test venga superato scrivendo il codice più semplice e funzionante nella classe `MathService`:</span><span class="sxs-lookup"><span data-stu-id="ce72d-148">Make this test pass by writing the simplest code in the `MathService` class that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="ce72d-149">Nella directory *unit-test-con-fsharp* eseguire di nuovo `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="ce72d-149">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="ce72d-150">Il comando `dotnet test` esegue prima una compilazione del progetto `MathService` e quindi del progetto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="ce72d-150">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="ce72d-151">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="ce72d-151">After building both projects, it runs this single test.</span></span> <span data-ttu-id="ce72d-152">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="ce72d-152">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="ce72d-153">Completamento dei requisiti</span><span class="sxs-lookup"><span data-stu-id="ce72d-153">Completing the requirements</span></span>

<span data-ttu-id="ce72d-154">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="ce72d-154">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="ce72d-155">Il prossimo test case semplice opera su una sequenza in cui l'unico numero dispari è `1`.</span><span class="sxs-lookup"><span data-stu-id="ce72d-155">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="ce72d-156">Il numero 1 è più semplice perché il quadrato di 1 è 1.</span><span class="sxs-lookup"><span data-stu-id="ce72d-156">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="ce72d-157">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="ce72d-157">Here's that next test:</span></span>

```fsharp
[<Fact>]
let ``Sequences of Ones and Evens returns Ones`` () =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="ce72d-158">L'esecuzione di `dotnet test` esegue i test e mostra che il nuovo test non viene superato.</span><span class="sxs-lookup"><span data-stu-id="ce72d-158">Executing `dotnet test` runs your tests and shows you that the new test fails.</span></span> <span data-ttu-id="ce72d-159">A questo punto, aggiornare il metodo `squaresOfOdds` per gestire il nuovo test.</span><span class="sxs-lookup"><span data-stu-id="ce72d-159">Now, update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="ce72d-160">Filtrare tutti i numeri pari fuori sequenza per fare in modo che il test venga superato.</span><span class="sxs-lookup"><span data-stu-id="ce72d-160">You filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="ce72d-161">È possibile farlo scrivendo una breve funzione di filtro e usando `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="ce72d-161">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="ce72d-162">Manca un altro passaggio: elevare al quadrato ciascuno dei numeri di dispari.</span><span class="sxs-lookup"><span data-stu-id="ce72d-162">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="ce72d-163">Per iniziare, scrivere un nuovo test:</span><span class="sxs-lookup"><span data-stu-id="ce72d-163">Start by writing a new test:</span></span>

```fsharp
[<Fact>]
let ``SquaresOfOdds works`` () =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.Equal(expected, actual)
```

<span data-ttu-id="ce72d-164">È possibile correggere il test tramite il piping della sequenza filtrata attraverso un'operazione di mapping per calcolare il quadrato di ogni numero dispari:</span><span class="sxs-lookup"><span data-stu-id="ce72d-164">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="ce72d-165">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="ce72d-165">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="ce72d-166">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ce72d-166">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="ce72d-167">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce72d-167">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce72d-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce72d-168">See also</span></span>

- [<span data-ttu-id="ce72d-169">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ce72d-169">dotnet new</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="ce72d-170">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ce72d-170">dotnet sln</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="ce72d-171">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="ce72d-171">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="ce72d-172">test dotnet</span><span class="sxs-lookup"><span data-stu-id="ce72d-172">dotnet test</span></span>](../tools/dotnet-test.md)
