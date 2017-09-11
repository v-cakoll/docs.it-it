---
title: "Testing unità in .NET Core usando il test dotnet e xUnit"
description: Fornisce sui concetti relativi agli unit test in .NET Core tramite un'esperienza interattiva che consente la creazione di una soluzione di esempio con test dotnet e xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: d989ee731d7ffd0439bac69afe1458e2aa10733a
ms.contentlocale: it-it
ms.lasthandoff: 08/17/2017

---
# <a name="unit-testing-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="e747d-103">Testing unità in .NET Core usando il test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="e747d-103">Unit testing in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="e747d-104">In questa esercitazione viene illustrata un'esperienza interattiva di compilazione passo passo di una soluzione di esempio finalizzata all'apprendimento dei concetti base del testing unità.</span><span class="sxs-lookup"><span data-stu-id="e747d-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="e747d-105">Se si preferisce seguire l'esercitazione usando una soluzione preesistente, [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="e747d-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="e747d-106">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e747d-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="e747d-107">Creazione del progetto di origine</span><span class="sxs-lookup"><span data-stu-id="e747d-107">Creating the source project</span></span>

<span data-ttu-id="e747d-108">Aprire una finestra della shell.</span><span class="sxs-lookup"><span data-stu-id="e747d-108">Open a shell window.</span></span> <span data-ttu-id="e747d-109">Creare una directory denominata *unit-testing-using-dotnet-test* in cui archiviare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="e747d-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="e747d-110">All'interno di questa nuova directory creare una directory *PrimeService*.</span><span class="sxs-lookup"><span data-stu-id="e747d-110">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="e747d-111">La struttura della directory fino a questo momento è la seguente:</span><span class="sxs-lookup"><span data-stu-id="e747d-111">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
```

<span data-ttu-id="e747d-112">Impostare *PrimeService* come directory corrente ed eseguire [`dotnet new classlib`](../tools/dotnet-new.md) per creare il progetto di origine.</span><span class="sxs-lookup"><span data-stu-id="e747d-112">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="e747d-113">Assegnare il nome *PrimeService.cs* al file *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="e747d-113">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="e747d-114">Per usare lo sviluppo basato su test (TDD), si creerà un'implementazione con esito negativo della classe `PrimeService`:</span><span class="sxs-lookup"><span data-stu-id="e747d-114">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

## <a name="creating-the-test-project"></a><span data-ttu-id="e747d-115">Creazione del progetto di test</span><span class="sxs-lookup"><span data-stu-id="e747d-115">Creating the test project</span></span>

<span data-ttu-id="e747d-116">Tornare alla directory *unit-testing-using-dotnet-test* e creare la directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="e747d-116">Change the directory back to the *unit-testing-using-dotnet-test* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="e747d-117">La struttura della directory è la seguente:</span><span class="sxs-lookup"><span data-stu-id="e747d-117">The directory structure is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="e747d-118">Impostare *PrimeService.Tests* come directory corrente e creare un nuovo progetto usando [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="e747d-118">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="e747d-119">In questo modo viene creato un progetto di test che usa xUnit come libreria di test.</span><span class="sxs-lookup"><span data-stu-id="e747d-119">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="e747d-120">Il modello generato configura il Test Runner nel file *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="e747d-120">The generated template configures the test runner in the *PrimeServiceTests.csproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="e747d-121">Per creare ed eseguire unit test, il progetto di test richiede altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e747d-121">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="e747d-122">Nel passaggio precedente `dotnet new` ha aggiunto xUnit e il Runner di xUnit.</span><span class="sxs-lookup"><span data-stu-id="e747d-122">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="e747d-123">Aggiungere ora la libreria di classi `PrimeService` come un'altra dipendenza del progetto.</span><span class="sxs-lookup"><span data-stu-id="e747d-123">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="e747d-124">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="e747d-124">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="e747d-125">Un'altra opzione consiste nel modificare il file *PrimeService.Tests.csproj*.</span><span class="sxs-lookup"><span data-stu-id="e747d-125">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="e747d-126">Subito sotto il primo nodo `<ItemGroup>` aggiungere un altro nodo `<ItemGroup>` con un riferimento al progetto della libreria:</span><span class="sxs-lookup"><span data-stu-id="e747d-126">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="e747d-127">È possibile visualizzare l'intero file nel [repository degli esempi](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="e747d-127">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="e747d-128">Di seguito è riportato il layout finale della soluzione:</span><span class="sxs-lookup"><span data-stu-id="e747d-128">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="e747d-129">Creazione del primo test</span><span class="sxs-lookup"><span data-stu-id="e747d-129">Creating the first test</span></span>

<span data-ttu-id="e747d-130">Prima di compilare la libreria o i test, è necessario eseguire [`dotnet restore`](../tools/dotnet-restore.md) nella directory *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="e747d-130">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="e747d-131">Questo comando ripristina tutti i pacchetti NuGet necessari a ogni progetto.</span><span class="sxs-lookup"><span data-stu-id="e747d-131">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="e747d-132">L'approccio di sviluppo basato su test richiede la creazione di un test con esito negativo. È quindi necessario che il test venga superato e che il processo venga ripetuto.</span><span class="sxs-lookup"><span data-stu-id="e747d-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="e747d-133">Rimuovere *UnitTest1.cs* dalla directory *PrimeService.Tests* e creare un nuovo file C# denominato *PrimeService_IsPrimeShould.cs* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="e747d-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="e747d-134">L'attributo `[Fact]` identifica un metodo come un singolo test.</span><span class="sxs-lookup"><span data-stu-id="e747d-134">The `[Fact]` attribute denotes a method as a single test.</span></span> <span data-ttu-id="e747d-135">Eseguire [`dotnet test`](../tools/dotnet-test.md) per compilare i test e la libreria di classi, quindi eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="e747d-135">Execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="e747d-136">Il Test Runner di xUnit include il punto d'ingresso del programma per l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="e747d-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="e747d-137">`dotnet test` avvia il Test Runner e indica a quest'ultimo un argomento della riga di comando che specifica l'assembly contenente i test.</span><span class="sxs-lookup"><span data-stu-id="e747d-137">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="e747d-138">Il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e747d-138">Your test fails.</span></span> <span data-ttu-id="e747d-139">Non è stata ancora creata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="e747d-139">You haven't created the implementation yet.</span></span> <span data-ttu-id="e747d-140">Scrivere il codice più semplice nella classe `PrimeService` per superare il test:</span><span class="sxs-lookup"><span data-stu-id="e747d-140">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

```csharp
public bool IsPrime(int candidate) 
{
    if (candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

<span data-ttu-id="e747d-141">Nella directory *PrimeService.Tests* eseguire di nuovo `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="e747d-141">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="e747d-142">Il comando `dotnet test` esegue prima una compilazione del progetto `PrimeService` e quindi del progetto `PrimeService.Tests`.</span><span class="sxs-lookup"><span data-stu-id="e747d-142">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="e747d-143">Dopo la compilazione di entrambi i progetti, verrà eseguito il test singolo,</span><span class="sxs-lookup"><span data-stu-id="e747d-143">After building both projects, it runs this single test.</span></span> <span data-ttu-id="e747d-144">che viene superato.</span><span class="sxs-lookup"><span data-stu-id="e747d-144">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="e747d-145">Aggiunta di altre funzionalità</span><span class="sxs-lookup"><span data-stu-id="e747d-145">Adding more features</span></span>

<span data-ttu-id="e747d-146">Ora che il test è stato superato, è necessario scriverne altri.</span><span class="sxs-lookup"><span data-stu-id="e747d-146">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="e747d-147">Esistono alcuni altri casi semplici per i numeri primi: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="e747d-147">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="e747d-148">È possibile aggiungerli come nuovi test, con l'attributo `[Fact]`, ma questa operazione risulta rapidamente noiosa.</span><span class="sxs-lookup"><span data-stu-id="e747d-148">You could add those as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="e747d-149">Sono disponibili altri attributi xUnit che consentono di scrivere una suite di test analoghi.</span><span class="sxs-lookup"><span data-stu-id="e747d-149">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="e747d-150">Un attributo `[Theory]` rappresenta una suite di test che eseguono lo stesso codice, ma hanno argomenti di input diversi.</span><span class="sxs-lookup"><span data-stu-id="e747d-150">A `[Theory]` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="e747d-151">È possibile usare l'attributo `[InlineData]` per specificare i valori per tali input.</span><span class="sxs-lookup"><span data-stu-id="e747d-151">You can use the `[InlineData]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="e747d-152">Anziché creare nuovi test, usare questi due attributi per creare una singola teoria che verifica diversi valori minori di due, ovvero il numero primo più basso:</span><span class="sxs-lookup"><span data-stu-id="e747d-152">Instead of creating new tests, leverage these two attributes to create a single theory that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="e747d-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="e747d-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="e747d-154">Eseguire `dotnet test`. Due test hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e747d-154">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="e747d-155">Per assicurare che tutti i test vengano superati, modificare la clausola `if` all'inizio del metodo:</span><span class="sxs-lookup"><span data-stu-id="e747d-155">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="e747d-156">Continuare a eseguire l'iterazione aggiungendo altri test, altre teorie e altro codice nella libreria principale.</span><span class="sxs-lookup"><span data-stu-id="e747d-156">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="e747d-157">Si otterrà la [versione completa dei test](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) e l'[implementazione completa della libreria](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="e747d-157">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="e747d-158">È stata compilata una piccola libreria e un set di unit test per tale libreria.</span><span class="sxs-lookup"><span data-stu-id="e747d-158">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="e747d-159">La soluzione è stata strutturata in modo da semplificare l'aggiunta di nuovi pacchetti e test, consentendo all'utente di dedicare quanto più tempo e attenzione possibili al raggiungimento degli obiettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e747d-159">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

