---
title: Testing unità di F# in .NET Core con il test dotnet e NUnit
description: Informazioni sui concetti relativi agli unit test per F# in .NET Core tramite un'esperienza interattiva per la creazione passo-passo di una soluzione di esempio con test dotnet e NUnit.
author: rprouse
ms.date: 10/04/2018
dev_langs:
- fsharp
ms.custom: seodec18
ms.openlocfilehash: e919da8910129be027ff7e2dbed8c4564738e023
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241762"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="17d10-103">Testing unità di librerie F# in .NET Core usando il test dotnet e NUnit</span><span class="sxs-lookup"><span data-stu-id="17d10-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="17d10-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="17d10-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="17d10-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="17d10-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="17d10-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="17d10-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="17d10-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="17d10-107">Prerequisites</span></span>

- <span data-ttu-id="17d10-108">[.NET Core 2.1 SDK](https://www.microsoft.com/net/download) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="17d10-108">[.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later versions.</span></span>
- <span data-ttu-id="17d10-109">Editor di testo o editor di codice a scelta.</span><span class="sxs-lookup"><span data-stu-id="17d10-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="17d10-110">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="17d10-110">Creating the source project</span></span>

<span data-ttu-id="17d10-111">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="17d10-111">Open a shell window.</span></span> <span data-ttu-id="17d10-112">Creare una directory denominata *unit-testing-with-fsharp* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="17d10-112">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="17d10-113">In questa nuova directory eseguire il comando seguente per creare un nuovo file di soluzione per la libreria di classi e il progetto di test:</span><span class="sxs-lookup"><span data-stu-id="17d10-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="17d10-114">Creare quindi una directory *MathService*.</span><span class="sxs-lookup"><span data-stu-id="17d10-114">Next, create a *MathService* directory.</span></span> <span data-ttu-id="17d10-115">Finora è stata creata la struttura di directory e file seguente:</span><span class="sxs-lookup"><span data-stu-id="17d10-115">The following outline shows the directory and file structure so far:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="17d10-116">Impostare *MathService* come directory corrente ed eseguire il comando seguente per creare il progetto di origine:</span><span class="sxs-lookup"><span data-stu-id="17d10-116">Make *MathService* the current directory and run the following command to create the source project:</span></span>

```console
dotnet new classlib -lang F#
```

<span data-ttu-id="17d10-117">Per usare lo sviluppo basato su test (TDD) , è necessario creare un'implementazione non funzionante del servizio matematico:</span><span class="sxs-lookup"><span data-stu-id="17d10-117">To use test-driven development (TDD), you create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="17d10-118">Tornare alla directory *unit-test-con-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="17d10-118">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="17d10-119">Eseguire il comando seguente per aggiungere il progetto di libreria di classi alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="17d10-119">Run the following command to add the class library project to the solution:</span></span>

```console
dotnet sln add .\MathService\MathService.fsproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="17d10-120">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="17d10-120">Creating the test project</span></span>

<span data-ttu-id="17d10-121">Creare quindi la directory *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="17d10-121">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="17d10-122">Di seguito è illustrata la struttura di directory:</span><span class="sxs-lookup"><span data-stu-id="17d10-122">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="17d10-123">Impostare *MathService.Tests* come directory corrente e creare un nuovo progetto usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="17d10-123">Make the *MathService.Tests* directory the current directory and create a new project using the following command:</span></span>

```console
dotnet new nunit -lang F#
```

<span data-ttu-id="17d10-124">Ciò crea un progetto di test che usa NUnit come framework di test.</span><span class="sxs-lookup"><span data-stu-id="17d10-124">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="17d10-125">Il modello generato configura il Test Runner nel file *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="17d10-125">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="17d10-126">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="17d10-126">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="17d10-127">`dotnet new` nel passaggio precedente aggiunge NUnit e l'adattatore di test NUnit.</span><span class="sxs-lookup"><span data-stu-id="17d10-127">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="17d10-128">Aggiungere ora la libreria di classi `MathService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="17d10-128">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="17d10-129">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="17d10-129">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="17d10-130">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="17d10-130">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="17d10-131">Il layout della soluzione finale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="17d10-131">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathService.Tests.fsproj
```

<span data-ttu-id="17d10-132">Eseguire il comando seguente nella directory *unit-testing-with-fsharp*:</span><span class="sxs-lookup"><span data-stu-id="17d10-132">Execute the following command in the *unit-testing-with-fsharp* directory:</span></span>

```console
dotnet sln add .\MathService.Tests\MathService.Tests.fsproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="17d10-133">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="17d10-133">Creating the first test</span></span>

<span data-ttu-id="17d10-134">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="17d10-134">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="17d10-135">Aprire *UnitTest1.fs* e aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="17d10-135">Open *UnitTest1.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open NUnit.Framework
open MathService

[<TestFixture>]
type TestClass () =

    [<Test>]
    member this.TestMethodPassing() =
        Assert.True(true)

    [<Test>]
     member this.FailEveryTime() = Assert.True(false)
```

<span data-ttu-id="17d10-136">L'attributo `[<TestFixture>]` indica una classe che contiene test.</span><span class="sxs-lookup"><span data-stu-id="17d10-136">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="17d10-137">L'attributo `[<Test>]` indica un metodo di test eseguito dal Test Runner.</span><span class="sxs-lookup"><span data-stu-id="17d10-137">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="17d10-138">Dalla directory *unit-test-con-fsharp* eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="17d10-138">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="17d10-139">Il Test Runner di NUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="17d10-139">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="17d10-140">`dotnet test` avvia il Test Runner usando il progetto di unit test creato.</span><span class="sxs-lookup"><span data-stu-id="17d10-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="17d10-141">Questi due test mostrano i test più semplici superati e non superati.</span><span class="sxs-lookup"><span data-stu-id="17d10-141">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="17d10-142">`My test` viene superato e `Fail every time` non viene superato.</span><span class="sxs-lookup"><span data-stu-id="17d10-142">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="17d10-143">A questo punto, creare un test per il metodo `squaresOfOdds`.</span><span class="sxs-lookup"><span data-stu-id="17d10-143">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="17d10-144">Il metodo `squaresOfOdds` restituisce una sequenza di quadrati di tutti i valori interi dispari che fanno parte della sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="17d10-144">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="17d10-145">Anziché tentare di scrivere tutte queste funzioni in una sola volta, è possibile creare in modo iterativo test per la convalida della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="17d10-145">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="17d10-146">Fare in modo che ogni test venga superato significa creare le funzionalità necessarie per il metodo.</span><span class="sxs-lookup"><span data-stu-id="17d10-146">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="17d10-147">Il test più semplice che si può scrivere consiste nel chiamare `squaresOfOdds` con tutti i numeri pari. In questo caso il risultato dovrebbe essere una sequenza vuota di numeri interi.</span><span class="sxs-lookup"><span data-stu-id="17d10-147">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="17d10-148">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="17d10-148">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="17d10-149">Si noti che la sequenza `expected` è stata convertita in elenco.</span><span class="sxs-lookup"><span data-stu-id="17d10-149">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="17d10-150">Il framework NUnit si basa su molti tipi .NET standard.</span><span class="sxs-lookup"><span data-stu-id="17d10-150">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="17d10-151">Questa dipendenza indica che l'interfaccia pubblica e i risultati previsti supportano <xref:System.Collections.ICollection> invece di <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="17d10-151">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="17d10-152">Quando si esegue il test, si noterà che non viene superato.</span><span class="sxs-lookup"><span data-stu-id="17d10-152">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="17d10-153">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="17d10-153">You haven't created the implementation yet.</span></span> <span data-ttu-id="17d10-154">Fare in modo che questo test venga superato scrivendo il codice più semplice nella classe *Library.fs* nel progetto MathService funzionante:</span><span class="sxs-lookup"><span data-stu-id="17d10-154">Make this test pass by writing the simplest code in the *Library.fs* class in your MathService project that works:</span></span>

```csharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="17d10-155">Nella directory *unit-test-con-fsharp* eseguire di nuovo `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="17d10-155">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="17d10-156">Il comando `dotnet test` esegue prima una compilazione del progetto `MathService` e quindi del progetto `MathService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="17d10-156">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="17d10-157">Dopo la compilazione di entrambi i progetti, verranno eseguiti i test.</span><span class="sxs-lookup"><span data-stu-id="17d10-157">After building both projects, it runs your tests.</span></span> <span data-ttu-id="17d10-158">Due test vengono ora superati.</span><span class="sxs-lookup"><span data-stu-id="17d10-158">Two tests pass now.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="17d10-159">Completamento dei requisiti</span><span class="sxs-lookup"><span data-stu-id="17d10-159">Completing the requirements</span></span>

<span data-ttu-id="17d10-160">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="17d10-160">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="17d10-161">Il prossimo test case semplice opera su una sequenza in cui l'unico numero dispari è `1`.</span><span class="sxs-lookup"><span data-stu-id="17d10-161">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="17d10-162">Il numero 1 è più semplice perché il quadrato di 1 è 1.</span><span class="sxs-lookup"><span data-stu-id="17d10-162">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="17d10-163">Ecco questo test:</span><span class="sxs-lookup"><span data-stu-id="17d10-163">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="17d10-164">Il nuovo test non viene superato con l'esecuzione di `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="17d10-164">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="17d10-165">È necessario aggiornare il metodo `squaresOfOdds` per gestire il nuovo test.</span><span class="sxs-lookup"><span data-stu-id="17d10-165">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="17d10-166">È necessario filtrare tutti i numeri pari fuori sequenza per fare in modo che il test venga superato.</span><span class="sxs-lookup"><span data-stu-id="17d10-166">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="17d10-167">È possibile farlo scrivendo una breve funzione di filtro e usando `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="17d10-167">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="17d10-168">Si noti la chiamata a `Seq.toList`,</span><span class="sxs-lookup"><span data-stu-id="17d10-168">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="17d10-169">che crea un elenco che implementa l'interfaccia <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="17d10-169">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="17d10-170">Manca un altro passaggio: elevare al quadrato ciascuno dei numeri di dispari.</span><span class="sxs-lookup"><span data-stu-id="17d10-170">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="17d10-171">Per iniziare, scrivere un nuovo test:</span><span class="sxs-lookup"><span data-stu-id="17d10-171">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="17d10-172">È possibile correggere il test tramite il piping della sequenza filtrata attraverso un'operazione di mapping per calcolare il quadrato di ogni numero dispari:</span><span class="sxs-lookup"><span data-stu-id="17d10-172">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="17d10-173">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="17d10-173">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="17d10-174">La soluzione è stata strutturata in modo che l'aggiunta di nuovi pacchetti e test faccia parte del normale flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="17d10-174">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="17d10-175">La maggior parte del tempo e dell'impegno è dedicata alla soluzione degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="17d10-175">You've concentrated most of your time and effort on solving the goals of the application.</span></span>